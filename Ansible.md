## Ad-hoc command

Lệnh ad-hoc cho phép thực hiện các task đơn ( các yêu cầu thực hiện độc lập) để ra lệnh cho các client được quản lý bởi ansible 

Cú pháp chung của ad-hoc trong ansible :

```
ansible [pattern] -m [module] -a ["module opstions"]
```

### Một số lệnh ad-hoc thường dùng :

Kiểm tra kết nối đến máy đích có thành công hay không (không liên quan đến lệnh ping) :

```
ansible all --key-file ~/.ssh/id_rsa -i inventory -m ping -u root
```

Kiểm tra thông tin chi tiết của các máy đích :

```
ansible all -m setup -i inventory
```

Thực hiện cách lệnh trên máy đích :

```
ansible all -m shell -a "shutdown now" -s
```

Cài đặt package trên máy đích :

```
ansible all -m apt -a "name=vim state=latest"
```

Liệt kê các máy do ansible management node quản lý :

```
ansible all --list-hosts
```

Chạy lệnh với quyền root (Tương dưới với dùng lệnh sudo) :

```
ansible all -m apt -a "update_cache=true" --become --ask-becom-pass
```

## Inventory

Inventory là nơi lưu trữ thông tin các đối tượng remote server với các khái niệm trong Ansible như Host, Group.

- Default group trong ansible (các group khác do chúng ta tự định nghĩa tên):
  - all: tất cả các host nằm trong file inventory
  - ungrouped: các host không thuộc group nào

- Mỗi host có thể nằm ở nhiều group nhưng trong một group, không thể xuất hiện một host 2 lần

### Tạo Custom Inventory file

Mặc định Ansible sẽ tạo file inventory ở vị trí `/etc/ansible/host`. Ansible sẽ sử dụng inventory mặc định để thực thi khi không được chỉ định với tùy chọn `-i`

Để tạo custom inventory file , ta chỉ cần tạo 1 file với nội dung là các địa chỉ của host, group mà Ansible quản lý:

```
192.168.1.20

[ubuntu]
192.168.1.30

[centos]
192.168.1.40

[linux:children]
ubuntu
centos
```

Trong đó :

- `192.168.1.20`: Không thuộc group nào cả
- `192.168.1.30`: Thuộc group `ubuntu` và group `linux` (Do group ubuntu là children của linux)
- `192.168.1.40`: Thuộc group `centos` và group `linux` (Do group centos là children của linux)

### Kiểm tra Inventory

Sử dụng câu lệnh :

```
ansible-inventory -i inventory --list
```

## Playbook

- Playbook là các tệp YAML đơn giản, dễ đọc với con người
- Playbook nói cho Ansible biết những việc cần thực hiện
- Giống 1 danh sách (list) các viết cần làm (task)
- Nó cũng có chứa các biến/các role/các handler, nếu đã định nghĩa.
- Mỗi task liên kết đến 1 đoạn code gọi là module
- 1 playbook có thể bao gồm nhiều task -> được thực hiện tuần tự

=> Hiểu đơn giản: Playbook cho phép ta nhập list các task cần làm -> thực hiện trên 1 hệ thống từ xa

VD về 1 playbook :

```
---
- hosts: all
  become: true
  tasks:

  - name: install vim - Ubuntu
    apt:
      update_cache: yes
      name: vim
      state: latest
```

## Variable

- Variable được sử dụng để lưu trữ các giá trị và có thể thay đổi giá trị được.
- Có 2 loại :
  - Built-in : Có sẵn của Ansible
  - Custom : Do người dùng tự định nghĩa
- Biến có thể được định nghĩa tại nhiều vị trí : task nằm trong Playbook, inventory, trong file riêng
- Rigister là một biến đặc biệt , là một biến từ output một task trong ansible

Để khai báo biến trong Playbook, chúng ta sẽ sử dụng thuộc tính vars mà ansible đã cung cấp. car_model sẽ là key, "BMW M3" sẽ là value. Bên dưới để sử dụng biến car_model ta sử dụng cặp dấu ngoặc nhọn và tên biến {{ car_model }}
VD về Variable:

```
---
- name: Print car's information
  hosts: localhost
  vars:
    car_model: "BMW M3"
    country_name: USA
  tasks:
    - name: Print my car model
      command: echo "My car's model is {{ car_model }}"

    - name: Print my country
      command: echo "I live in the {‌{ country_name }}"
```

## Conditions

- Ansible cho phép chỉ định điều kiện để chạy một task nào đó và chỉ khi điều kiện đó đúng thì task đó mới được thực thi.

VD : Chỉ cài đặt package vim trên ubuntu

```
---
- hosts: all
  become: true
  tasks:
  
  - name: install vim - ubuntu
	apt:
	  update_cache: yes
	  name: vim
	  state: latest
	when: ansible_distribution == "Ubuntu"
```

## Loops

- Loops cho phép ta thực hiện cùng 1 task nhiều lần, thay vì phải lặp lại từng bước.

VD : 
Khi cài đặt 3 package `nginx`, `mysql`, `php` nếu không sử dụng loop, ta phải viết từng task để cài các package :

```
- name: Install nginx
  apt: 
    name: nginx 
    state: present
- name: Install mysql
  apt: 
    name: mysql
    state: present
- name: Install php
  apt: 
    name: php
    state: present
```

Nếu sử dụng Loop để thực hiện task này :

```
- name: Install Packages
  apt: 
    name: "{{ item }}" 
    state: present
  loop:
    - nginx
    - mysql
    - php
```

## Handlers

- `Handler` là một tác vụ giống Task trong playbook nhưng khác là task được tự động khởi chạy theo flow cấu hình hoặc theo tag còn handler chỉ chạy khi có tín hiệu `notify` (Khi có thay đổi)
- `notify` là keyword dùng để gọi một hoặc nhiều handler trong một task.

VD: Cài đặt Apache sau đó khởi động service, nếu Apache package đã được cài thì handler không cần chạy

```
---
- name: Install Apache on RHEL server
  hosts: webserver
  tasks:
    - name: Install the latest version of Apache
      dnf:
        name: httpd
        state: latest
      notify:
       - Start Apache

  handlers:
     - name: Start Apache
       service:
         name: httpd
         state: started
```

## Roles

- Trong Ansible, role là một cơ chế tách playbook ra thành nhiều file. Việc này nhằm đơn giản hóa việc tái sử dụng lại nhiều lần.
- Các tác vụ liên quan đến nhau có thể được tập hợp lại thành role, sau đó áp dụng cho một nhóm máy khi cần thiết.
- Role không phải là một playbook. Role là một bộ khung (framework) để chia nhỏ playbook thành nhiều file khác nhau. Mỗi role là một thành phần độc lập bao gồm nhiều: variable, tasks, files, templates, modules

### Role Directory Structure

- Task: chứa các file yaml định nghĩa các nhiệm vụ chính khi triển khai.
- Handlers: chứa các handler sử dụng trong role.
- Files: chứa các file được sử dụng bởi role.
- Templates: chứa các file được sử dụng trong role, ví dụ như các file config.
- Vars: định nghĩa các variable được sử dụng trong roles.
- Default: định nghĩa các giá trị default của variable được sử dụng trong roles. Nếu variable không được định nghĩa trong thư mục vars, các giá trị default này sẽ được gọi.
- Meta: thư mục chứa metadata của roles.

VD: 

![](https://shorturl.at/cmg1V)

## Templates - Jinja2

- Template trong Ansible là một tệp chứa tất cả các tham số cấu hình, nhưng các giá trị động được cung cấp dưới dạng biến. Trong quá trình thực thi playbook, các biến có thể được thay thế bằng các giá trị ta cần
- Template được xử lý bởi module `template` sử dụng Jinja2. Module này lấy Template file rồi xử lý sau đó triển khai output file sang địa chỉ cụ thể trên remote host

### Chức năng chính Jinja2

- Variables : Đưa dữ liệu vào Template
- Control Structure : Xây dựng Template file phức tạp với vòng lặp, điều kiện và cấu trúc dữ liệu phức tạp

#### Ví dụ

Tạo Template file `test.conf.j2`

```
My favourite color is {{ favourite_color }}

{% if age > 18 %}
You are an adult, and you can vote in the voting center: {{ voting_center }}
{% else %}
Sorry, you are minor and you can’t vote yet.
{% endif %}

A list of fruits:
{% for fruit in fruits %}
 - {{ fruit }}
{% endfor %}
```

Tạo Playbook `test_templates_playbook.yml` sử dụng module `template`  :

```
- name: Playbook to test templates
 hosts: all
 vars:
   favourite_color: blue
   age: 21
   voting_center: ab456-g
   fruits:
     - banana
     - apple
     - mango
     - pear

 tasks:
 - name: Template test
   template:
     src: templates/test.conf.j2
     dest: /tmp/test.conf
```

Sau khi chạy Playbook , file `/tmp/test.conf` sẽ được tạo :

```
My favourite color is blue

You are an adult, and you can vote in the voting center: ab456-g

A list of fruits:
  - banana
  - apple
  - mango
  - pear
```

## Configuration file

- Default configuration file của ansible nằm tại `/etc/ansible/ansible.cfg`
- Ansible tìm kiếm config file theo thứ tự sau, xử lý theo file tìm được đầu tiên và bỏ qua các trường hợp khác:
  - `$ANSIBLE_CONFIG` : nếu environment variable được thiết lập
  - `ansible.cfg` : nếu file này nằm trong thư mục hiện tại
  - `~/.ansible.cfg` : nếu file này nằm trong thư mục home của người dùng hiện tại
  - `/etc/ansible/ansible.cfg` : default config file

### Một số Configuration file section 

#### [default] - chứa 1 số giá trị default đơn giản

VD :

```
[defaults]
inventory = /etc/ansible/hosts # path của inventory
private_key_file = ~/.ssh/id_rsa #path của private ke
remote_user= root #chỉ định user
remote_port = 22 #chỉ định port
.....
```

#### [privilege_escalation]

```
become=True # Cho phép trở thành user khác sau khi đăng nhập
become_ask_pass=True # Hỏi pass để nâng quyền hạn
become_method=sudo # Phương thức nâng quyền hạn khi become được bật
become_user=root # User được trở thành
```

### [persistent_conection]

```
command_timeout=30 #Thời gian chờ phản hồi từ remote host trước khi hết hạn kết nối
connect_timeout=30 #Thời gian kết nối được duy trì trong bao lâu sau khi không hoạt động
```


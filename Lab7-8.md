## icinga2

### Các trạng thái của host/service trong icinga2

- Trạng thái của Host:
  - UP : host ở trạng thái sẵn sàng
  - DOWN : host ở trạng thái “chết”
  
- Trạng thái của Service :
  - OK : service làm việc bình thường – return code = 0
  - WARNING: service có chút vấn đề nhưng vẫn chưa nghiêm trọng – return code = 1
  - CRITICAL: service gặp vấn đề nghiêm trọng – return code = 2
  - UNKNOW: không thể xác định trạng thái của service – return code = 3
  
- Hard và soft state:
  - Soft State: Khi phát hiện vấn đề xảy ra với host/service, icinga sẽ kiểm tra lại host/service này một số lần trước khi gửi thông báo tới admin. Điều này đảm bảo rằng không có thông báo không cần thiết nào được gửi về các lỗi tạm thời. Trong thời gian này, host/service ở trong trạng thái SOFT state
  - Hard State: Đối với Hard State, khi mà đã kiểm tra một số lần mà host/service vẫn ở trong trạng thái non-OK state, host/service sẽ chuyển sang trạng thái HARD state và gửi thông báo tới admin

### File config của icinga2 

- /etc/icinga2/icinga2.conf :
  - file cấu hình chính của icinga2
  - Define nơi lưu các file cấu hình
```
include “constants.conf”
include_recursive “conf.d”
```

- /etc/icinga2/constants.conf : Chứa các biến toàn cục
```
const PluginDir = “/usr/lib64/nagios/plugins”
const ZoneName = NodeName
```

- zones.conf : file dùng để chỉ định các zone và endpoint object cho Distributed Monitor

- /etc/icinga2/conf.d/hosts.conf :
 - Chứa thông tin về host
 - Dùng “object Host hostname” để định nghĩa host
```
object Host NodeName {

import “generic-host”

address = “127.0.0.1”

var.os = Linux

}
```

- /etc/icinga2/conf.d/service.conf : Khai báo các command và rule của các Service áp dụng với các host

```
apply Service “ssh” {

import “generic-service”

check_command = “ssh”

assign where host.address && host.vars.os == “Linux”

}
```

- /etc/icinga2/conf.d/user.conf : Chứa danh sách các user có thể nhận được notification khi có vấn đề xảy ra.

- /etc/icinga2/conf.d/notifications.conf : Chứa cài đặt thông báo khi xảy ra vấn đề với host/service.

- /etc/icinga2/conf.d/commands.conf : Chứa các command và cấu trúc command

- /etc/icinga2/conf.d/groups.conf : Chứa định nghĩa host groups và service groups
```
object HostGroup "linux-servers" {
    display_name = "Linux Servers"
    assign where host.vars.os == "Linux"
}
```

- /etc/icinga2/conf.d/template.conf : chứa các template về host/service để tái sử dụng các cấu hình và giảm thiểu việc lặp lại cấu hình cho các host/service có cùng cấu hình.
```
template Host "generic-host" {
  max_check_attempts = 5
  check_interval = 1m
  retry_interval = 30s

  check_command = "hostalive"
}

template Service "generic-service" {
  max_check_attempts = 3
  check_interval = 1m
  retry_interval = 30s
}
```



### Install Icinga2

Thêm Icinga Package Repository :

```
apt update
apt -y install apt-transport-https wget gnupg

wget -O - https://packages.icinga.com/icinga.key | gpg --dearmor -o /usr/share/keyrings/icinga-archive-keyring.gpg

. /etc/os-release; if [ ! -z ${UBUNTU_CODENAME+x} ]; then DIST="${UBUNTU_CODENAME}"; else DIST="$(lsb_release -c| awk '{print $2}')"; fi; \
 echo "deb [signed-by=/usr/share/keyrings/icinga-archive-keyring.gpg] https://packages.icinga.com/ubuntu icinga-${DIST} main" > \
 /etc/apt/sources.list.d/${DIST}-icinga.list
 echo "deb-src [signed-by=/usr/share/keyrings/icinga-archive-keyring.gpg] https://packages.icinga.com/ubuntu icinga-${DIST} main" >> \
 /etc/apt/sources.list.d/${DIST}-icinga.list

apt update
```

Install icinga2

```
apt install icinga2
```

Install Check Plugins để giám sát external service
```
apt install monitoring-plugins
```

Install Icinga2 API để kết nối với icinga web

```
icinga2 api setup
```

Sau đó restart icinga2 để áp dụng các thay đổi

```
systemctl restart icinga2
```

### Install Icinga DB

Install Icinga DB Redis Package :

```
apt install icingadb-redis
```

Chạy Icinga DB Redis :

```
systemctl enable --now icingadb-redis
```

Enable icingadb feature:

```
icinga2 feature enable icingadb
```

restart icinga2 để áp dụng các thay đổi

```
systemctl restart icinga2
```

Cài đặt icingadb :

```
apt install icingadb
```

Cài mysql database cho icingadb :

```
# mysql -u root -p

CREATE DATABASE icingadb;
CREATE USER 'icingadb'@'localhost' IDENTIFIED BY 'CHANGEME';
GRANT ALL ON icingadb.* TO 'icingadb'@'localhost';
```

Nhập icingadb schema :

```
mysql -u root -p icingadb </usr/share/icingadb/schema/mysql/schema.sql
```

Chạy icingadb :

```
systemctl enable --now icingadb
```

### Install Icinga web

Cài đặt các package cần thiết :

```
apt-get install icingaweb2 libapache2-mod-php icingacli
```

Tạo database cho icingaweb :

```
MariaDB [mysql]> CREATE DATABASE icingaweb2;

MariaDB [mysql]> GRANT ALL ON icingaweb2.* TO icingaweb2@localhost IDENTIFIED BY 'CHANGEME';
```

Tạo 1 token để sử dụng cho quá trình thiết lập Icinga2 Web

```
icingacli setup token create
```

Truy cập vào địa chỉ <(ip-address)>/icingaweb2/setup trên trình duyệt để thực hiện setup Icinga Web.

Kết quả sau khi cài đặt

![](https://i.imgur.com/1YfA242.png)o


## TIG Stack

### Tổng quan

TIG stack là một bộ công cụ phổ biến được sử dụng trong lĩnh vực giám sát và thu thập dữ liệu hệ thống. TIG viết tắt của Telegraf, InfluxDB và Grafana, là 3 thành phần chính của bộ công cụ này

- Telegraf: Là một agent giám sát mã nguồn mở, chuyên nghiệp trong việc thu thập và gửi dữ liệu về các hệ thống và ứng dụng. Telegraf hỗ trợ nhiều nguồn dữ liệu khác nhau và có khả năng mở rộng để tích hợp với nhiều loại hệ thống khác nhau

- InfluxDB: Là một cơ sở dữ liệu dạng time-series, được thiết kế đặc biệt để lưu trữ và truy vấn dữ liệu theo thời gian. Dữ liệu time-series thích hợp cho việc lưu trữ thông tin như log hệ thống, dữ liệu giám sát và các dữ liệu theo thời gian khác
- Grafana: Là một nền tảng giám sát và trực quan hoá dữ liệu mã nguồn mở. Grafana cho phép bạn tạo các đồ thị, biểu đồ và bảng điều khiển để hiển thị từ InfluxDB và các nguồn dữ liệu khác một cách dễ dàng và trực quan. Điều này giúp người quản trị phát triển theo dõi hiệu suất hệ thống, phân tích vấn đề và đưa ra quyết định thông minh

### Hoạt động của TIG Stack

![](https://i.imgur.com/TzgFn2G.png)

- Telegraf là 1 agent dùng để thu thập số liệu hệ thống cũng như dịch vụ trên hệ thống mà nó chạy

- Các số liệu được thu thập và đưa vào InfluxDB

- Grafana sau đó thực hiện truy vấn dữ liệu từ InfluxDB và biểu diễn dữ liệu dưới dạng đồ thị trực quan

### Triển khai

#### InfluxDB

##### Cài đặt InfluxDB

Thêm Influxdata key :

```
wget -q https://repos.influxdata.com/influxdata-archive_compat.key
echo '393e8779c89ac8d958f81f942f9ad7fb82a25e133faddaf92e15b16e6ac9ce4c influxdata-archive_compat.key' | sha256sum -c && cat influxdata-archive_compat.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/influxdata-archive_compat.gpg > /dev/null
```

Thêm repositorty Influxdata và update lại các thay đổi :

```
echo 'deb [signed-by=/etc/apt/trusted.gpg.d/influxdata-archive_compat.gpg] https://repos.influxdata.com/debian stable main' | sudo tee /etc/apt/sources.list.d/influxdata.list
apt update -y
```

Cài đặt gói influxdb :

```
apt install influxdb2 -y
```

Khởi động dịch vụ và cấu hình khởi động cùng hệ thống :

```
systemctl start influxdb
systemctl enable influxdb
```

##### Cấu hình InfluxDB

Để lưu trữ dữ liệu từ Telegraf, ta cần thiết lập cơ sở dữ liệu và người dùng Influx :

```
influx setup
> Welcome to InfluxDB 2.0!
? Please type your primary username datldt
? Please type your password ***********
? Please type your password again ***********
? Please type your primary organization name TIG Stack
? Please type your primary bucket name tigstack
? Please type your retention period in hours, or 0 for infinite 360
? Setup with these parameters?
  Username:          datldt
  Organization:      TIG Stack
  Bucket:            tigstack
  Retention Period:  360h0m0s
 Yes
User    Organization    Bucket
datldt  TIG Stack      	tigstack
```

Khi ta đã thực hiện thiết lập ban đầu, ta có thể đăng nhập vào URL bằng thông tin đăng nhập được tạo ở trên với địa chỉ : `http://<serverIP>:8086/`

![](https://i.imgur.com/trVLUGQ.png)

Quá trình thiết lập ban đầu sẽ tạo mã token mặc định có toàn quyền đọc và ghi đối với tất cả organizations trong database. Ta cần một mã token mới cho mục đích bảo mật. Mã này sẽ chỉ kết nối với Organization và Bucket mà chúng ta muốn kết nối.

Để tạo mã token mới, icon như hình dưới nằm bên trái sidebar và click và API Tokens :
![](https://www.howtoforge.com/images/how_to_install_tig_stack_telegraf_influxdb_and_grafana_on_ubuntu_2204/influxdb-tokens-list.png?ezimgfmt=rs:178x195/rscb10/ng:webp/ngcb9)

Click vào `Generate API Token` và chọn Custom API Token sau đó chọn các quyền được gán :

![](https://i.imgur.com/RY4oPlr.png)

Sau đó copy lại mã Token :

![](https://i.imgur.com/6d91YoS.png)

#### Telegraf

Cài đặt Telegraf :

```
apt install telegraf -y
```

Khởi động dịch vụ và cấu hình khởi động cùng hệ thống :

```
systemctl start telegraf
systemctl enable telegraf
```

Mở file cấu hình để chỉnh sửa

```
vim /etc/telegraf/telegraf.conf
```

Sửa các dòng sau để kết nối Telegraf với InfluxDB :

![](https://i.imgur.com/FD3z5fX.png)

Khởi động lại dịch vụ Telegraf và InfluxDB :

```
systemctl restart influxdb
systemctl restart telegraf
```

#### Grafana

##### Cài đặt Grafana

Add key vào các gói cài đặt :

```
wget -q -O - https://packages.grafana.com/gpg.key | apt-key add -

add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"
```

Update repo và cài đặt Grafana :

```
apt update

apt install -y grafana
```

Khởi động grafana-server và cho phép khởi động cùng hệ thống :

```
systemctl start grafana-server

systemctl enable grafana-server
```

##### Cấu hình Grafana

Truy cập trên trình duyệt với địa chỉ. Grafana mặc định sẽ sử dụng port 3000

![](https://i.imgur.com/M5inCp7.png)

Đăng nhập bằng tài khoản admin/admin. Sau đó, sẽ được yêu cầu đổi mật khẩu ngay

Thêm InfluxDB làm nguồn dữ liệu (datasource) cho Grafana :

![](https://i.imgur.com/u9JolwW.png)

Điền thông tin database :

![](https://i.imgur.com/Tj09a9J.png)

![](https://i.imgur.com/9zxwyS5.png)

Sau khi điền xong, ta chọn Save & Test

##### Import Grafana dashboard

Ta import dashboard với id 15650

![](https://i.imgur.com/8Qkh6bX.png)
![](https://i.imgur.com/ERRGGV6.png)

Kết quả :

![](https://i.imgur.com/dad5b0z.png)

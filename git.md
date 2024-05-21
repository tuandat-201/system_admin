## Git là gì ?

Git là một hệ thống quản lý phiên bản phân tán (DVCS – Distributed Version Control System). Nó được sử dụng để theo dõi và quản lý sự thay đổi trong mã nguồn của dự án phần mềm hoặc bất kỳ loại tập tin văn bản nào. Git cho phép nhiều người cùng làm việc trên cùng một dự án mà không gây xung đột lẫn nhau, và cung cấp khả năng quản lý lịch sử của mã nguồn.

## Cách hoạt động

![Cách hoạt động của Git](https://miro.medium.com/max/602/1*OqKfKe3mqCRbaWT2Y8YDOQ.png)

- Working Directory : thư mục mà sẽ thực hiện mọi công việc như tạo, chỉnh sửa, xóa và quản lý file
- Staging Area : nơi bạn liệt kê những thay đổi đã thực hiện ở working directory
- Repository: nơi Git lưu những thay đổi trên thành các phiên bản (version) khác nhau của project. 

## Branch - Nhánh và thao tác với nhánh

Một repository có thể chia làm nhiều nhánh giúp chúng ta có thể phát triển các tính năng riêng biệt trong dự án trên mỗi nhánh. Bằng cách sử dụng các nhánh riêng biệt, main branch vẫn nguyên vẹn mà không bị ảnh hưởng trước khi các thay đổi được review và merge vào project

![branch](https://www.nobledesktop.com/image/gitresources/git-branches-merge.png)

Sau khi tạo repository mới chúng ta sẽ có sẵn branch master, branch này thường được sử dụng để triển khai (deploy) dự án thực tế cho người dùng cuối (end user).

#### Tạo nhánh

VD : Tạo nhánh develop từ nhánh main

```
git branch develop
```


#### Chuyển nhánh 

Xem các branch đang có trên local và ta đang ở branch nào, dấu sao (*) trước tên branch thể hiện ta đang ở branch đó.

```
git branch

# Out put :
#   develop
# * master
```

Chuyển sang nhánh `develop` :

```
git checkout develop
```

Với `git checkout -b` sẽ tạo branch mới từ branch hiện tại và đồng thời chuyển sang branch mới :

```
git checkout -b feature
```

#### Hợp nhất nhánh

VD : 

Tạo thêm file authen.txt với nội dung "Authen feature", add vào Staging Area và commit với message "Authen feature complete". File authen.txt vừa tạo đã được commit thành công vào branch `feature`.

```
git add authen.txt
git commit -m "Authen feature complete"
```

Di chuyển về nhánh `master` :

```
git checkout master
```

Lúc này Working directory của chúng ta không hề có file authen.txt vì nó được commit ở branch feature/authen, còn bây giờ chúng ta đang ở branch master. Để hợp nhất các thay đổi từ bên branch feature/authen sang branch hiện tại ta sử dụng lệnh git merge.

```
git merge feature
```

#### Xóa nhánh

Để xóa một branch ta sử dụng lệnh `git branch -d [branch_name]` :

```
git branch -D feature
```

## Các lệnh git cơ bản

- Tạo repository mới :

```
git init
```

- Clone một remote repository :

```
git clone [path to repository]
```

- Thêm file vào Staging Are :

```
git add [file]
```

- Kiểm tra thay đổi giữa Working Directory và Staging Are :

```
git diff [file]
```

- Commit thay đổi từ Staging Area vào repository :

```
git commit -m "[message]"
```

- Xem lại lịch sử các lần commit :

```
git log
```

- Đẩy các thay đổi từ Local Repos lên Remote Repos :

```
git push origin master
```

- Kết nối Local Repos với Remote Repos :

```
git remote add origin [Remote Repos]
```

- Cập nhật thay đổi từ Remote Repos xuống Local Repos :

```
git pull
```

- Huỷ bỏ thay đổi trong Working Directory

```
git checkout HEAD [file_name]
```

- Loại bỏ thay đổi của file ra khỏi Stagging Area

```
git reset HEAD [file_name]
```

- Quay lại lần commit nào đó trong commit history

```
git reset [commit_hash]
```

Lưu ý : Mặc định git reset sẽ sử dụng option --mixed , 2 option còn lại là --hard , --soft

- Tạo commit mới có nội dung giống hệt với commit muốn quay về :

```
git revert [commit_hash]
```

## Git Flow

Flow ở đây hiểu là "Luồng", Git-flow nghĩa là "Luồng sử dụng Git", "Quy trình sử dụng Git", v.v. Trong công việc thực tế thì các team, các doanh nghiệp đưa Git vào quy trình làm việc thường sẽ tuân thủ theo một Git-flow nào đó

Gitflow chỉ là một ý tưởng trừu tượng về quy trình sử dụng Git, Nó chỉ ra cách thức setup các loại branchs khác nhau và cách thức để merge chúng lại với nhau.

![Git Flow](https://i.imgur.com/WpX7moy.png)

- Branch khởi đầu sẽ là master. Khi bắt đầu phát triển tính năng sẽ checkout từ master ra develop.

- Mỗi tính năng sẽ checkout tiếp từ develop ra các nhánh có prefix là feature/. (ví dụ tính năng login là feature/login, tính năng logout là feature/logout…) và phát triển độc lập với nhau. Sau khi hoàn thành thì merge feature vào develop.

- Đến kì release sẽ merge develop vào release, nhánh release đóng vai trò như là môi trường stagging của dự án. Nhánh release lúc này chỉ gồm các commit fixbug mà không bao gồm commit thêm tính năng nào nữa. Nếu có fixbug phát sinh trên release thì merge lại vào develop.

- Khi bug đã hết cũng là lúc tiến hành merge release vào master. Tại đây ta có thể đánh dấu tag cho commit đó để làm dấu hiệu phiên bản phát hành tiện lợi cho việc theo dõi và truy vết.

- Khi chạy production không thể tránh khỏi lỗi phát sinh, khi đó chúng ta checkout từ master ra nhánh có tiền tố hotfix/ để fixbug. Sau khi sửa lỗi xong thì merge nhánh vừa tạo vào develop, từ develop kiểm tra thấy bản fix đã hoạt động thì tiếp tục merge hotfix vào master và kết thúc phiên sửa lỗi.


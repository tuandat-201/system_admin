## Partition

### Không tách partition có được không ?

Chúng ta có thể định dạng toàn bộ ổ đĩa mà không cần bất cứ phân vùng nào. Ta chỉ cần tạo filesystem cho ổ đĩa sau đó mount lại và sử dụng.

### Các lý do nên sử dụng partition :

- Tổ chức, quản lý dữ liệu tốt hơn
- Giảm nguy cơ mất mát dữ liệu do phân mảnh
- Thuận lợi cho việc sao lưu và khôi phục
- Cải thiện hiệu suất
- Có thể sử dụng các filesystem khác nhau cho các partition khác nhau để tối ưu, sử dụng được các tính năng đặc biệt mà filesystem cung cấp
- Bảo vệ dữ liệu có chọn lọc hơn, ta có thể mã hóa 1 số phân vùng nhất định để bảo vệ thay vì cả ổ đĩa

## Vim

### Cách copy trong vim

#### Sử dụng Visual mode

1. Sử dụng phím `v` để vào Visual mode, sau đó dùng phím điều hướng để chọn dòng muốn copy.
2. Nếu muốn copy nhiều dòng, có thể ấn phím `v` rồi nhập số dòng muốn chọn. Ví du : chọn 100 dòng tính từ vị trí con trỏ, ta bấm phím `v` + `100`
3. Bấm phím `y` để copy các dòng đã chọn
4. Bấm phím `p` để paste vào phím sau con trỏ, phím `P` để paste vào phía trước con trỏ.

#### Copy bằng phím tắt

- `yy` : Copy dòng hiện tại
- `3yy` : Copy nhiều dòng , câu lệnh này copy 3 dòng tính từ vị trí con trỏ
- `yEnd` : Copy mọi thứ bắt đầu từ vị trí con trỏ đến cuối dòng
- `yHome` : Copy mọi thứ bắt đầu từ đầu dòng đến vị trí con trỏ
- `yiw` : Copy từ hiện tại

### Khắc phục lỗi đang sử dụng vim mà bất ngờ bị gián đoạn, chưa kịp lưu

Ta có file `test.txt` sau :
```
File test.txt da luu
```

Khi đang thực hiện chỉnh sửa, máy tính bỗng dưng bị sập. Sau khi chúng ta truy cập lại file bằng vim để tiếp tục , nó hiện ra lỗi sau :
```
E325: ATTENTION
Found a swap file by the name ".test.txt.swp"
          owned by: datle201   dated: T4 Thg 1 31 11:18:26 2024
         file name: ~datle201/Desktop/test.txt
          modified: no
         user name: datle201   host name: Dat-Intern
        process ID: 9285 (STILL RUNNING)
While opening file "test.txt"
             dated: T4 Thg 1 31 11:18:14 2024

(1) Another program may be editing the same file.  If this is the case,
    be careful not to end up with two different instances of the same
    file when making changes.  Quit, or continue with caution.
(2) An edit session for this file crashed.
    If this is the case, use ":recover" or "vim -r test.txt"
    to recover the changes (see ":help recovery").
    If you did this already, delete the swap file ".test.txt.swp"
    to avoid this message.

Swap file ".test.txt.swp" already exists!
[O]pen Read-Only, (E)dit anyway, (R)ecover, (Q)uit, (A)bort: 
```

Trước tiên, cần hiểu về swap file trong vim

#### Swap file

Khi bắt đầu thực hiện chỉnh sửa file với vim, vim sẽ tự động tạo ra swap file. Swap file là 1 buffer file dưới dạng nhị phân, được vim tạo ra như một bản sao tạm thời của file đang được chỉnh sửa.
Khi hoàn thành việc chỉnh sửa file (file được lưu vào disk), nội dung của swap file này được hợp nhất với file gốc và swap file sẽ bị xóa.

#### Mục đích của swap file

1. Tránh trường hợp nhiều instance của vim truy cập cùng 1 file (Nhiều người dùng trong hệ thống cùng mở và truy cập 1 file)

2. Khắc phục sự cố khi bị crash

#### Khắc phục sự cố

Trong trường hợp máy tính hoặc chính vim gặp sự cố , ta có thể sử dụng swap file để khắc phục

Các option để xử lý swap file :
```
[O]pen Read-Only, (E)dit anyway, (R)ecover, (D)elete it, (Q)uit, (A)bort
```
Trong đó 
- `O` : Mở file dưới dạng chỉ đọc
- `E` : Tiếp tục chỉnh sửa những thay đổi
- `R` : Khôi phục lại lần sửa đổi gần nhất
- `Q`,`A` : Cùng là thoát
- `D` : Chỉ xuất hiện nếu vim biết rằng không có trình soạn thảo nào khác đang mở file.

Sau khi lưu lại những sửa đổi, ta có thể xóa swap file để không đưa ra thông báo lỗi nữa

## Repository

Repository chứa thông tin về địa chỉ của các package, còn các package sẽ nằm ở vị trí do người viết ra quản lý

## Load average

Load average thể hiện rằng có bao nhiêu task đang chờ, bao nhiêu task đang được xử lý và bao nhiêu task đã được CPU xử lý trong thời gian 1p , 5p , 15p.

Load average phụ thuộc vào số lượng core mà hệ thống có. Load average nhỏ hơn số lượng core thì có nghĩa là hệ thống đang hoạt động bình thường.

Ví dụ : Hệ thống chạy CPU có 4 core, có average nhỏ hơn 4 nghĩa là hệ thống đang hoạt động bình thường. Nếu hệ thống có load average hơn số core , hệ thống đang chịu tải nặng (quá tải).

## kill vs kill -9

với kill, nó sẽ đợi tiến trình giải phóng bộ nhớ, xử lý tiến trình con, ... tuy nghiên nó có thể từ chối dừng tiến trình còn lệnh kill -9 buộc tiến trình dừng luôn, nó không quan tâm tiến trình con chạy hay không.

## Mount tự động bằng fstab

### Cấu trúc của fstab

```
[Device] [Mount Point] [File System Type] [Options] [Dump] [Pass]
```

|Trường|Mô tả|
|-|-|
|device|UUID hoặc đường dẫn tới file thiết bị trong thư mục /dev|
|mount point|Điểm mount|
|file system type|Định dạng file system của thiết bị (ext2,ext3,ext4,xfs..)|
|options|Các tùy chọn, nếu sử dụng nhiều tùy chọn có thể phân tách bởi dấu ,|
|dump|Tùy chọn sao lưu filesystem hay không (0 để bỏ qua, 1 để thực hiện sao lưu)|
|pass num|Thứ tự kiểm tra lỗi lúc khởi động , mặc định là 0 (không kiểm tra), 1 là root filesystem, các filesystem còn lại được định nghĩa với giá trị là 2.|

## RAID 5 và So sánh các loại RAID

### RAID 5

Đặc điểm của chuẩn này là dùng một phần không gian lưu trữ để lưu mã sửa sai. Dữ liệu và bản sao lưu được chia lên tất cả các ổ cứng

Ví dụ có 8 đoạn dữ liệu được đánh số từ 1 đến 8 và 3 ổ đĩa cứng có dung lượng giống nhau. Đoạn dữ liệu số 1 và số 2 sẽ được ghi vào ổ đĩa 1 và 2 riêng rẽ, đoạn sao lưu của chúng được ghi vào ổ cứng 3. Đoạn số 3 và 4 được ghi vào ổ 1 và 3 với đoạn sao lưu tương ứng ghi vào ổ đĩa 2. Đoạn số 5, 6 ghi vào ổ đĩa 2 và 3, còn đoạn sao lưu được ghi vào ổ đĩa 1 và sau đó tŕnh tự này lặp lại, đoạn số 7,8 được ghi vào ổ 1, 2 và đoạn sao lưu ghi vào ổ 3 như ban đầu

Như vậy, RAID 5 vừa đảm bảo tốc độ có cải thiện, vừa giữ được tính an toàn cao. Dung lượng đĩa cứng cuối cùng bằng tổng dung lượng đĩa sử dụng trừ đi một ổ. Tức là nếu dùng 3 ổ 80GB thì dung lượng cuối cùng sẽ là 160GB. Nhờ đó nếu hỏng một ổ cứng bất kỳ thì hệ thống vẫn hoạt động bình thường, tuy nhiên hệ thống sẽ lỗi nếu hỏng từ 2 ổ trở lên 

#### Cơ chế dự phòng của RAID 5

Raid 5 sử dụng parity để dự phòng, parity đạt được bằng cách sử dụng toán tử XOR

|A|B|Kết quả|
|:-:|:-:|:-:|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|0|

Ví dụ : Ta có 3 disk và 1 trong số đó chứa thông tin về parity. Để tính toán parity này, ta chỉ cần áp dụng toán tử XOR cho các data ở 2 disk còn lại. Giả sử ta lưu trữ ở disk đầu tiên ký tự `a` và `b` ở disk thứ 2.

```
0110 0001 (Decimal 97 = ‘a’)
0110 0010 (Decimal 98 = ‘b’)
============XOR============
0000 0011 (Decimal 3 – Parity)
```

Disk thứ 3 của chúng ta sẽ lưu thông tin parity là 0000 0011 - Decimal 3. Dựa trên parity này chúng ta có thể khôi phục lại dữ liệu nếu có 1 disk bị lỗi. Khôi phục lại dữ liệu bằng cách áp dụng toán tử XOR cho dữ liệu ở disk chưa bị lỗi với thông tin parity

```
0110 0010 (Decimal 98 = ‘b’)
0000 0011 (Decimal 3 – Parity)
============XOR============
0110 0001 (Decimal 97 = ‘a’)
```

Kết quả trả về dữ liệu đã mất. Ở ví dụ này , ta chỉ tính toán parity với 1 byte (8 bit), nhưng thực tế RAID 5 tính toán lớn hơn nhiều.

### So sánh các loại RAID

* RAID 0 có tốc độ đọc ghi nhanh nhất,
* RAID 1 có tốc độ đọc nhanh hơn ổ thường, Tốc độ ghi không thay đổi,
* RAID 5 có tốc độ đọc nhanh hơn RAID 1 gần tương đương RAID 0, Tốc độ ghi chậm nhất do phải tính toán PARITY

## Lí do Static ip và Dynamic ip

Vì ip tĩnh không thay đổi, còn ip động do có thời gian thuê nên địa chỉ có thể bị hết hạn và thay đổi bất kỳ lúc nào. Do đó, khi cần duy trì tính sẵn sàng của dịch vụ của server ta phải cài đặt ip tĩnh

## Các cách tìm địa chỉ IP của một domain

### Sử dụng lệnh Dig

```
dig <website>
```

### Sử dụng lệnh nslookup

```
nslookup <website>
```

### Sử dụng lệnh host

```
host <website>
```

### Sử dụng lệnh ping

```
ping <website>
```

## Cách hoạt động của DHCP

![](https://www.computernetworkingnotes.org/images/cisco/ccna-study-guide/csg68-01-how-dhcp-works.png)

### DHCP Discovery

DHCP client gửi gói tin DHCP Discovery tới địa chỉ broadcast 255.255.255.255 để tìm DHCP server

### DHCP Offer

Khi DHCP server nhận được DHCP Discovery , nó sẽ đưa ra đề xuất một Ip address có trong Ip address pool của nó bằng cách gửi DHCP Offer tới DHCP Client. Trong gói tin này chứa IP address, Subnet mask, Default gateway, DNS address, thông tin về lease

### DHCP Request

Một DHCP client có thể nhận nhiều DHCP Offer, tuy nhiên chỉ có thể chấp nhận 1 Offer duy nhất. Để phản hồi lại Offer, DHCP client gửi DHCP Request tới địa chỉ của DHCP Server được chấp nhận

### DHCP Acknowledgment

DHCP server gửi DHCP Acknowledgment tới DHCP client để xác nhận việc thuê địa chỉ của DHCP. Tại thời điểm này, việc cấu hình địa chỉ IP đã hoàn thành và client có thể sử dụng địa chỉ Ip mới này

## Lí do sử dụng passphare

passphrase giúp bảo vệ private key bằng cách mã hoá private key, ngăn chặn việc private key bị copy bởi những người có khả năng truy cập vào máy tính mà không đủ thẩm quyền.

## rsync và scp

### scp

SCP (secure copy - sao chép an toàn) là lệnh do OpenSSH Client cung cấp, nó cho phép truyền tải file qua lại giữa máy local và remote (server), nó sử dụng giao thức SSH để truyền file. Có thể sử dụng đến lệnh scp khi muốn:

* Copy file,thư mục, từ máy local lên server
* Copy file,thư mục, từ máy server (remote) về local (client)
* Copy file,thư mục, từ máy server (remote) này sang máy server (remote) khác

### rsync

Rsync (remote sync) là công cụ đồng bộ file, thư mục của Linux. Nó sử dụng thuật toán khi copy dữ liệu sao cho dữ liệu phải copy là nhỏ nhất (chỉ copy những gì thay đổi giữa nguồn và gốc), khi đồng bộ nó giữ nguyên mọi thuộc tính của file, thư mục (từ chủ sở hữu, quyền truy cập file ...)

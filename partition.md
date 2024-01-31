## Partition

###Các lý do nên sử dụng partition :

- Tổ chức, quản lý dữ liệu tốt hơn
- Giảm nguy cơ mất mát dữ liệu do phân mảnh
- Thuận lợi cho việc sao lưu và khôi phục
- Cải thiện hiệu suất
- Có thể sử dụng các filesystem khác nhau cho các partition khác nhau để tối ưu, sử dụng được các tính năng đặc biệt mà filesystem cung cấp
- Bảo vệ dữ liệu có chọn lọc hơn, ta có thể mã hóa 1 số phân vùng nhất định để bảo vệ thay vì cả ổ đĩa

### Không tách partition có được không ?

Chúng ta có thể định dạng toàn bộ ổ đĩa mà không cần bất cứ phân vùng nào. Ta chỉ cần tạo filesystem cho ổ đĩa sau đó mount lại và sử dụng.

### Tài liệu tham khảo

https://www.familug.org/2014/11/partition-tai-sao-can-phan-vung-o-cung.html

https://www.datanumen.com/blogs/6-primary-reasons-partitioning-hard-disk/

https://www.stellarinfo.com/article/should-you-partition-your-hard-drive-pros-and-cons.php

https://askubuntu.com/questions/1209553/is-there-any-benefit-to-partitioning-hdd-data-only-disk

https://unix.stackexchange.com/questions/685642/do-i-need-to-partition-my-external-hard-drive

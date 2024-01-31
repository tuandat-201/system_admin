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
[O]pen Read-Only, (E)dit anyway, (R)ecover, (Q)uit, (A)bort
```

### Tài liệu tham khảo

https://www.warp.dev/terminus/vim-copy-paste#:~:text=Copying%20(Yanking),-yy%3A%20Copy%20the&text=3yy%3A%20To%20yank%20multiple%20lines,starting%20from%20your%20cursor%20position.&text=y%5E%3A%20Copy%20everything%20from%20the,yiw%3A%20Copy%20the%20current%20word.

https://askubuntu.com/questions/1036030/e325-attention-swap-file-already-present-error-in-vi

https://superuser.com/questions/543354/swap-file-error-message-while-trying-to-edit-vimrc-file

https://www.baeldung.com/linux/vim-swap-files

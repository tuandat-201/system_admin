## Shell Linux

Shell là một chương trình cung cấp cho bạn một giao diện với hệ thống Unix. Nó nhận thông tin đầu vào từ người dùng và thực hiện tập lệnh của các chương trình máy tính dựa trên những thông tin ấy. Khi một chương trình kết thúc việc thực hiện tập lệnh, shell sẽ hiển thị kết quả đầu ra của chương trình đó.

Shell là môi trường mà chúng ta có thể chạy các lệnh, chương trình và script shell. Trong một shell có nhiều kiểu khác nhau, nó giống như việc các hệ điều hành có những kiểu riêng biệt. Mỗi kiểu của shell đều có một bộ lệnh và chức năng được xác định riêng.

### Các loại Shell

Trong Unix gồm có hai loại shell chính là Bourne shell và C shell. Bourne shell có dấu nhắc lệnh mặc định là ký tự “$”. Còn C shell sẽ có ký tự là “%”

Bourne shell có các danh mục phụ bao gồm:

- Bourne shell (sh)
- Korn shell (ksh)
- Bourne Again shell (bash)
- POSIX shell (sh)

Các danh mục phụ của C shell bao gồm:

- C shell (csh)
- TENEX/TOPS C shell (tcsh)

## Chức năng và cấu trúc của lệnh cd

Câu lệnh cd (viết tắt của Change Directory) cho phép user thay đổi thư mục làm việc hiện tại. Cấu trúc của câu lệnh đó như sau :

`cd [path]`

Trong đó, path là **đường dẫn tuyệt đối** hoặc **đường dẫn tương đối** đến thư mục.

### Phân biệt đường dẫn tương đối và đường dẫn tuyệt đối

**Đường dẫn tuyệt đối** của một tệp tin hay thư mục luôn bắt đầu bởi / (root) và tiếp theo sau đó là chuỗi các thư mục mà nó đi xuyên qua cho đến khi tới đích. Tóm lại, một đường dẫn tuyệt đối là đường dẫn bắt đầu bởi / (root)

**Đường dẫn tương đối** bắt đầu đi từ thư mục hiện tại. Một đường dẫn tương đối thường bắt đầu với tên của một thư mục hoặc tệp tin, kết hợp với các thư mục đặt biệt sau :

- Dấu . (dấu chấm), thư mục . là thư mục đặc biệt, liên kết (biểu thị) đến thư mục hiện thời (working directory).
- Dấu .. (hai chấm) liên kết (biểu thị) cho thư mục mẹ của thư mục hiện thời.
- Dấu ~ (dấu ngã) biểu thị thư mục cá nhân của người dùng hiện tại.

### Một số ví dụ :

Chuyển sang thư mục cá nhân của ngươi dùng hiện tại :

`cd ~ hoặc cd`

Chuyển sang thư mục gốc :

`cd /`

Chuyển về thư mục làm việc trước đó :

`cd ..`

## Chức năng và cú pháp của lệnh pwd

Lệnh pwd ghi vào đầu ra tiêu chuẩn tên đường dẫn đầy đủ của thư mục hiện tại (từ thư mục gốc). Tất cả các thư mục được phân tách bằng dấu / (dấu gạch chéo). Thư mục gốc được biểu thị bằng / đầu tiên và thư mục cuối cùng có tên là thư mục hiện tại .

Cú pháp :

`pwd`

### Ví dụ :

Nhập vào :

`pwd`

Kết quả :

`/home/datle201`

## Lệnh history

lệnh history sử dụng để hiển thị lịch sử câu lệnh đã thực thi tại user hiện hành

lệnh này dựa trên file `~/.bash_history`, mỗi lần reboot lại, file này sẽ được cập nhật.

### Cú pháp

```
history [option]
```

các option thường dùng :

- `-c` : Xoá toàn bộ lịch sử
- `-d` : Xoá lịch sử ở dòng cụ thể
- `-r` : Thêm dữ liệu trên file `.bash_history` vào history

### Cách dùng

Lặp lại câu lệnh gần nhất bằng câu lệnh `!!`

Lặp lại lệnh cụ thể bằng lệnh `![n]`, trong đó `n` vị trí trong lịch sử

### Sử dụng reverse-i search

1. Nhấn `Ctrl + R` để vào `reverse-i search`
2. Nhập vào câu lệnh muốn tìm
3. Nếu chưa khớp với lệnh mình muốn tìm. Tiếp tục bấm `Ctr + R` để đi đến kết quả tiếp theo
4. Khi tìm thấy kết quả mong muốn. Ấn `Enter` để thực thi. Hoặc ấn `Ctr + J` để nhập câu lệnh vào terminal nhưng không thực hiện

## Chức năng và cú pháp lệnh man

“Man” là từ viết tắt của “manual”, được coi là tài liệu trực tuyến trong Linux đã lưu trữ toàn bộ các lệnh có sẵn với các thông tin tham khảo khá đầy đủ cho phép người dùng có thể mở ra để nhận được trợ giúp.

Cú pháp :

`man [option] [command name]`

### Cấu trúc của một trang Man

- NAME : tên lệnh , khái quá tác dụng của lệnh
- SYNOPSIS : cú pháp của lệnh
- DESCRIPTION : mô tả cụ thể hơn về tác dụng của lệnh
- OPTIONS : liệt kê các tùy chọn lệnh và tác dụng của chúng
- FILES : liệt kê các file mà lệnh sử dụng hoặc tham chiếu đến
- SEE ALSO : liệt kê các lệnh, các tài liệu,…, có liên quan đến lệnh
- REPORTING BUGS : địa chỉ liên hệ nếu gặp lỗi khi sử dụng lệnh
- AUTHOR : tên tác giả của lệnh

## Chức năng và cú pháp lệnh cat

Lệnh Cat (viết tắt của “concatenate”) là một trong những lệnh được sử dụng thường xuyên nhất trong các hệ điều hành như Linux/Unix. Lệnh cat cho phép người dùng tạo một hoặc nhiều file, xem nội dung file, nối file và chuyển hướng đầu ra trong terminal hoặc file.

Cú pháp :

`cat [option] [file]`

### Ví dụ cụ thể

Xem toàn bộ nội dung của một file :

`cat file_name`

Xem toàn bộ nội dung của nhiều file :

`cat file_name1 file_name2`

Xem toàn bộ nội dung của một file với số dòng cụ thể :

`cat -n file_name`

Sao chép nội dung của file này sang file khác :

`cat file1.txt file2.txt > merged_file.txt`

Nối nội dung của file này vào cuối file khác :

`cat file_name1 >> file_name2`

## Lệnh tac

lệnh tac hiển thị toàn bộ nội dung của tệp tin, nhưng thay vì hiển thị từ đầu đến cuối tệp tin, lệnh này sẽ hiển thị theo thứ tự ngược lại

### Cú pháp

```
tac [options] file...
```

### Ví dụ

Có file `example.txt` sau :

```
1
2
3
```

Sử dụng lệnh tac để hiển thị nội dung của file :

```
3
2
1
```

## Lệnh sort

Lệnh sort được sử dụng trong Linux để in đầu ra của một file theo thứ tự nhất định

Theo mặc định, sort sẽ sắp xếp nội dung theo các tiêu chí sau:

- Các dòng bắt đầu bằng ký tự số có mức ưu tiên cao nhất.
- Sau đó, lệnh sẽ sắp xếp các dòng theo thứ tự bảng chữ cái
- Các dòng bắt đầu bằng ký tự thường đứng trước các dòng bắt đầu bằng cùng một ký tự đó nhưng viết hoa.

### Cú pháp

```
sort [option] <filename>
```

Các option thường dùng :

- `-r` : Đảo ngược thứ tự sắp xếp
- `-n` : Sắp xếp file chứa dữ liệu số
- `-k` : Sắp xếp theo cột
- `-u` : loại bỏ các giá trị trùng nhau

### Ví dụ

Ta có file `test.txt` sau :

```
Dr.B.R.Ambedkar
MahatmaJyotibaPhule
Budhha
ChatrapatiShahuMaharaj
budhha
Ramaai
```

1. Sắp xếp theo bảng chữ cái :

```
sort test.txt
// Kết quả
budhha
Budhha
ChatrapatiShahuMaharaj
Dr.B.R.Ambedkar
MahatmaJyotibaPhule
Ramaai
```

2. Sắp xếp ngược bảng chữ cái :

```
sort -r test.txt
// Kết quả
Ramaai
MahatmaJyotibaPhule
Dr.B.R.Ambedkar
ChatrapatiShahuMaharaj
Budhha
budhha
```

## Lệnh split

Lệnh split là một công cụ dòng lệnh phổ biến của Linux, được sử dụng để chia một tệp thành các tệp con nhỏ hơn. Theo mặc định, lệnh split tệp thành các phân đoạn 1000 dòng. Tệp gốc không thay đổi và một tập hợp các tệp mới có cùng tên cộng với tiền tố được thêm vào được tạo. Theo mặc định,tiền tố x được thêm vào (xaa,xab,xac,...)

### Cú pháp

```
split [OPTION]... [FILE] [PREFIX]
```

Các option thường dùng :

- `-l` : chia nhỏ dựa trên số lượng dòng
- `-b` : Chia nhỏ dựa trên kích thước
- `-n` : Chỉ nhỏ thành n số lượng chỉ định
- `-d` : Cho phép prefix là số thay vì chữ cái.

### Ví dụ

Để chia một tệp có tên “largefile.txt” thành nhiều tệp nhỏ, mỗi tệp có 100 dòng :

```
split -l 100 largefile.txt smallfile
```

Để chia nhỏ largefile.txt thành các tệp nhỏ hơn, có kích thước 300 byte mỗi tệp :

```
split -b 300 largefile.txt smallfile
```

Để chia một tệp lớn thành 5 phần bằng nhau :

```
split -n 5 largefile.txt smallfile
```

## Lệnh uniq

Lệnh uniq dùng để bỏ các dòng liên tiếp trùng lặp trong một tệp văn bản rất hữu ích để đơn giản hóa hiển thị văn bản.

Lệnh uniq yêu cầu các dòng trùng lặp phải liên tiếp, nên chúng ta thường chạy sắp xếp trước, sau đó mới chuyển đầu ra thành uniq.

### Cú pháp

```
uniq [option] [input] [output]
```

Các option thường dùng

- `-d` : hiển thị các giá trị bị trùng lặp, chỉ hiển thị 1 giá trị đại diện
- `-c` : điếm số lần lặp lại của từng giá trị
- `-u` : Chỉ in những giá trị mà không trùng lặp

### Ví dụ

Ta có file sau `example.txt` sau khi đã sắp xếp như sau:

```
I love music.
I love music.
I love music.
I love music of Kartik.
I love music of Kartik.
Thanks.
```

Lọc các giá trị trùng nhau :

```
uniq example.txt
// Kết quả
I love music.
I love music of Kartik.
Thanks.
```

Lấy những giá trị bị trùng lặp :

```
uniq -d example.txt
// Kết quả
I love music.
I love music of Kartik.
```

Điếm số lần lặp lại của từng giá trị :

```
uniq -c example.txt
// Kết quả
      3 I love music.
      2 I love music of Kartik.
      1 Thanks.
```

Chỉ in những giá trị mà không trùng lặp :

```
uniq -u  example.txt
// Kết quả
Thanks.
```

## Lệnh nl

Lệnh nl đánh số dòng cho tệp nhưng không tính dòng trống

### Cú pháp

```
nl [OPTION]... [FILE]...
```

Các option thường dùng :

- `-b a` : đánh số tất cả các dòng

### Ví dụ

Ta có file `greekfile.txt`
![](https://media.geeksforgeeks.org/wp-content/uploads/20201227110737/3.JPG)

Đánh số các dòng cho tệp nhưng không tính dòng trống
![](https://media.geeksforgeeks.org/wp-content/uploads/20201223231453/1.JPG)

Đánh số các dòng cho tệp tính cả dòng trống
![](https://media.geeksforgeeks.org/wp-content/uploads/20201227105351/5.JPG)

## Lệnh head

Lệnh head in ra những dòng đầu tiên trên file, mặc định là 10 dòng.

### Cú pháp

```
head [options] [file]
```

các option thường dùng :

- `-n` : Hiển thị n dòng đầu của file
- `-c` : Hiển thị số byte dữ liệu đầu tiên của file đầu

### Ví dụ

Để hiển thị 50 dòng đầu tiên :

```
head -n 50 filename.txt
```

Hiển thị 300 byte dữ liệu đầu tiên :

```
head -c 300 filename.txt
```

Hiển thị nhiều file cùng lúc :

```
head filename1.txt filename2.txt
```

## Lệnh tail

Cũng giống như head, lệnh tail xuất ra n số dữ liệu cuối cùng của đầu vào đã cho. Mặc định tail sẽ hiển thị 10 dòng cuối của file

### Cú pháp

```
tail [options] [file]
```

các option thường dùng :

- `-n` : Hiển thị n dòng cuối của file
- `-c` : Hiển thị số byte dữ liệu cuối của file đầu
- `-f` : Tiếp tục hiển thị nội dung cuối nếu file vẫn đang tiếp tục thay đổi

### Ví dụ

Để hiển thị 50 dòng cuối :

```
tail -n 50 filename.txt
```

Hiển thị 300 byte dữ liệu cuối :

```
tail -c 300 filename.txt
```

Hiển thị nhiều file cùng lúc :

```
tail filename1.txt filename2.txt
```

## Lệnh less

lệnh less cho phép xem nội dung của một tập tin và điều hướng qua tập tin đó, ngoài ra còn có thể tìm kiếm.

### Cú pháp

```
less file
```

### Cách sử dụng

Di chuyển :

- Phím điều hướng : cuộn lên xuống
- Phím Space : di chuyển xuống trang mới
- Phím b: di chuyển lên lại trang phía trên
- Phím g : Đi đến đầu tập tin
- Phím G : Đi đến cuối tập tin

Tìm kiếm :

- `/{pattern}` : Tìm kiếm xuôi
- `?{pattern}`: Tìm kiếm ngược
- Để chuyển đến kết quả tìm kiếm khác bấm phím n

Hiển thị số dòng :

- `-n` : Không hiển thị số dòng
- `-N` : Hiển thị số dòng

Thoát tệp hiện tại bấm phím q

## Lệnh cut

cut là một tiện ích dòng lệnh cho phép bạn cắt các phần của dòng từ các tệp hoặc dữ liệu được chỉ định và in kết quả ra đầu ra. Nó có thể được sử dụng để cắt các phần của một dòng theo dấu phân cách, vị trí byte và ký tự.

### Cú pháp

```
cut <option> <file>
```

Các option thường dùng :

- `-f` : Trích xuất theo một trường cụ thể, có thể lấy nhiều trường cách nhau bởi dấu `,` hoặc `-`
- `-b` : Cắt theo vị trí byte
- `-c` : Cắt theo vị trí ký tự
- `-d` : Chỉ định một dấu phân cách sẽ được sử dụng thay cho dấu phân cách “TAB” mặc định.

### Ví dụ :

1. Cắt mười sáu ký tự đầu tiên của mỗi dòng STDIN:

```
[root@test1 ~]# echo "This is a filetest" | cut -c 1-16
This is a filete
```

2. Cắt từ ký tự thứ 3 đến cuối mỗi dòng

```
[root@test1 ~]# cat file.txt
Roses are red, Violets are blue,
Sugar is sweet, And so are you.
[root@test1 ~]# cut -c 3- file.txt
ses are red, Violets are blue,
gar is sweet, And so are you.
```

3. Cắt trường thứ 1 của mỗi dòng trong file

```
[root@test1 ~]# cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
adm:x:3:4:adm:/var/adm:/sbin/nologin
lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin
[root@test1 ~]# cut -d':' -f1 /etc/passwd
root
bin
daemon
adm
lp
```

## Lệnh wc

Lệnh được sử dụng để đếm số dòng, số từ, số byte trong một tệp văn bản

### Cú pháp

```
wc [OPTON] [FILE]
```

Các option thường dùng :

- `-l`: In số dòng.
- `-w`: In số lượng từ.
- `-m`: In số ký tự.
- `-c`: In số byte.

### Ví dụ

Ta có file `state.txt` sau :

```
Andhra Pradesh
Arunachal Pradesh
Assam
Bihar
Chhattisgarh
```

1. Xem đầy đủ thông tin của lệnh wc

```
$ wc state.txt
// Kết quả
 5  7 58 state.txt
```

Trong đó :

- 5 : Số dòng
- 7 : Số từ
- 58 : Số byte
- state.txt : Tên file

2. Chỉ xem số dòng

```
$ wc -l state.txt
5 state.txt
```

3. Chỉ xem số từ

```
$ wc -w state.txt
7 state.txt
```

4. Chỉ xem số lượng ký tự

```
$ wc -m state.txt
56 state.txt
```

5. Chỉ xem số lượng byte

```
$ wc -c state.txt
58 state.txt
```

## Lệnh grep

Lệnh grep là lệnh tìm kiếm và trích xuất các chuỗi ký tự từ các tập tin, lệnh GREP rất hữu ích trong quá trình phân tích và xử lý dữ liệu trên Linux. Đặc biệt, lệnh GREP còn hỗ trợ các biểu thức chính quy (regular expressions) để tìm kiếm các chuỗi ký tự phức tạp hơn

### Cú pháp

```
grep [options] pattern [files]
```

Các option thường dùng

- `-i` : Không phân biệt chữ hoa chữ thường
- `-c` : Hiện thị số lượng dòng khớp với chuỗi tìm kiếm
- `-w` : Chỉ tìm chuỗi khớp với từ cần tìm, không tìm kiếm các từ chứa từ khóa đó
- `-E` : Tìm kiếm chuỗi sử dụng biểu thức chính quy
- `-n` : Hiển thị số thứ tự dòng chứa chuỗi kết quả

### Ví dụ

Tìm kiếm chuỗi “Hello” trong file `text.txt`

```
grep “Hello” text.txt
```

Tìm kiếm chuỗi "Hello" trong file `text.txt` mà không phân biệt chữ hoa, chữ thường

```
grep -i “Hello” text.txt
```

Tìm kiếm chuỗi "apple" trong file `fruits.txt` mà không chứa trong các từ khác như "pineapple" hay "applesauce"

```
grep -w “apple” fruits.txt
```

## Lênh Sed

Lệnh sed là công cụ xử lý văn bản mạnh mẽ và là một tiện ích UNIX lâu đời nhất và phổ biến nhất. Nó thường được dùng để tìm kiếm và thay thế văn bản.

### Cú pháp

```
sed [option] [command] [inputfile]
```

Trong đó :

- `option` : các tùy chọn
- `command` : các lệnh thực hiện trên tệp đầu vào, bao gồm các lệnh thay thế, chèn, xóa, cắt và sao chép dòng văn bản. Các lệnh được viết bằng các biểu thức chính quy (regex).
- `inputfile`: tên hoặc đường dẫn tới tệp cần xử lý bởi Sed. Nếu không có tên tệp được chỉ định, Sed sẽ đọc từ đầu vào tiêu chuẩn (stdin).

### Sử dụng sed thay thế chuỗi

Mặc định sed chỉ thay thế lần xuất hiện đầu tiên của mẫu trong mỗi file.

- Để thay thế tất cả các lần xuất hiện: `#sed "s/pattern/replace_string/g" file`
- Thay thế từ xuất hiện thứ N của mẫu đến cuối văn bản: `#sed "s/pattern/replace_string/Ng" file`
- Thay thế lần xuất hiện thứ N: `#sed "s/pattern/replace_string/N" file`

### Ví dụ

#### Thay thế một chuỗi được tìm thấy ở vị trí nhất định

```
# sed ‘s/before/after/2’ test.txt
```

Cờ /1, /2…có chức năng chỉ định vị trí tìm thấy chuỗi cần thay thế ở trên mỗi dòng.

Ví dụ ở lệnh trên, lệnh sẽ thực hiện thay thế chuỗi before ở vị trí thứ 2 mà nó tìm được ở trên mỗi dòng.

#### Thay thế một chuỗi được tìm thấy ở tất cả các dòng

```
# sed ‘s/before/after/g’ test.txt
```

Cờ “g” trong lệnh trên là viết tắt của global, ý chỉ lệnh sed sẽ tìm và thay thế chuỗi được tìm thấy ở tất cả các dòng.

Ví dụ ở lệnh trên, lệnh sẽ thực hiện thay thế tất cả chuỗi before tìm được ở tất cả các dòng thành after.

## Lệnh awk

awk là một ngôn ngữ lập trình giúp chúng ta thao tác dễ dàng với kiểu dữ liệu có cấu trúc và tạo ra những kết quả được định dạng

Lệnh awk sử dụng để tìm kiếm và xử lý file text. Nó có thể tìm kiếm một hoặc nhiều file để xem các file có dòng nào bao gồm những pattern cần tìm kiếm và sau đó thực hiện những action.

### Cú pháp

```
awk '/search-pattern/ { action-to-take-on-matches; another-action; }' file-to-parse
```

Trong đó :

- `/search-patterm/` : Là nội dung mẫu tìm kiếm.
- `action-to-take-on-matches` : Biểu thức xử lí nội dung.
- `;` : Dấu kết thúc biểu thức xử lí nội dung.
- `another-action` : Biểu thức xử lí nội dung khác.
- `file-to-parse` : Là tên tệp hoăc đường dẫn đến tệp.

### Sử dụng awk cơ bản qua ví dụ

Để hiểu hơn về awk, bây giờ chúng ta hãy tạo một tệp mẫu `hoadon.txt` có nội dung hiển thị là một hóa đơn bán hàng với danh sách là các loại quả mình yêu thích với nội dung như sau:

```
STT     Fruit   Amount  Price   Total amount
1       Cam     5       6000    30000
2       Xoài    6       30000   180000
3       Bưởi    7       40000   280000
4       Kiwi    4       60000   240000
5       Mận     10      20000   200000
```

In tệp `hoadon.txt` vừa tạo ở trên ra màn hình :

```
$ awk '{print}' hoadon.txt
// Kết quả :
STT     Fruit   Amount  Price   Total amount
1       Cam     5       6000    30000
2       Xoài    6       30000   180000
3       Bưởi    7       40000   280000
4       Kiwi    4       60000   240000
5       Mận     10      20000   200000
```

tìm kiếm một chuỗi nào đó trong tệp bằng lệnh :

```
$ awk '/Kiwi/' hoadon.txt
// Kết quả
4       Kiwi    4       60000   240000
```

hiển thị nội dung chúng ta tìm kiếm trên một cột bất kì khi sử dụng lệnh sau:

```
$ awk '/Xoài/ {print $4;}' hoadon.txt
//Kết quả
30000
```

Lệnh này sẽ thực hiện tìm kiếm dòng có chứa nội dung Xoài và in ra màn hình nội dung trường (cột) thứ thứ tư ($4) của dòng đó. Cho nên chúng ta nhìn thấy giá tiền của Xoài trong bảng hoadon.txt

## Tổng quan về vim

Vim là trình soạn thảo mã mạnh mẽ và linh hoạt nhất hiện có cho các hệ thống giống Unix. Nó là một phần mở rộng của trình soạn thảo Vi do Bill Joy phát triển. Vim có sẵn theo mặc định trên hầu hết các hệ thống Linux

### Các chế độ trong vim

| Chế độ  | Mô tả                                          |
| ------- | ---------------------------------------------- |
| Normal  | Mặc định; để điều hướng và chỉnh sửa đơn giản  |
| Insert  | Để chèn và sửa đổi văn bản rõ ràng             |
| Command | Đối với các hoạt động như saving, exiting, etc |
| Ex      | Mở rộng hơn so với Command mode                |

### Cách sử dụng cơ bản

#### Vào các chế độ

| Chế độ       | Mô tả                                                             |
| ------------ | ----------------------------------------------------------------- |
| Normal       | Mặc định khi vào, có thể dùng ESC để về chế độ này từ Insert Mode |
| Insert       | Thường dùng phím i                                                |
| Command mode | phím :                                                            |
| Ex           | Nhập gQ                                                           |

#### Điều hướng trong Normal mode

| Phím        | Mô tả                                      |
| ----------- | ------------------------------------------ |
| k           | Di chuyển con trỏ lên trên một dòng        |
| j           | Di chuyển con trỏ xuống một dòng           |
| l           | Di chuyển con trỏ sang phải theo một ký tự |
| h           | Di chuyển con trỏ sang trái bởi một ký tự  |
| ^ hoặc Home | Di chuyển con trỏ đến đầu dòng             |
| $ hoặc End  | Di chuyển con trỏ đến cuối dòng            |
| gg          | Di chuyển lên trên cùng                    |
| G           | Di chuyển tới cuối cùng                    |

#### Chèn văn bản

| Phím | Mô tả                                                  |
| ---- | ------------------------------------------------------ |
| i    | chèn văn bản tại vị trí con trỏ hiện tại               |
| a    | chèn văn bản một ký tự sau vị trí hiện tại của con trỏ |
| A    | chèn văn bản ở cuối dòng hiện tại                      |
| o    | chèn văn bản trên một dòng mới bên dưới dòng hiện tại  |
| O    | chèn văn bản trên một dòng mới phía trên dòng hiện tại |

#### Xóa văn bản

| Phím         | Mô tả                                             |
| ------------ | ------------------------------------------------- |
| x            | Xóa kí tự tại con trỏ                             |
| dw           | Xóa bắt đầu từ vị trí tại con trỏ đến cuối của từ |
| dEND hoặc d$ | Xóa từ vị trí hiện tại con trỏ đến cuối dòng      |
| dj           | Xóa dòng dưới                                     |
| dh           | Xóa dòng trên                                     |

#### Hoàn tác

| Phím  | Mô tả |
| ----- | ----- |
| u     | Undo  |
| Ctr r | Redo  |

#### Tìm kiếm và thay thế

| Phím                                  | Mô tả                            |
| ------------------------------------- | -------------------------------- |
| / + pattern                           | Tìm kiếm xuôi                    |
| ? + pattern                           | Tìm kiếm ngược                   |
| n                                     | Bỏ qua kết quả tìm kiếm hiện tại |
| N                                     | Trở về kết quả tìm kiếm trước    |
| s/<search_phrase>/<replace_phrase>/g  | Thay thế trong 1 dòng            |
| %s/<search_phrase>/<replace_phrase>/g | Thay thế trong toàn bộ           |

#### Các lệnh thường dùng trong Command mode

| Lệnh | Mô tả                |
| ---- | -------------------- |
| :w   | Lưu văn bản          |
| :wq  | Lưu và thoát văn bản |
| :q!  | Thoát không lưu      |

## Tổng quan về Byobu

Byobu là 1 trình hỗ trợ terminal. Nó mang đến nhiều chức năng hữu ích như chia đôi màn hình, mở tab nhanh,…

Khi ta cần phải ssh vào nhiều server, cần tạo nhiều sesion trên server đó. Tuy nhiên, khi đang dở việc mà phải tắt máy hay sập điện, các phiên SSH bị tắt đi thì coi như hết.

Khi đó, Byobu có thể giúp chúng ta điều đó. Ta có thể truy cập đến server mà không phải ssh nhiều lần. Khi công việc vẫn đang thực hiện, ta phải tắt máy thì Byobu vẫn chạy. Khi ta mở lại thì công việc vẫn được tiếp tục.

### Hướng dẫn sử dụng byobu

Một số phím tắt thường dùng để làm việc với byobu

| Phím tắt                     | Chức năng                                       |
| ---------------------------- | ----------------------------------------------- |
| Shift-F1                     | Hiển thị help                                   |
| F2                           | Tạo cửa sổ làm việc mới                         |
| Shift-F2                     | Chia ngang cửa sổ làm việc                      |
| Ctrl-F2                      | Chia dọc cửa sổ làm việc                        |
| Ctrl-Shift-F2                | Tạo session làm việc mới                        |
| Alt-Left/Right               | Chuyển đổi cửa sổ làm việc                      |
| Shift-F3/F4                  | Chuyển đổi màn hình làm việc (sau khi chia đôi) |
| Alt-Up/Down                  | Chuyển đổi session làm việc                     |
| Ctrl-F3/F4                   | Di chuyển màn hình làm việc (sau khi chia đôi)  |
| Ctrl-Shift-F3/F4             | Di chuyển cửa sổ làm việc                       |
| Shift-Alt-Left/Right/Up/Down | Thay đổi kích thước màn hình (Chia đôi)         |
| F6                           | Rời rời khỏi phiên                              |
| Ctr-F6                       | Dừng màn hình/window/session đang làm việc      |
| F8                           | Thay đổi tên cửa sổ đang làm việc               |
| Ctrl-F8                      | Thay đổi session đang làm việc                  |

## Lệnh ps

### Tổng quan

ps (hay Process Status) là một tiện ích của Unix/Linux dùng để xem thông tin của các tiến trình đang chạy trong hệ thống. Đây có thể nói là một tiện ích quan trọng các tiến trình, giúp bạn hiểu chuyện gì đang diễn ra trên hệ thống của bạn.

Tiện ích ps sẽ đọc thông tin tiến trình từ một file ảo nằm trong thư mục /proc. Nó sẽ cung cấp một số tuỳ chọn để cho bạn dễ dang xem thông tin của các tiến trình. Trong bài này mình sẽ giới thiệu một vài câu lệnh phổ biến.

### Cú pháp

```
ps [option]
```

Output của lệnh ps :
|Trường | Ý Nghĩa |
| ------------- | ------------- |
| PID | Process ID |
| TTY | Terminal liên quan tới tiến trình |
| TIME | Thời gian mà tiến trình sử dụng tài nguyên của CPU |

Một số option thường dùng :

- `-e` : Hiển thị tất cả tiến trình
- `-f` : Hiển thị đầy đủ thông tin hơn về tiến trình
- `-o` : Hiển thị những trường cụ thể
- `--forest` : Hiển thị tiến trình dưới dạng cây phân cấp
- `--sort` : Sắp xếp tiến trình

### Ý nghĩa một số trường thông tin

| Trường        | Ý Nghĩa                                           |
| ------------- | ------------------------------------------------- |
| CMD           | Câu lệnh thực thi tiến trình                      |
| %CPU          | Lượng cpu sử dụng                                 |
| %MEM          | Lượng Ram tiêu thụ                                |
| PID           | Mã tiến trình                                     |
| PPID          | Mã của tiến trình cha                             |
| UID           | Mã người dùng                                     |
| PRI           | Độ ưu tiên của tiến trình                         |
| RSS           | Lượng bộ nhớ sử dụng thực                         |
| VSZ / SZ      | Lượng bộ nhớ ảo sử dụng                           |
| S / STAT      | Chứa đoạn mã code mô tả trạng thái của tiến trình |
| Start / STIME | Thời gian mà câu lệnh đó khởi động                |

## Lệnh top

Lệnh top trong Linux được sử dụng để hiển thị tất cả các tiến trình đang chạy theo thời gian thực trong môi trường Linux

### Cú pháp

```
top [option]
```

Một số option thường dùng :

- `-d` - Chỉ định thời gian làm mới
- `-p` - Chỉ hiển thị các tiến trình được chỉ định
- `-u` - Chỉ hiển thị những tiến trình của người dùng được chỉ định

### Các thông số

![](https://camo.githubusercontent.com/abd2983f1854b063cfa2b1e45629804b5386369c890118748e04453c458515c0/68747470733a2f2f692e696d6775722e636f6d2f5a4c6e6668374e2e706e67)

1. **Dòng 1:** Thời gian của server

   <img src="https://i.imgur.com/WzcoouZ.png">

   - 1 : Thời gian hiện tại của hệ thống
   - 2 : Thời gian uptime
   - 3 : Số lượng user đang login
   - 4 : Thời gian CPU load trung bình trong 1 phút, 5 phút, 15 phút (số lượng process cần tài nguyên tính toán của CPU tại thời điểm nhất định)

2. **Dòng 2:** Thông tin các tiến trình

   <img src="https://i.imgur.com/4T2qJht.png">

   - 1 : Tổng số tiến trình đang ở trạng thái Active
   - 2 : Số tiến trình đang chạy
   - 3 : Số tiến trình đang ở chế độ Sleep
   - 4 : Số tiền trình đang ở trạng thái Stopped
   - 5 : Số lượng tác vụ zombie (tiến trình không tồn tại hoặc bị hỏng)

3. **Dòng 3:** Thông tin CPU

   <img src="https://i.imgur.com/mm6iSAn.png">

   - 1 : % CPU dùng cho từng tiến trình của user
   - 2 : % CPU dùng cho từng tiến trình của hệ thống
   - 3 : % CPU dùng cho các tiến trình có mức ưu tiên thấp (low-priority processes)
   - 4 : % CPU ở trạng thái nghỉ (idle process)
   - 5 : % CPU đang ở trong thời gian chờ I/O process
   - 6 : % CPU được dành cho phần cứng khi bị gián đoạn
   - 7 : % CPU được dành cho phần mềm khi bị gián đoạn
   - 8 : % CPU ảo chờ CPU thực xử lý các tiến trình

4. **Dòng 4:** Liên quan đến thông tin RAM

   <img src ="https://i.imgur.com/flsOUSr.png">

   - 1 : Tổng dung lượng RAM
   - 2 : Dung lượng RAM free
   - 3 : Dung lượng RAM đang được sử dụng
   - 4 : Dung lượng vào buffers

5. **Dòng 5:**

   <img src="https://i.imgur.com/6jYFyyW.png">

   - 1 : Dung lượng SWAP RAM
   - 2 : Dung lượng Swap RAM free
   - 3 : Dung lượng Swap RAM đã sử dụng
   - 4 : Bộ nhớ khả dụng

6. Bảng các tiến trình đang chạy
   <img src="https://i.imgur.com/tRVpRPO.png">

   - `PID` : ID Process
   - `USER` : User thực hiện tiến trình
   - `PR` : Độ ưu tiên của tiến trình
   - `NI` : Giá trị Nice Value (giá trị âm tăng độ ưu tiên của Process, giá trị dương giảm độ ưu tiên của Process)
   - `VIRT` : Dung lượng RAM ảo thực hiện tiến trình
   - `RES` : Dung lượng RAM thực sử dụng cho tiến trình
   - `SHR` : Dung lượng RAM share cho tiến trình.
   - `S` : Tình trạng process, có thể là: running (R), sleeping and unable to be interrupted (D), sleeping and able to be interrupted (S), traced/stopped (T), or zombie (Z)
   - `%CPU` : %CPU được sử dụng cho tiến trình
   - `%MEM` : %RAM được sử dụng cho tiến trình
   - `TIME+` : Thời gian tiến trình đã chạy
   - `COMMAND` : Tên hay lệnh thực hiện tiến trình

## Lệnh htop

Cũng giống như top, htop là một ứng dụng hoạt động trên Linux/Unix cho phép theo dõi các Process theo dạng tương tác thời gian thực (Real-Time)

### Cú pháp

```
htop [option]
```

Một số option thường dùng :

- `-d` : Thời gian delay giữa các lần refresh
- `-u` : chỉ hiện những process bởi người dùng chỉ định
- `-s` : Sắp xếp theo cột

### Các thông số

![](https://tailieu.tgs.com.vn/wp-content/uploads/2020/10/htop.png)

1. **Header**

![](https://tailieu.tgs.com.vn/wp-content/uploads/2020/10/htop1.png)

Phần bên trái biểu thị mức độ sử dụng CPU và RAM. Số lượng thanh tiến trình CPU tương ứng với số lượng CPU/Core của máy chủ. Ta sẽ thấy có nhiều màu sắc, mỗi màu có một ý nghĩa riêng

Đối với mức dùng CPU :

- Xanh lam: các tiến trình độ ưu tiên thấp
- Xanh lục: các tiến trình người dùng (user)
- Đỏ: các tiến hành hạt nhân (kernel)

Đối với mức dùng RAM :

- Xanh lục: bộ nhớ đã dùng
- Xanh dương: bộ nhớ đệm
- Vàng: bộ nhớ cache

Phía bên trái biểu thị các tiến trình đang chạy , Load average, thời gian hoạt động

2. **Body**

![](https://tailieu.tgs.com.vn/wp-content/uploads/2020/10/htop2.png)

Ý nghĩa thông số :

- `PID`: Số PID của tiến trình. Mỗi tiến trình sẽ có PID riêng
- `USER`: Chủ sở hữu tiến trình
- `PRI`: Độ ưu tiên của tiến trình. Số càng thấp thì mức độ ưu tiên càng cao
- `NI`: Giá trị nice value của tiến trình, ảnh hưởng đến độ ưu tiên của tiến trình đó
- `VIRT`: Bộ nhớ ảo đang được sử dụng cho tiến trình
- `RES`: Bộ nhớ RAM vậy lý đang được sử dụng, đo bằng kylobytes
- `SHR`: Bộ nhớ chia sẻ mà tiến trình đang sử dụng
- `S`: Trạng thái hiện tại của tiến trình (zombied, sleeping, running, uninterruptedly sleeping, traced)
- `% CPU`: Phần trăm tài nguyên CPU đang được tiến trình sử dụng
- `% MEM`: Phần trăm bộ nhớ RAM đang được tiến trình sử dụng
- `TIME`: Thời gian bộ xử lý mà tiến trình đã sử dụng
- `COMMAND`: Tên lệnh bắt đầu tiến trình

## Tìm kiếm PID của 1 process

Có thể sử dụng câu lệnh `pidof` hoặc `pgrep`

```
pidof <program>...
```

```
pgrep <program>
```

## Lệnh kill

Lệnh kill được sử dụng để dừng một tiến trình. Lệnh kill sẽ gửi một tín hiệu đến các tiến trình hoặc nhóm tiến trình được chỉ định (PID).

### Cú pháp :

```
kill [signal] pid...
```

Các tín hiệu được sử dụng phổ biến nhất là :

- 1 (HUP) – Khởi động lại tiến trình.
- 9 (KILL) – Dừng tiến trình ngay lập tức.
- 15 (TERM) – Dừng quá trình nhẹ nhàng hơn. Nếu không khai báo tín hiệu, thì đây sẽ là mặc định

### Sự khác nhau giữa kill -9 và kill -15

| kill -15 (Sigterm)                                                           | kill -9 (Sigkill)                                                                     |
| ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| yêu cầu tiến trình dừng hoạt động                                            | chấm dứt hoạt động của tiến trình ngay lập tức                                        |
| có thể được xử lý hoặc từ chối xử lý quá trình dừng hoạt động bởi tiến trình | tiến trình không có cơ hội ngăn chặn hay từ chối                                      |
| không dừng hoạt động của tiến trình con                                      | dừng hoạt động cả tiến trình cha và tiến trình con nếu có => Dễ tạo ra zombie process |

## Tổng quan về Package

### Khái niệm package

Package là một file chứa phần mềm mong muốn, cùng với tất cả các dependancy của phần mềm đó

### Khái niệm dependency

Dependency bao gồm các thư viện, package và modules cần cài đặt để ứng dụng có thể chạy và hoạt động

### Khái niệm binary package

là các package bao gồm tệp thực thi(có sẵn), được build từ mã nguồn và không thể đảo ngược(giấu mã nguồn và không thể thay đổi).

Các package trong repository có định dạng lưu trữ. Ví dụ, Debian sử dụng định dạng DEB để lưu trữ và phân phối chương trình.

### Khái niệm Repository

Repository là các kho lưu trữ tập chung chứa các phần mềm / package cần thiết và phổ biến cho các distro Linux khác nhau , mỗi distro có 1 repository riêng

## Tổng quan về package management

Trình quản lý gói là tập hợp những công cụ phần mềm tự động hóa quá trình cài đặt, cập nhật, định cấu hình và xóa ứng dụng trên Linux.

### Trình quản lý gói dpkg

Dpkg là một tiện ích cấp thấp bao gồm một tập hợp các lệnh được sử dụng để cài đặt, gỡ bỏ, liệt kê và quản lý các gói phần mềm trên các bản phân phối Linux dựa trên Debian.

Cài đặt cục bộ tệp Gói phần mềm Debian (.deb)là một trong những điểm đặc biệt của dpkg.

#### Cài đặt package

Trước khi ta có thể cài đặt các gói phần mềm trên máy tính của mình với dpkg, trước tiên, ta cần tải xuống gói phần mềm. Chúng ta có thể dễ dàng tải xuống các gói phần mềm bằng trình duyệt của mình hoặc thông qua các công cụ như wget hoặc curl.

Cú pháp :

```
dpkg --install/-i <package>
```

Ví dụ: để cài đặt Google Chrome, hãy tải nó xuống thư mục Downloads. Sau đó, chỉ cần chạy lệnh sau.

```
sudo dpkg --install ~/Downloads/google-chrome-stable_current_amd64.deb
```

**Lưu ý** : Khi ta cài đặt một gói với dpkg, hệ thống sẽ chỉ cài đặt gói đó. Tuy nhiên, một số gói cần phần mềm bổ sung được gọi là gói phụ thuộc (dependency) để hoạt động. Trong trường hợp này, dpkg có thể cảnh báo bạn bằng một thông báo lỗi.

#### Gỡ cài đặt package

Cú pháp :

```
dpkg --remove/-r <package>
```

#### Cập nhật thông tin về phiên bản mới của package trong repository

Để cập nhật trongthông tin về các phiên bản mới của package trong respository. Chúng ta cần sử dụng :

```
dpkg --update-avail
```

#### Liệt kê các package đã cài đặt

```
dpkg --list
```

### Trình quản lý gói APT

Lệnh apt (Advanced Package Tool) là một công cụ được sử dụng để quản lý các gói phần mềm trên các bản phân phối Linux thuộc dòng Ubuntu/Debian. Apt hoạt động giống như một công cụ quản lý gói hoàn chỉnh thông qua việc sử dụng dpkg.

#### Cập nhật thông tin về phiên bản mới của package trong repository

Để cập nhật thông tin về các phiên bản mới của package trong respository. Chúng ta cần sử dụng :

```
apt update
```

**Lưu ý** : Nó sẽ chỉ cập nhật thông tin về các phiên bản mới của package chứ không thực sự cập nhật packages.

#### Cập nhật package

Lệnh `apt update` được đề cập ở trên sẽ không cài đặt hoặc nâng cấp bất kỳ gói nào. Vì vậy, sau khi chạy lệnh trên, ta sẽ biết được các gói nào cần cập nhật.

Nếu muốn cập nhật toàn bộ các gói đã cài đặt lên phiên bản mới nhất, sử dụng lệnh :

```
apt upgrade
```

#### Cài đặt package

Cú pháp :

```
apt install <package>
```

#### Gỡ cài đặt package

Cú pháp :

```
apt remove <package>
```

#### Tìm kiếm packages

Cú pháp :

```
apt search <package>
```

#### Liệt kê các packages đã cài đặt

Cú pháp:

```
apt list --installed
```

## Startup Script

Ví dụ ta có script `reboot_message` sau :

```
#!/bin/sh
echo "Last reboot time: $(date)" > /etc/motd
```

Có thể sử dụng các cách sau để thiết lập Startup Script

### Sử dụng cron

Đầu tiên sử dụng lệnh sau để chỉnh sửa crontab

```
crontab -e
```

Rồi sau đó thêm dòng sau vào crontab file

```
@reboot sh /home/ec2-user/reboot_message.sh
```

### Sử dụng systemd

Có thể tạo file với đuôi .service tại `/etc/systemd/system`

```
[Unit]
Description=Reboot message systemd service.

[Service]
Type=simple
ExecStart=/bin/bash /home/ec2-user/reboot_message.sh

[Install]
WantedBy=multi-user.target
```

Để có thể chạy khi hệ thống khởi động

```
chmod 644 /etc/systemd/system/reboot_message.service
systemctl enable reboot_message.service
```

## Tổng quan về filesystem

File System hay hệ thống tệp là phương pháp cấu trúc dữ liệu mà các hệ điều hành sử dụng để quản lý,tổ chức và lưu trữ dữ liệu,các tệp tin trên ổ đĩa

### Các loại filesystem phổ biến

#### ext - extended file system

- Là định dạng file hệ thống đầu tiên được thiết kế dành riêng cho Linux .
- Là phần nâng cấp từ file hệ thống **Minix** .
- Không nên sử dụng `ext` vì có nhiều hạn chế , không còn được hỗ trợ trên nhiều distribution.

#### ext2

- Thực chất không phải là file hệ thống **_journaling_** , được phát triển để kế thừa các thuộc tính của file system cũ .
- Ext2 không sử dụng **_journal_** cho nên sẽ có ít dữ liệu được ghi vào ổ đĩa hơn .
- Hỗ trợ partition size lên đến `2-32TiB`
- Hỗ trợ file size lên đến `16GiB-2TiB`
- Có thể chứa tối đa 10<sup>18</sup> file trong 1 volume .
- Độ dài tên file tối đa là `255` kí tự .

#### ext3

- Là `ext2` đi kèm với **_journaling_** .
- Mục đích chính của `ext3` là tương thích ngược với `ext2` , và do vậy những ổ đĩa, phân vùng có thể dễ dàng được chuyển đổi giữa 2 chế độ mà không cần phải format như trước kia .
- `Ext3` là hoạt động nhanh , ổn định hơn rất nhiều .
- Không thực sự phù hợp để làm file system dành cho máy chủ bởi vì không hỗ trợ tính năng tạo **disk snapshot** và file được khôi phục sẽ rất khó để xóa bỏ sau này .
- Hỗ trợ partition size lên đến `4-32 TiB`
- Hỗ trợ file size lên đến `16GiB-2TiB`
- Độ dài tên file tối đa là `255` kí tự .

#### ext4

- File system này ra đời từ phiên bản `2.6.28` của Linux kernel ( 25-12-2008 )
- Nó kế thừa và phát huy các điểm mạnh của `ext3` , đồng thời `ext4` có thể giảm bớt hiện tượng phân mảnh dữ liệu trong ổ cứng , hỗ trợ file system và file có dung lượng lớn và có tốc độ hoạt động nhanh .
- Hỗ trợ partition size lên đến `1 EiB`
- Hỗ trợ file size lên đến `16 TiB`
- Có thể chứa tối đa `4 tỷ` file trong 1 partition .
- Độ dài tên file tối đa là `255` kí tự .

#### xfs

- Đây là **file system** mặc định trên CentOS 7
- Được phát triển bởi **_Silicon Graphics_** từ nằm 1993
- Có các đặc điểm :
  - Hạn chế được tình trạng phân mảnh dữ liệu
  - Hỗ trợ partition size lên đến `8 exbibytes`
  - Hỗ trợ file size lên đến `8 exbibytes`
  - Có thể chứa tối đa 2<sup>64</sup> file trong 1 volume .
  - Độ dài tên file tối đa là `255` kí tự .
  - Cấu trúc thư mục theo dạng **B+ trees**

## Tổng quan về lệnh fsck

Lệnh fsck là một công cụ dòng lệnh được sử dụng để kiểm tra tính nhất quán của filesystem tự động trong quá trình khởi động hoặc chạy thủ công.

Có những tình huống khác nhau khi ta muốn chạy fsck. Dưới đây là một số ví dụ:

- Hệ thống không khởi động được.
- Các tệp trên hệ thống bị hỏng (thường thấy lỗi đầu vào/đầu ra).
- Ổ đĩa kết nối (bao gồm ổ flash/thẻ SD) không hoạt động như mong đợi.

Cú pháp :

```
fsck [option] <filesystem>
```

nếu không có option thì sẽ chỉ trả về tình trạng của filesystems

Các option thường dùng :

- `-r` : để người dùng tự chọn cách sửa (Hỏi để xác nhận).
- `-a` : tự động sửa mà không hỏi gì cả.

## Lệnh df

### Chức năng của câu lệnh df

Lệnh “df” nghĩa là “disk filesystem”, nó được sử dụng để hiển thị tóm tắt đầy đủ về việc sử dụng không gian đĩa cứng còn sẵn và được sử dụng của hệ thống tập tin (filesystems) trên hệ thống Linux.

### Cú pháp lệnh df

```
df [option] [file]
```

Một số option cơ bản :

- `-a` : Hiển thị thông tin của tất cả dung lượng đĩa đã sử dụng
- `-h` : Hiển thị mức sử dụng dung lượng ổ cứng theo định dạng dễ đọc
- `-T` : Hiển thị các loại file system

## Lệnh du

### Chức năng của lệnh du

du là một công cụ dòng lệnh được cung cấp với Linux, nhằm báo cáo dung lượng ổ đĩa được sử dụng bởi các thư mục và file. du là viết tắt của từ “disk usage”. Đây là công cụ chính để phân tích không gian ổ đĩa trong dòng lệnh.

### Cú pháp của lệnh du

```
du [options] [directory/file]...
```

Một số option thường được sử dụng :

- `-a` : hiển thị toàn bộ thông tin về file và thư mục, bao gồm cả các mục bị ẩn
- `-h` : hiển thị dưới dạng kb, mb, gb
- `-c` : hiển thị tổng dung lượng ổ đĩa sử dụng bởi các thư mục đã quét
- `-s` : hiển thị tóm tắt tổng dung lượng ổ đĩa được sử dụng bởi các thư mục đã quét

### So sánh du vs df

Lệnh df đưa ra tóm tắt đầy đủ về việc sử dụng không gian đĩa cứng đã được sử dụng và còn sẵn của hệ thông tập tin trên Linux. Lệnh du thì tập trung vào việc ước tính không gian đĩa cứng được sử dụng của từng thư mục hoặc tệp tiêng lẻ.

## Tổng quan về lệnh mkfs

Lệnh mkfs là một lệnh trong hệ điều hành Linux được sử dụng để tạo hệ thống tệp (filesystem) trên một thiết bị lưu trữ như ổ cứng, ổ đĩa USB, hoặc phân vùng. Cụ thể, mkfs được sử dụng để định dạng (format) thiết bị để tạo ra các cấu trúc dữ liệu cần thiết để lưu trữ các tệp và thư mục trên đó.

### Cú pháp

```
mkfs -t <filesystem_type> <device>
```

Hoặc

```
mkfs.<filesystem_type> <device>
```

Trong đó :

- `filesystem_type` là loại hệ thống tệp ta muốn tạo, ví dụ: ext4, ext3, xfs, vfat, ntfs, và nhiều loại khác.
- `device` là thiết bị lưu trữ ta muốn tạo hệ thống tệp trên, thường là đường dẫn đến thiết bị như `/dev/sda1` hoặc `/dev/sdb`.

## Tổng quan về mount/unmount

Trên Linux để có thể truy cập/sử dụng các thiết bị như USB, đĩa CD/DVD, file ISO, phân vùng ổ cứng, các tài nguyên được chia sẻ qua mạng (gọi chung là thiết bị)… thì trước hết các thiết bị này các được gắn kết (mount) vào 1 thư mục trống (gọi là mount point). Và khi muốn tháo gỡ thiết bị đang hoạt động khỏi hệ thống thì bạn phải ngắt kết nối (unmount) giữa thiết bị với mount point trước đó.

### Mount

#### Mount thủ công

Với cách mount này thì khi ta reboot lại thì ta phải tiến hành mount lại

Cú pháp :

```
mount -t [type] <device_path> <mount_point>
```

Trong đó :

- `type` : ext2, ext3, ext4, reiserFS, swap, FAT32, NTFS, auto,... Nếu thiết bị đã được định dạng từ trước thì ta có thể bỏ qua option này.
- `device_path` : thiết bị ta muốn tiến hành mount. Các thiết bị thường nằm trong /dev
- `mount_point`: thư mục ta muốn tiến hành gắn thiết bị vào

VD : Ta muốn tiến hành mount phân vùng /dev/sdb2 của ổ sdb vào thư mục /test

```
mount -t /dev/sdb2 /test
```

Sau khi mount xong ta có thể dùng lệnh lsblk để thấy được thiết bị đó đã có điểm mount.

```
lsblk
```

#### Mount tự động

Khi ta thực hiện mount kiểu này xong thì mỗi lần ta reboot ta không cần mount lại nữa vì nó sẽ tự động mount cho ta.

Để có thể mout tự động thì ta cần phải vào file `/etc/fstab` để thêm thiết bị cần mount vào file này. Sau khi máy khởi động nó sẽ tự động đọc file này và mount những gì được ghi ở trong file.

Cấu trúc file `/etc/fstab` :
![](https://linuxhint.com/wp-content/uploads/2022/12/Introduction-to-the-Linux-4.png)

Trong đó :

- Cột 1 : Lưu tên thiết bị (UUID) hoặc đường dẫn tới file thiết bị trong thư mục `/dev`. Để biết UUID của thiết bị ta có thể dùng lệnh `blkid`
- Cột 2 : Cho biết điểm mount
- Cột 3 : Cho biết định dạng file system của thiết bị (ext2,ext3,ext4,xfs..)
- Cột 4 : Các tùy chọn. Nếu có nhiều tùy chọn thì chúng được phân biệt bởi dấu `,`
  - Mặc định là `defaults`: tương ứng với tập các tùy chọn rw, suid,dev, exec, auto, nouser, async.
  - `auto`:tự động mount khi máy tính khởi động
  - `noauto`:phải tự chạy lệnh mount sau khi reboot
  - `user` cho phép người dùng thông thường được quyền mount
  - `nouser`: chỉ có root mới có quyền mount
  - `exec`: cho phép chạy các file nhị phân (binary) trên thiết bị.
  - `noexec`: không cho phép chạy file binary trên thiết bị.
  - `ro`: read only chỉ cho phép quyền đọc trên thiết bị.
  - `rw`: cho phép cả đọc và ghi trên thiết bị.
  - `sync`: thao tác nhập xuất (I/O) trên filesystem được đồng bộ hóa.
  - `async`: thao tác nhập xuất (I/O) trên filesystem diễn ra không đồng bộ.
- Cột 5: Là tùy chọn cho chương trình sao lưu filesystem.
  - Để **0** nếu muốn bỏ qua việc sao lưu.
  - Để **1** nếu muốn thực hiện việc sao lưu.
- Cột 6: Là tùy chọn cho chương trình fsck dò lỗi trên filesystem.
  - Để **0**: bỏ qua việc kiểm tra.
  - Để **1**: thực hiện việc kiểm tra.

### Unmount

Khi không dùng ta có ngắt kết nối thiết bị với thư mục bằng cách dùng lệnh:

```
umount <device_path/mount_point>
```

## Partition

Partition là những phân vùng nhỏ (phân vùng logic) được chia ra từ 1 ổ cứng vật lý. Một ổ cứng có thể có 1 hoặc nhiều partition. Partition là cách phân chia và quản lý một ổ cứng đơn giản và hiệu quả (chẳng hạn như phân ra 1 vùng quan trọng để chứa dữ liệu của hệ điều hành và 1 phân vùng để chứa phim, nhạc).

### Quản lý partition với fdisk

`fdisk` là tiện ích quản lý partition đĩa cứng trên Linux. Sử dụng fdisk, bạn có thể xem, tạo, thay đổi kích thước, xóa, thay đổi, sao chép và di chuyển các partition.

#### Xem các partition hiện có

```
sudo fdisk -l
```

Đầu ra :

![](https://funix.edu.vn/wp-content/uploads/2022/03/1-29.png)

#### Vào và sử dụng chế độ lệnh (command mode)

```
sudo fdisk [device]
```

Sau đó sẽ hiển thị :

```
[root@localhost ~]# fdisk /dev/sdb
Welcome to fdisk (util-linux 2.23.2).

Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.

Device does not contain a recognized partition table
Building a new DOS disklabel with disk identifier 0x36c2f72f.
```

Nhập m để xem danh sách tất cả các lệnh có sẵn của fdisk có thể được sử dụng trên /dev/sdb.

```
Command (m for help): m
```

#### Tạo phân vùng mới

Khi đang trong chế độ command mode, sau đó hãy nhập `n` và nhấn `Enter`. Khi đã hoàn thành việc đó, fdisk sẽ hỏi loại phân vùng nào bạn muốn tạo , nhập `p` cho phân vùng chính hoặc `e` cho phân vùng mở rộng.

```
Command (m for help): n
Partition type:
   p   primary (0 primary, 0 extended, 4 free)
   e   extended
Select (default p): p
```

Sau đó, ta sẽ được nhắc nhập số của phân vùng sẽ được tạo. Có thể nhấn Enter để chấp nhận mặc định.

```
Partition number (1-4, default 1): 1
```

Sau đó, ta sẽ được nhắc nhập kích thước của phân vùng sẽ được tạo ví dụ dưới chúng ta sẽ tạo đĩa với size 5GB. Có thể nhấn Enter để sử dụng tất cả không gian có sẵn.

```
First sector (2048-33554431, default 2048): 2048
Last sector, +sectors or +size{K,M,G} (2048-33554431, default 33554431): 10002400
Partition 1 of type Linux and of size 4 MiB is set
```

Cuối cùng, chạy lệnh w để lưu các thay đổi.

```
Command (m for help): w
The partition table has been altered!

Calling ioctl() to re-read partition table.
Syncing disks.
```

#### Xóa phân vùng

Khi đang trong chế độ command mode, sau đó hãy nhập `d` và nhấn `Enter`. Ta sẽ được nhắc nhở để nhập số phân vùng trường hợp này chúng ta nhập 2 để xóa `/dev/sdb2`. Lưu các thay đổi bằng cách nhập `w`.

```
Command (m for help): d
Partition number (1,2, default 2): 2
Partition 2 is deleted

Command (m for help): w
The partition table has been altered!

Calling ioctl() to re-read partition table.
Syncing disks.
```

## RAID là gì ?

RAID là viết tắt của Redundant Arrays of Independent Disks (Hệ thống đĩa dự phòng). Ban đầu RAID được sử dụng như một giải pháp phòng hộ vì nó cho phép ghi dữ liệu lên nhiều đĩa cứng cùng lúc. Về sau, RAID đã có nhiều biến thể cho phép không chỉ đảm bảo an toàn dữ liệu mà còn giúp gia tăng đáng kể tốc độ truy xuất dữ liệu từ đĩa cứng.

### Một số thuật ngữ của RAID

- **Striping** : Tách luồng dữ liệu thành các khối có kích thước nhất định (được gọi là kích thước khối) sau đó viết từng khối này qua từng RAID
- **Mirroring** : là kỹ thuật lưu trữ các bản sao dữ liệu giống hệt nhau được lưu trữ trên các thành viên RAID cùng một lúc
- **Parity** : là một kỹ thuật lưu trữ được sử dụng các phương pháp phân loại và tổng kiểm tra. Trong kỹ thuật chẵn lẻ, một hàm chẵn lẻ nhất định được tính cho các khối dữ liệu. Nếu một ổ đĩa bị lỗi, khối bị thiếu được tính toán lại từ tổng kiểm tra, cung cấp khả năng chịu lỗi RAID.

### Phân loại RAID

#### RAID 0

RAID 0 – dựa trên kỹ thuật striping. Mức RAID này không cung cấp khả năng chịu lỗi nhưng tăng hiệu năng hệ thống (tốc độ đọc và ghi cao). RAID 0 cần ít nhất 2 ổ đĩa. Tổng quát ta có n đĩa (n>=2) và các đĩa là cùng loại. Dữ liệu sẽ được chia ra thành nhiều phần bằng nhau. Ví dụ có 2 ổ cứng 80GB thì hệ thống ổ đĩa sẽ là 160GB.

![](https://static-xf1.vietnix.vn/wp-content/uploads/2021/07/raid-0.webp)

Tổng quan :

- **Ưu điểm** : Tăng tốc độ đọc/ghi ổ đĩa, mỗi đĩa chỉ cần đọc/ghi 1/n lượng dữ liệu yêu cầu.
- **Nhược điểm** : Tính an toàn thấp vì nếu một đĩa hư thì dữ liệu trên tất cả các đĩa còn lại sẽ không còn sử dụng được.

#### RAID 1

RAID 1 – sử dụng kỹ thuật mirroring. Và cung cấp khả năng chịu lỗi khi mất không quá một đĩa thành viên. Đây là RAID cơ bản nhất có khả năng đảm bảo an toàn dữ liệu. Cũng giống như RAID 0, thì RAID 1 cũng yêu cầu 2 ổ đĩa cứng để làm việc. Dữ liệu sẽ được ghi vào 2 ổ đĩa giống nhau (Mirroring) và nếu một ổ đĩa gặp trục trặc thì ổ đĩa còn lại vẫn làm việc và hoạt động bình thường.

Người dùng có thể thay thế ổ đĩa bị hỏng mà không cần quá lo lắng đến vấn đề thông tin bị mất.Dung lượng cuối cùng của hệ thống RAID 1 sẽ bằng dung lượng của ổ đơn.

![](https://static-xf1.vietnix.vn/wp-content/uploads/2021/07/raid-1.webp)

Tổng quan :

- **Ưu điểm** : Trong trường hợp một ổ đĩa bị lỗi, dữ liệu không cần phải được xây dựng lại. Chỉ cần sao chép chúng vào ổ đĩa drive thay thế.
- **Nhược điểm** : Hiệu suất không cao, dung lượng lưu trữ hiệu quả chỉ bằng một nửa tổng dung lượng drive. Vì tất cả dữ liệu đều được ghi hai lần.

#### RAID 5

RAID 5 – sử dụng cả kỹ thuật phân stripe và parity. Cung cấp cải thiện tốc độ đọc như trong RAID 0 xấp xỉ, tồn tại khi mất một đĩa thành viên RAID. Có cơ chế khôi phục dũ liệu, các parity dùng để khôi phục dữ liệu được phân bổ đều trên tất cả các ổ cứng. RAID 5 yêu cầu tối thiểu 3 ổ cứng.

![](https://github.com/nhanhoadocs/thuctapsinh/raw/master/HienNT/Linux/images/raid/DefenselessDeficientBelugawhale-mobile.gif)

Giả sử có 8 đoạn dữ liệu và 3 ổ đĩa: Đoạn dữ liệu số 1 và số 2 sẽ được ghi vào ổ đĩa 1 và 2 riêng rẽ, đoạn sao lưu của chúng được ghi vào ổ cứng 3. Đoạn số 3 và 4 được ghi vào ổ 1 và 3 với đoạn sao lưu tương ứng ghi vào ổ đĩa 2. Đoạn số 5, 6 ghi vào ổ đĩa 2 và 3, còn đoạn sao lưu được ghi vào ổ đĩa 1 và sau đó trình tự này lặp lại, đoạn số 7,8 được ghi vào ổ 1, 2 và đoạn sao lưu ghi vào ổ 3 như ban đầu.

Dung lượng cuối cùng RAID 5 được tính: (Dung lượng 1 ổ cứng) x [(Số lượng ổ cứng tham gia) – 1

Tổng quan :

- **Ưu điểm** : Nâng cao hiệu suất, an toàn dữ liệu
- **Nhược điểm** : Giá thành cao

### Cấu hình RAID bằng lệnh mdadm

Lệnh mdadm trong Linux được sử dụng để quản lý và giám sát Sofware RAID. Đây là một công cụ mạnh mẽ có thể giúp tạo, quản lý và khắc phục sự cố RAID

#### Cú pháp

```
mdadm --[action] /dev/mdX --level=<RAID LEVEL> --raid-devices=<NUMBER OF DEVICES> <DEVICE1> <DEVICE2>...
```

#### Ví dụ :

Ở đây ta sẽ thực hành tạo RAID 0 :

```
mdadm --create /dev/md0 --level=0 --raid-devices=2 /dev/sda1 /dev/sdb1
```

Để kiểm tra RAID vừa tạo tập tin `/proc/mdstat`

```
cat /proc/mdstat
```

Để giám sát RAID :

```
mdadm --detail /dev/md0
```

## Filesystem Hierarchy Standard

Filesystem của hệ điều hành Linux được tổ chức theo tiêu chuẩn cấp bậc của hệ thống tập tin Filesystem Hierarchy Standard (FHS). Tiêu chuẩn này định nghĩa mục đích của mỗi thư mục.

### Sơ đồ minh họa FHS

![](https://github.com/nhanhoadocs/thuctapsinh/raw/master/HienNT/Linux/images/filesystem/filesystem-2.png)

Giống như các hệ thống Unix-like, thì các distro Linux cũng có các file và thư mục được đặt ở bên trong một thư mục gốc có đường dẫn là `/`. Ngay phía dưới thư mục gốc, sẽ có những thư mục như sau:

- **`bin`** : chứa những file binaries, tức những command cơ bản và thiết yếu của hệ thống
- **`boot`** : chứa Linux Kernel và tất cả các files cần thiết cho quá trình boot hệ thống
- **`dev`** : chứa các tập tin thiết bị (device files), ví dụ : CDRom, HDD, FDD…
- **`etc`** : chứa file config của những phần mềm thuộc hê thống.
- **`home`** : chứa các file, cũng như personal settings của từng người dùng khác root
- **`lib`** : chứa các thư viện dùng chung cho các lệnh nằm trong /bin và /sbin. Và thư mục này cũng chứa các module của kernel.
- **`media`** : điểm truy nhập (mount) cho các thiết bị rời (CD-ROM,floppy,..)
- **`mnt`** : điểm truy nhập (mount) tạm thời
- **`opt`** : chứa các ứng dụng bổ sung do bên thứ ba cung cấp
- **`proc`** : là thư mục chứa các process đang chạy hay thông tin về kernel ở dạng files
- **`root`** : đây là thư mục home cho user root của hệ thống
- **`sbin`** : chứa các file binary command của hệ thống, và có thể được thực thi ở Singer User Mode (Maintenance Mode). Các command thường là dành cho superuser, tức cần đến quyền root để thực thi.
- **`srv`** : chứa dữ liệu được sử dụng bởi các máy chủ lưu trữ trên hệ thống.
- **`tmp`** : chứa các file tạm thời, thư mục này thường được làm mới mỗi khi khởi động lại
- **`usr`** : Thư mục chứa những file cố định hoặc quan trọng, chẳng hạn như ứng dụng và thư viện hệ thống để phục vụ tất cả người dùng.
- **`var`** : Chứa dữ liệu biến đổi thường xuyên trong quá trình chạy hệ thống, chẳng hạn như log, thư mục tạm thời và các dữ liệu của các ứng dụng.
- **`var`** : Chứa dữ liệu biến đổi thường xuyên trong quá trình chạy hệ thống, chẳng hạn như log, thư mục tạm thời và các dữ liệu của các ứng dụng.

## Lệnh ls

Lệnh ls cho phép người dùng liệt kê các file và thư mục , ngoài ra còn có thể liệt kê các quyền,tên của user và group sở hữu, ngày giờ sửa đổi của tệp/thư mục.

### Cú pháp

```
ls [option] [dir]
```

Các tùy chọn thường dùng :

- `-a` : Liệt kê tất cả thư mục và file , kể cả các mục bị ẩn
- `-l` : Hiển thị đầy đủ thông tin
- `-x` : Sắp xếp đầu ra theo bảng chữ cái
- `-h` : thường sử dụng kèm với `-h`, sẽ hiển thị kích thước file/thư mục dưới dạng KB,MB,GB
- `-R` : Hiển tị danh sách cây thư mục, chỉ ra đường dẫn của từng thư mục

## Lệnh cp

Lệnh cp là một tiện ích dòng lệnh cho các hệ thống Unix và Linux có khả năng sao chép cả file và thư mục, cp có sẵn trên hầu hết mọi bản phân phối Linux.

### Cú pháp

```
cp [options] <source>... <destination>
```

Các tùy chọn thường dùng :

- `-R` : Copy thư mục và toàn bộ nội dung của nó
- `-v` : Hiển thị chi tiết hơn về quá trình copy
- `-p` : Copy nhưng vẫn giữ lại các thuộc tính thông tin của file được copy

Lệnh cp có thể chứa nhiều nguồn, nhưng chỉ có thể có một đích. Đích đến có thể là một thư mục khác, một tên file mới hoặc cả hai.

## Lệnh mv

Lệnh mv (viết tắt của move) được sử dụng để đổi tên và di chuyển các file và thư mục từ vị trí này sang vị trí khác

### Cú pháp

```
mv [option] <source> <destination>
```

Các tùy chọn thường dùng :

- `-v` : Hiển thị chi tiết hơn về quá trình di chuyển/đổi tên
- `-n` : Tránh ghi đè vào file đã tồn tại
- `-i` : Hỏi trước khi ghi đè tập tin

## Lệnh rm

rm được viết tắt từ remove, lệnh này dùng để xóa các đối tượng như tệp, liên kết, thư mục, … khỏi hệ thống như Linux hay Unix. Mặc định lệnh rm sẽ không xóa các thư mục cho đến khi ta cho phép bằng các tùy chọn mà nó hỗ trợ

### Cú pháp

```
rm [option] <file>...
```

Các tùy chọn thường dùng :

- `-i` : Hỏi trước khi xóa tập tin
- `-f` : Xóa tập tin được bảo vệ mà không đưa ra xác nhận
- `-d` : Xóa thư mục không có dữ liệu
- `-r` : Xóa thư mục và tất cả dữ liệu bên trong

## Lệnh touch

Lệnh Touch Linux được dùng để tạo file trống, đổi timestampts của files và folders.

Lệnh touch mà không có option nào sẽ tạo một file. Nếu file đã tồn tại, lệnh touch sẽ cập nhật thời gian truy cập và chỉnh sửa đến thời gian hiện tại mà không thay đổi nội dung của nó

### Cú pháp

```
touch [options] [file_name]
```

Các tùy chọn thường dùng :

- `-a` : Đổi thời gian truy cập (Access time)
- `-m` : Đổi thời gian chỉnh sửa (Modification time)

## Lệnh ln

Lệnh Ln trong Linux cho phép người dùng tạo liên kết giữa các tệp và thư mục. Lệnh Ln mặc định sẽ tạo ra các liên kết cứng. Để tạo liên kết tượng trưng, hãy sử dụng tùy chọn -s (–symbolic).

### Các loại link trên Linux

Trên Linux, chúng ta có hai loại links như sau:

- **Hard links**: có thể hiểu hard link là một cái tên mới bổ sung cho một file nào đó.Ta có thể tạo một hoặc nhiều hard link cho một file, và không thể tạo cho các file nằm trên các phân vùng khác nhau.
- **Soft links(Symbolic Links)**: Nó giống như là shortcut trên Windows vậy đó. Khi mở một biểu tượng shortcut trên Windows thì nó sẽ tự liên kết tới phần mềm và chạy. Với cách này thì ta có thể liên kết đến các file nằm nhiều phân vùng khác nhau.

![](https://tecadmin.net/wp-content/uploads/2013/03/hard-links-vs-soft-links.png)

### Cú pháp để tạo Symbolic Links

```
ln -s [OPTIONS] FILE LINK
```

Trong đó:

- Nếu cả hai tham số FILE và LINK đều được cung cấp trong lệnh trên thì Linux sẽ tạo một symlink có tên là LINK và trỏ tới FILE.
- Nếu chỉ cung cấp cho tham số FILE hoặc tham số LINK là dấu chấm thì Linux sẽ tạo một symlink có tên là thư mục hiện tại và trỏ đến file.

### Xóa symlink trên Linux

Để xóa symlink trên Linux thì ta sử dụng lệnh unlink hoặc rm.

```
unlink symlink_to_remove
```

```
rm symlink_to_remove
```

## File Permissions

### Quyền truy xuất

- Quyền truy xuất trên file và thư mục được trình bày khi thực hiện lệnh `ls -l`

    <img src=https://i.imgur.com/MudtSDu.png>

- Danh sách quyền truy xuất trình bày ở cột đầu tiên của kết quả . Các loại quyền truy xuất gồm :
  - **Read ( r ) :** cho phép đọc nội dung tập tin và xem nội dung của thư mục bằng lệnh
  - **Write ( w ) :** cho phép thay đổi nội dung hoặc xóa tập tin . Đối với thư mục , quyền này cho phép tạo , xóa hoặc đổi tên mà không phụ thuộc quyền sở hữu của thư mục chứa mình .
  - **Execute ( x ) :** cho phép thực thi chương trình , đối với thư mục , quyền này cho phép vào thư mục bằng lệnh `cd` .
- Quyền truy xuất gồm 3 nhóm :

    <img src=https://i.imgur.com/9k9Pv64.png>

  - Bảng cờ đặc tính ( **_flag_** ) :

    | Ký hiệu | Kiểu file                   |
    | ------- | --------------------------- |
    | `-`     | Regular file                |
    | `d`     | Directory                   |
    | `l`     | Symbolic link ( Soft link ) |
    | `b`     | Block special file          |
    | `c`     | Character special file      |
    | `p`     | Named pipe                  |
    | `s`     | Socket                      |

  - **Nhóm 1 :** Quyền của người sở hữu ( owner hoặc user ) , ký hiệu bằng kí tự `u` : người tạo ra thư mục / file hoặc được gán quyền sở hữu .
  - **Nhóm 2 :** Quyền của nhóm ( group ) ký hiệu bằng kí tự `g` : nhóm người sử dụng được gắn quyền .
  - **Nhóm 3 :** Quyền của người dùng khác ( others ) ký hiệu bằng kí tự `o` : là những người sử dụng khác không thuộc 2 nhóm trên .

### Biểu diễn quyền truy xuất

- Biểu diễn quyền truy xuất có 2 cách : bằng chữ và bằng số

#### Bằng chữ

- Trong cách biểu diễn này , quyền truy xuất được viết bằng các ký tự :
  - `r` : read
  - `w` : write
  - `x` : execute
  - `-` : không có quyền
  - **VD :**
    - `rwx` : có full quyền
    - `r--` : chỉ có quyền đọc
    - `rw-` : chỉ có quyền đọc và ghi
    - `---` : không có quyền gì
- Quyền hạn trên 1 file sẽ gồm cả 3 nhóm quyền ( **owner , group , others** ) nên danh sách quyền sẽ gồm `9` kí tự :
  - **VD :**
    - `rwxrw----` : người sở hữu có full quyền , các user cùng nhóm chỉ có quyền đọc/ghi còn mọi người khác không có quyền truy xuất .
    - `rw-r-----` : người sở hữu có quyền đọc/ghi , các user cùng nhóm chỉ có quyền đọc còn mọi người khác không có quyền truy xuất .
    - `rwxr-xr--` : người sở hữu có full quyền , các user cùng nhóm chỉ có quyền đọc và thực thi chương trình còn mọi người khác chỉ có quyền đọc .

#### Bằng số

- Trong cách biểu diễn này , mỗi quyền được gán cho 1 trị số theo bảng sau :
<center>

| Quyền | Giá trị |
| ----- | ------- |
| `r`   | `4`     |
| `w`   | `2`     |
| `x`   | `1`     |

</center>
- Mỗi nhóm quyền truy xuất là tổng của các loại quyền trên :
<center>

| Quyền | Ý nghĩa                      | Biểu diễn bằng số |
| ----- | ---------------------------- | ----------------- |
| `rwx` | Có full quyền                | `7`               |
| `rw-` | Chỉ có quyền đọc và ghi      | `6`               |
| `r-x` | Chỉ có quyền đọc và thực thi | `5`               |
| `r--` | Chỉ có quyền đọc             | `4`               |
| `---` | Không có quyền gì            | `0`               |

</center>

- Vì quyền thực sự gồm cả 3 nhóm quyền ( **owner , group , others** ) nên danh sách quyền biểu diễn dưới dạng số sẽ gồm `3` chữ số .
  - **VD :**
    - `rwxrw----` ( `760` ) : người sở hữu có toàn quyền , các user cùng nhóm chỉ có quyền đọc/ghi còn mọi người khác không có quyền truy xuất .
    - `rw-r--r--` ( `644` ) : người sở hữu có quyền đọc/ghi , các user cùng nhóm chỉ có quyền đọc còn mọi người khác không có quyền truy xuất .
    - `rwxr-xr--` ( `754` ) : người sở hữu có toàn quyền , các user cùng nhóm chỉ có quyền đọc và thực thi chương trình còn mọi người khác chỉ có quyền đọc .
      > **\*Lưu ý :** Người sử dụng có quyền đọc thì có quyền sao chép tập tin và tập tin sau khi sao chép sẽ thuộc về sở hữu của người thực hiện sao chép .\*

### Các lệnh về quyền

#### chmod

- Là lệnh thay đổi quyền truy xuất trên thư mục / tập tin
  ```
  # chmod [options] [mode] [file]
  ```
  - **Options :**
    - `-R` : áp dụng với mọi thư mục làm cho lệnh `chmod` có hiệu lực trên cả các thư mục con
  - **Mode :** Quyền truy xuất mới cho tập tin
    - `u` : quyền của người sở hữu ( **owner** )
    - `g` : quyền sở hữu của nhóm ( **group** )
    - `o` : quyền của mọi user khác ( **others** )
    - `+` : thêm quyền
    - `-` : rút bớt quyền
    - `=` : gán quyền
    - **VD :**
      - `g+w` : thêm quyền ghi cho group
      - `o-rwx` : loại bỏ tất cả các quyền của các user khác
      - `u+x` : thêm quyền thực thi cho user
      - `+x` : thêm quyền thực thi cho cả
      - `a+rw` : thêm quyền đọc ghi cho tất cả
      - `ug+r` : thêm quyền đọc cho owner và group
      - `o=x` : chỉ cho phép mọi người thực thi

#### chown

- Là lệnh thay đổi chủ sở hữu thư mục / tập tin ( **owner** )
  ```
  # chown [options] [owner] [file]
  ```
  - **Options :**
    - `-R` : áp dụng đối với thư mục làm cho lệnh `chown` có tác dụng trên cả các thư mục con
  - **Owner :** chủ sở hữu mới của tập tin
- Có thể thay đổi đồng thời chủ sở hữu và group sở hữu file
  ```
  # chown [options] [owner]:[group_owner] [file]
  ```

#### chgrp

- Là lệnh thay đổi nhóm sở hữu thư mục / tập tin
  ```
  # chgrp [options] [group_owner] [file]
  ```
  - **Options :**
    - `-R` : áp dụng đối với thư mục làm cho lệnh `chgrp` có tác dụng trên cả các thư mục con
  - **Group_owner :** nhóm sở hữu mới của tập tin

## Lệnh find

Lệnh find là một trong những lệnh quan trọng và tiện dụng nhất trên hệ thống Linux. Như tên gọi của nó cho thấy, lệnh có thể tìm các file trên PC Linux dựa trên khá nhiều điều kiện và biến số. Ta có thể tìm file theo quyền, người dùng, nhóm, loại file, ngày tháng, dung lượng và các tiêu chí có thể có khác bằng cách sử dụng lệnh find.

### Cú pháp

```
find [path] [options] [expression]
```

Trong đó :

- path: Đường dẫn thư mục bắt đầu tìm kiếm. Nếu không chỉ định, lệnh find sẽ tìm kiếm trong thư mục hiện tại.
- options: Các tùy chọn để điều chỉnh quá trình tìm kiếm.
- expression: Biểu thức tìm kiếm.

### Các tùy chọn phổ biến của lệnh find

- `-name`: Tìm kiếm theo tên tệp tin.
- `-type`: Tìm kiếm theo loại tệp tin (vd: -type f tìm kiếm tệp tin, -type d tìm kiếm thư mục).
- `-size`: Tìm kiếm theo kích thước tệp tin (vd: -size +10M tìm kiếm tệp tin lớn hơn 10 megabytes).
- `-mtime`: Tìm kiếm theo thời gian sửa đổi tệp tin (vd: -mtime +7 tìm kiếm các tệp tin đã sửa đổi trước hơn 7 ngày).
- `-user`: Tìm kiếm theo tên người dùng sở hữu tệp tin.
- `-exec`: Thực hiện một lệnh trên các tệp tin được tìm thấy (vd: -exec rm {} \; xóa tất cả các tệp tin được tìm thấy).

### Ví dụng

Tìm kiếm tất cả các tệp tin có tên là “file.txt” trong thư mục hiện tại và các thư mục con:

```
find . -name file.txt
```

Tìm kiếm tất cả các thư mục trên hệ thống có tên là “data”:

```
find / -type d -name data
```

Tìm kiếm tất cả các tệp tin có kích thước lớn hơn 10 megabytes trong thư mục /home/user/documents:

```
find /home/user/documents -type f -size +10M
```

Tìm kiếm tất cả các tệp tin được sửa đổi trong vòng 7 ngày trở lại đây trong thư mục /var/log:

```
find /var/log -type f -mtime -7
```

Tìm kiếm tất cả các tệp tin có tên là “file.txt” và đổi tên chúng thành “newfile.txt”:

```
find . -name file.txt -exec mv {} newfile.txt \;
```

## Lệnh locate

Lệnh locate là cách nhanh nhất và đơn giản nhất để tìm kiếm các file, cũng như thư mục theo tên

### Cách lệnh locate hoạt động

Lệnh `locate` tìm kiếm một pattern (mẫu) nhất định thông qua file cơ sở dữ liệu được tạo bởi lệnh `updatedb` ( Vị trí của CSDL được lưu tại `var/lib/plocate/plocate.db`). Các kết quả tìm thấy được hiển thị trên màn hình, mỗi kết quả trên một dòng.

Trong quá trình cài đặt gói `plocate`, một cron job được tạo để chạy lệnh `updatedb` cứ sau 24 giờ. Điều này đảm bảo cơ sở dữ liệu được cập nhật thường xuyên.

Cơ sở dữ liệu có thể được cập nhật thủ công bằng cách chạy lệnh `updatedb` với quyền root hoặc người dùng có quyền sudo:

```
$ sudo updatedb
```

Quá trình cập nhật sẽ mất một chút thời gian, tùy thuộc vào số lượng file và thư mục, cũng như tốc độ hệ thống của bạn.

Các file được tạo sau khi cập nhật cơ sở dữ liệu sẽ không được hiển thị trong kết quả lệnh `locate`.

### Cú pháp

```
locate [OPTION] PATTERN...
```

Ở dạng cơ bản nhất, khi được sử dụng mà không có bất kỳ tùy chọn nào, lệnh locate sẽ in đường dẫn tuyệt đối của tất cả các file và thư mục phù hợp với mẫu tìm kiếm và người dùng có quyền đọc file trong kết quả tìm kiếm.

### Các tùy chọn phổ biến của lệnh locate

- `-n` : Giới hạn kết quả tìm kiếm
- `-i` : Tìm kiếm không phân biệt chữ hoa chữ thường
- `-c` : Để hiển thị số lượng kết quả tìm kiếm
- `-e` : Để chỉ hiển thị tên của các file còn tồn tại ở thời điểm lệnh locate được chạy
- `-r` : Cho phép tìm kiếm bằng cách sử dụng biểu thức chính quy thay vì mẫu

### VD

Tìm kiếm file có tên `.bashrc`

```
$ locate .bashrc
```

Tìm kiếm tất cả các file `.py` và chỉ hiển thị 10 kết quả

```
$ locate -n 10 *.py
```

Tìm kiếm file `readme.md` mà không phân biệt chữ hoa hay chữ thường

```
$ locate -i readme.md
```

Tìm kiếm số lượng của tất cả các file có chứa `.bashrc` trong tên của chúng

```
$ locate -c .bashrc
```

Tìm kiếm các file `.json` còn tồn tại tại thời điểm tìm kiếm

```
$ locate -e *.json
```

Tìm kiếm tất cả các file .mp4 và .avi trên hệ thống , không phân biệt chữ hoa, chữ thường

```
$ locate --regex -i "(\.mp4|\.avi)"
```

## Lệnh Whereis

Lệnh whereis được sử dụng để xác định vị trí lưu trữ các binary file, source code, manual page (manpage) của 1 chương trình hay 1 câu lệnh trong Linux

### Cú pháp

```
whereis [option] program_name/command
```

Khi không có tùy chọn (option), whereis trả về đường dẫn tuyệt đối của binary file, source code, man page (nếu chúng tồn tại) cho program_name (hoặc câu lệnh).

### Các tùy chọn phổ biến của lệnh locate

- `-b`: Tìm kiếm binary file
- `-m`: Tìm kiếm man page
- `-s`: Tìm kiếm source code

### VD

Xem đầy đủ thông tin của lệnh `bash`

```
whereis bash
```

Chỉ xem vị trí binary file của lệnh `bash`

```
whereis -b bash
```

Chỉ xem vị trí man page của lệnh `bash`

```
whereis -m bash
```

Chỉ xem vị trí source code của lệnh `bash`

```
whereis -s bash
```

## Lệnh which

Linux dùng lệnh which để xác định vị trí file thực thi của lệnh mà ta truyền vào. Lệnh này sẽ tìm kiếm các đường dẫn trong biến môi trường PATH, so khớp và trả về kết quả tương ứng với lệnh truyền vào.

### Cú pháp

```
which [OPTIONS] FILE_NAME
```

Tuỳ chọn duy nhất của which :

- `-a`: in ra toàn bộ các kết quả chứa câu lệnh

### VD

```
which ping
// Kết quả
/bin/ping
```

## Quản lý User

- Trên Linux có 2 loại user :
  - **User hệ thống**
  - **User người dùng**
- **User hệ thống** : dùng để thực thi các module , script cần thiết phục vụ cho hệ điều hành .
- **User người dùng** : là những tài khoản để login sử dụng hệ điều hành .
- Trong các tài khoản người dùng thì tài khoản user `root` ( **_super user_** ) là tài khoản quan trọng nhất :
  - Tài khoản này được tự động tạo ra khi cài đặt Linux .
  - Tài khoản này không thể đổi tên hoặc xóa bỏ .
  - User `root` còn gọi là **_super user_** vì nó có full quyền trên hệ thống .
  - Chỉ làm việc với user `root` khi muốn thực hiện công tác quản trị hệ thống , trong các trường hợp khác , chỉ nên làm việc với user thường .
- Mỗi user thường có đặc điểm như sau :
  - Tên tài khoản user là duy nhất , có thể đặt tên _chữ thường , chữ hoa_ .
  - Mỗi user có 1 mã định danh duy nhất ( **uid** ) .
  - Mỗi user có thể thuộc về nhiều group .
  - Tài khoản **_super user_** có **uid**=**gid**=`0` .

### Các lệnh quản lý User

Lệnh tạo user mới :

```
useradd <username>

// VD : Tạo user có tên là example
// useradd example
```

Đặt password cho user vừa tạo :

```
passwd <password>

// VD : Tạo password có tên là example
// passwd example
```

Chỉ định home directory của user và khởi tạo trong quá trình khởi động :

```
useradd -d <dir> -m <username>

// VD : Tạo user example có home directory là /example
// useradd -d /home/example -m example
```

Tạo user với group tùy chọn(đã tồn tại và chưa tồn tại) :

```
useradd -G <group_name> <username>

// Ví dụ: Tạo user example thuộc group Temp
// useradd -G Temp example
```

Xóa user :

```
userdel <username>

// VD : Xóa user example
// userdel example
```

Xóa user và cả home directory của user đó :

```
userdel -r <username>

// VD : Xóa user example và cả home directory của example
// userdel -r exampl
```

### File dữ liệu về User

#### /etc/passwd

Là file văn bản chứa thông tin về các tài khoản user trên máy. Mọi user đều có thể đọc tập tin này nhưng chỉ có user root mới có quyền thay đổi. Để xem nội dung file ta dùng lệnh :

```
cat /etc/passwd
```

Cấu trúc file :

![](https://github.com/nhanhoadocs/thuctapsinh/raw/master/HienNT/Linux/images/25%20bai%20linux/download.png)

Trong đó :

- `Username` - tên đăng nhập của người dùng, có phân biệt HOA/thường(nên sử dụng chữ thường).

- `Password` - chuỗi password đã mã hóa, nếu có sử dụng password thì ở đây sẽ là chữ x.

- `User ID` - ID của user, được hệ thống dùng để nhận biết và phân biệt user.

- `Group ID` - ID của nhóm mà user nằm trong đó.

- `User Info` - mô tả user.

- `HomeDirectory` - Đường dẫn tuyệt đối đến thư mục mà người dùng sẽ ở khi họ đăng nhập. Nếu thư mục này không tồn tại thì thư mục người dùng sẽ trở thành `/`

- `Shell` - Đường dẫn tuyệt đối của lệnh hoặc shell (`/ bin / bash`). Nếu không có shell thì user sẽ không thể login vào.

#### /etc/shadow

Đây là tập tin văn bản chứa thông tin về mật khẩu của các tài khoản user lưu trên máy. Chỉ có user root mới có quyền đọc tập tin này . User root có quyền reset mật khẩu của bất cứ user nào trên máy .

![](https://camo.githubusercontent.com/676554528cfd0e7912c0851b290eb569a14ae556f04c9d5fb3b702f84ad37884/68747470733a2f2f692e696d6775722e636f6d2f394e3061444d312e706e67)

Trong đó :

- `1` - Tên user , giống với trong `/etc/passwd` ( **_login name_** )
- `2` - Mật khẩu đã được mã hóa
  - Để trống ( _empty_ ) - không có mật khẩu
  - `*` - tài khoản bị tạm ngưng ( _disable_ )
- `3` - Số ngày kể từ lần cuối thay đổi mật khẩu ( tính từ `1/1/1970` )
- `4` - Số ngày trước khi có thể thay đổi mật khẩu . Giá trị `0` có nghĩa có thể thay đổi bất cứ lúc nào .
- `5` - Số ngày mật khẩu có giá trị . `99999` có nghĩa mật khẩu có giá trị vô thời hạn .
- `6` - Số ngày cảnh báo user trước khi mật khẩu hết hạn
- `7` - Số ngày sau khi mật khẩu hết hạn tài khoản sẽ bị khóa . Thường có giá trị là `7` ( 1 tuần )
- `8` - Số ngày kể từ khi tài khoản bị khóa ( tính từ `1/1/1970` )

## Quản lý Group

Group là tập hợp của nhiều user. Mỗi group có 1 tên duy nhất và 1 mã định danh duy nhất ( gid ). Khi tạo ra 1 user ( không dùng option -g ) thì mặc định 1 group mang tên user được tạo ra .

### Các lệnh quản lý User

Lệnh tạo group mới :

```
groupadd [option] [group_name]

// Option :
// 	-g [gid] : định nghĩa nhóm cùng mã nhóm ( gid )

// VD : Tạo group example với GID là 1010
// groupadd -g 1010 example
```

Lệnh sửa thông tin group :

```
groupmod [options] [group_name]

// Option :
// 	-g [gid] : sửa lại mã nhóm ( gid )
// 	-n [group_name] : sửa lại tên group

// VD : Sửa GID của group example thành 1002
// groupmod -g 1002
```

Lệnh xóa group :

```
groupdel [group_name]

// VD : xóa group example
// userdel example
```

### File /etc/group

Đây là tập tin văn bản chứa thông tin về các group trên máy . Mọi user đều có quyền đọc tập tin này nhưng chỉ có user root mới có quyền thay đổi .

![](https://camo.githubusercontent.com/34bbfda1bc073bdf0e28e65f458df677299e2720e0ffb9501b9f15600e796131/68747470733a2f2f692e696d6775722e636f6d2f42304243595a472e706e67)

Ý nghĩa các cột :

- `1` - Tên group
- `2` - Mật khẩu group đã được mã hóa ( vì có file `/etc/gshadow` ) nên mặc định ở đây là `x`
- `3` - Mã nhóm ( **_gid_** )
- `4` - Danh sách các user nằm trong nhóm

## Giới thiệu về file log

File log là một tập hợp các bản ghi mà hệ thống duy trì để các quản trị viên theo dõi các sự kiện quan trọng. Các file log này sẽ chứa các thông báo về máy chủ, bao gồm kernel, dịch vụ và ứng dụng đang chạy trên nó. File log cung cấp thời gian của các sự kiện cho hệ điều hành, ứng dụng và hệ thống Linux và là một công cụ quan trọng giúp chúng ta kiểm tra và khắc phục sự cố.

Trong hệ quản trị Linux thì kho lưu trữ Log được tập trung tại các file log trong thư mục `/var/log`

### Các file log quan trọng

- **`/var/log/syslog`** : File log này sẽ chứa nhật ký hoạt động hệ thống (System Logs). Nó chủ yếu được sử dụng để lưu trữ các thông tin liên quan đến hệ thống như mail, cron, daemon, kern, auth,…

- **`/var/log/auth.log`** : Chứa thông tin xác thực trên hệ thống trong máy chủ được ghi lại. Khi các bạn tìm kiếm vấn đề liên quan đến cơ chế ủy quyền của người dùng thì hãy tìm kiếm trong file log này.

- **`/var/log/boot.log`** : nơi lưu trữ tất cả thông tin liên quan đến khởi động và mọi thông báo được ghi lại trong quá trình khởi động bao gồm tập lệnh khởi tạo hệ thống, /etc/init.d/bootmisc.sh,…

- **`/var/log/dmesg`** : nơi lưu trữ thông tin liên quan đến trình quản lý thiết bị (device drivers).

- **`/var/log/kern.log`** : Đây là một file log vô cùng quan trọng chính là nơi chứa các thông tin được ghi bởi kernel. Thông qua file log này giúp cho chúng ta có thể khắc phục các lỗi và cảnh báo liên quan đến kernel.

- **`/var/log/wtmp`** : Chứa các bản ghi đăng nhập. Sử dụng wtmp bạn có thể tìm ra ai đã đăng nhập vào hệ thống.

- **`/var/log/btmp`** : Tập tin này chứa thông tin về các thông tin đăng nhập thất bại.

### Giới thiệu Rotate Log

#### Định nghĩa

Rotate Log là quá trình xử lý các file log cũ theo một quy trình như xóa, nén hoặc di chuyển và tạo ra file log mới theo thời gian (ngày, tuần,...), theo dung lượng giúp tránh việc file log quá lớn và gây tắc nghẽn hệ thống.

#### Cấu hình với Logrotate

Các file cấu hình chính của Logrotate :

- **`/etc/logrotate.conf`** : chứa các thông tin thiết lập toàn bộ file log mà Logrotate quản lý, bao gồm chu kì lặp, dung lượng file log, nén file,…
- **`/etc/logrotate.d/`** : chứa thông tin về cấu hình file log đối với từng ứng dụng được lưu tại đây.

#### Các thông số trong việc cấu hình Logratate

| Thông số      | Chức năng                                                                                    |
| ------------- | :------------------------------------------------------------------------------------------- |
| daily         | Mỗi ngày                                                                                     |
| weekly        | Mỗi tuần                                                                                     |
| monthly       | Mỗi tháng                                                                                    |
| yearly        | Mỗi năm                                                                                      |
| size          | Rotate khi đạt đến dung lượng file yêu cầu                                                   |
| rotate        | Quy định số lượng file log cũ được giữ lại sau khi rotate                                    |
| missingok     | Nếu file log không tồn tại, chuyển sang file tiếp theo mà không đưa ra thông báo lỗi         |
| nomissingok   | Ngược lại với missingok                                                                      |
| notifempty    | Không thực hiện rotate đối với file log trống này                                            |
| compress      | File log sẽ được nén sau khi rotate dưới dạng gzip                                           |
| nocompress    | Không nén file log cũ                                                                        |
| compresscmd   | Nén file log dưới dạng khác như xz, zip, bzip2,...                                           |
| delaycompress | Không nén file log cũ ngay sau khi rotate, việc nén sẽ được thực hiện vào lần rotate kế tiếp |
| su            | Thay đổi user và group thay vì sử dụng default user/group                                    |
| create        | Phân quyền cho file log mới sau khi rotate                                                   |

#### Cấu hình logrotate với file /var/log/syslog :

```
/var/log/syslog{
        daily
        rotate 4
        nomissingok
        su root syslog
        create 664 root syslog
}
```

Thực hiện rotate định kì hàng ngày, dữ liệu được lưu trong 4 file, nếu file log không tồn tại, thông báo lỗi, file log mới tạo ra sẽ có quyền đọc và ghi với user là root và group là syslog, các loại tài khoản còn lại chỉ có quyền đọc

## Thiết lập Cron Job trong Linux

### Cron Job là gì ?

Cron là chương trình được tích hợp sẵn trong hệ thống Linux, cho phép chạy các lệnh tự động tại một thời điểm cụ thể. Các nhà quản trị lựa chọn công cụ này để tự động hóa các tác vụ sao lưu, dọn dẹp thư mục, thông báo trên hệ điều hành Linux.

### Thiết lập Cron

Các công việc cron được ghi lại và quản lý trong một tệp đặc biệt được gọi là **crontab**. Mỗi user đều có một crontab riêng được lưu ở `/var/spool/cron/crontabs/`

Để thêm một cronjob, bạn sẽ mở crontab của mình thêm một cron được viết dưới dạng `a cron expression`. Một biểu thức cron được chia làm 2 phần: _**lịch trình (schedule)**_ và _**câu lệnh (command)**_.

Cấu trúc :

```
* * * * * command được thực hiện
- - - - -
| | | | |
| | | | +----- ngày trong tuần (0 - 6) (Sunday=0)
| | | +------- tháng (1 - 12)
| | +--------- ngày trong tháng (1 - 31)
| +----------- giờ (0 - 23)
+------------- phút (0 - 59)
```

Phần schedule còn nhận một số giá trị đặc biệt, nhằm viết biểu thức cron một cách dễ dàng hơn:

- **`*`** : Tất cả các giá trị
- **`-`** : Khoảng giá trị. VD: 6-8 cột giờ thực hiện lúc 6h, 7h, 8h
- **`,`** : Liệt kê các giá trị. VD: 10,20,30 cột phút thực hiện ở các phút 10, phút 20, phút 30.
- **`/`** : Bước nhảy giá trị. VD: _/15 8-10/2 _ \* \* sẽ thực hiện vào 8h00, 8h15, 8h30, 8h45, 10h00, 10h15, 10h30, 10h45

Ví dụ :

```
* * * * * - Chạy command mỗi phút

0,15,30,45 * * * * - Chạy command mỗi 15 phút.

*/15 * * * * - Giống như trên.

0 4 * * * - Chạy command mỗi ngày 4 giờ sáng.

0 4 * * 2-4 - Chạy command vào 4 giờ chiều Thứ 3, Thứ 4, Thứ 5.

20,40 */8 * 7-12 * - Chạy command vào phút 20 và 40 mỗi 8 giờ vào tháng 7 đến tháng 12.
```

Một số syntax đặc biệt :

- **@yearly** : Chạy một lần mỗi năm "0 0 1 1 \*"
- **@annually** : (Tương tự @yearly)
- **@monthly** : Chạy mỗi tháng một lần "0 0 1 \* \*"
- **@weekly** : Chạy mỗi tuần một lần "0 0 \* \* 0"
- **@daily** : Chạy một lần mỗi ngày "0 0 \* \* \*"
- **@midnight** : (Tương tự @daily)
- **@hourly** : Chạy một lần mỗi giờ "0 \* \* \* \*"

Để thêm/sửa/xóa crontab:

```
crontab -e
```

![](https://co-well.vn/wp-content/uploads/2022/03/cron-3.png)

Thêm và lưu lại, crontab không cần khởi động lại để áp dụng.

Xem các crontab đang chạy:

```
crontab -l
```

Xóa crontab của user:

```
crontab -r
```

### Quản lý output

Do cron là tác vụ chạy background nên không thể biết nó đã thành công hay chưa. Ta có thể thử nghiệm một số cách khác nhau để theo dõi việc hoàn thành của cronjob.

Nếu ta có một service để gửi mail, ta có thể gửi kết quả của cron tới email được chỉ định ở `MAILTO` trên đầu crontab :

```
MAILTO="example@gmail.com"

SHELL=/bin/bash

HOME=/

* * * * * echo ‘Run this command every minute’
```

### Hạn chế truy cập

Ta có thể quản lý user nào được phép sử dụng crontab với các file `cron.allow` và `cron.deny`, cả hai file này đều nằm ở thư mục `/etc/`.

Nếu `cron.allow` tồn tại thì chỉ user được list mới edit được crontab. Nếu cả 2 file cùng tồn tại và cùng user được list thì `cron.allow` sẽ được ưu tiên hơn.

Cú pháp:

```
sudo echo ALL >>/etc/cron.deny

sudo echo testuser>>/etc/cron.allow
```

## Thiết lập at trong Linux

### Tổng quan lệnh at

Là một phương án thay thế cho trình lập lịch cron, lệnh at cho phép bạn lên lịch chạy một lệnh một lần vào một thời gian cụ thể mà không cần chỉnh sửa tệp cấu hình. Yêu cầu duy nhất là cài đặt tiện ích này và bắt đầu kích hoạt việc thực thi của nó.

Cú pháp :

```
at [option] runtime
```

### Cách chỉ định ngày và thời gian để lên lịch cho các lệnh at

#### Chạy lệnh sau số phút, giờ, ngày hoặc tuần được chỉ định :

```
at now + 10 minutes
at now + 10 hours
at now + 10 days
at now + 10 weeks
```

#### Chạy vào một thời điểm chính xác:

```
at 23:10
```

Nếu bây giờ là 12:00, và ta chạy:

```
at 11:00
```

Thì lệnh sẽ chạy vào ngày mai, tại thời điểm được chỉ định.

#### Chạy vào thời gian và ngày được chỉ định chính xác:

```
at 12:00 December 31
```

### Cách sử dụng lệnh at

Sau khi chỉ định thời gian được lên lịch, một dấu nhắc lệnh giống như hình ảnh sau sẽ xuất hiện:

![](https://st.quantrimang.com/photos/image/2019/03/01/len-lich-cac-lenh-trong-linux-voi-at-4.jpg)

Tại đây, người dùng chỉ cần nhập các lệnh muốn chạy. Chúng sẽ được thực thi dưới tên user hiện tại. Nhập lệnh muốn chạy tại một thời điểm được chỉ định và nhấn `Enter`. Nếu muốn chạy một lệnh tiếp theo, lặp lại quy trình tương tự. Khi thực hiện xong, nhấn `Ctrl + D`. <EOT> sẽ được hiển thị khi nhấn các phím đó, theo sau là thời gian (các) lệnh sẽ được thực thi.

Nếu máy tính bị tắt trước khi một công việc được lên lịch có cơ hội chạy, nhiệm vụ đó sẽ chạy ở lần khởi động tiếp theo (nếu thời gian được đặt cho nó đã qua). Ví dụ, nếu lên lịch công việc vào lúc 3 giờ chiều, tắt máy lúc 2 giờ chiều và bật nguồn lúc 4 giờ chiều, công việc sẽ chạy vào lúc 4 giờ chiều.

### Xem và/hoặc xóa các công việc theo lịch trình

Người dùng có thể xem các công việc được xếp theo thứ tự với lệnh:

```
atq
```

Hoặc lệnh :

```
at -l
```

![](https://st.quantrimang.com/photos/image/2019/03/01/len-lich-cac-lenh-trong-linux-voi-at-6.jpg)

Để xem những lệnh nào được lên lịch trong một công việc, hãy sử dụng số tiền tố của công việc đó.

```
at -c 22
```

![](https://st.quantrimang.com/photos/image/2019/03/01/len-lich-cac-lenh-trong-linux-voi-at-7.jpg)

Các dòng đầu ra cuối cùng sẽ hiển thị cho người dùng các lệnh đã lên lịch.

Để xóa một công việc, sử dụng số tiền tố của nó như sau:

```
atrm 22
```

hoặc :

```
at -d 22
```

## Cấu hình ip tĩnh trên Ubuntu

Trước tiên, hãy tìm tên network interface bằng lệnh bên dưới:

```
sudo ip a
```

![](https://st.quantrimang.com/photos/image/2023/02/23/cau-hinh-dia-chi-ip-tinh-tren-ubuntu-3.jpg)

Những gì ta thấy ở đây là tên network interface của mình. Tên này có thể khác nhau trên mỗi thiết bị.

Bây giờ, hãy tạo một file có tên `01-netcfg.yaml` trong thư mục `/etc/netplan`, ngoài ra có thể sử dụng file có sẵn trong thư mục đó . Sau đó chỉnh sửa nó bằng trình soạn thảo văn bản.

```
sudo vim /etc/netplan/01-netcfg.yaml
```

Thêm vào các dòng sau vào file vừa tạo :

```
network:
  version: 2
  renderer: networkd
  ethernets:
    eth0: #Edit this line according to your network interface name.
      dhcp4: no
      addresses:
        - 192.168.1.10/24
      gateway4: 192.168.1.1
      nameservers:
        addresses:
          - 8.8.8.8
          - 8.8.4.4   
```

Sau khi lưu file này, hãy chạy lệnh sau để áp dụng các thay đổi :

```
sudo netplan apply
```

## Cấu hình ip tĩnh cho Centos 7

Trước tiên, hãy tìm tên network interface bằng lệnh tương tự như khi làm trên Ubuntu:

```
sudo ip a
```

Giờ ta có network interface của mình thì ta cần tạo ra 1 file cấu hình có tiền tố là `ifcfg-<network-if>` trong thư mục `/etc/sysconfig/network-scripts/`. Ví dụ dưới đây ta sẽ tạo file `ifcfg-eth0`

```
# vi /etc/sysconfig/network-scripts/ifcfg-eth0
DEVICE=eth0
NAME=eth0
HWADDR=00:08:A2:0A:BA:B8
UUID=41171a6f-bce1-44de-8a6e-cf5e782f8bd6
ONBOOT=yes
TYPE=Ethernet
BOOTPROTO=static
IPV4_FAILURE_FATAL=no
IPV6INIT=no
IPADDR=192.168.1.10
PREFIX=24
GATEWAY=192.168.1.1
DNS1=8.8.8.8
DNS2=8.8.4.4
DEFROUTE=yes
```

_**Chú thích**_ :

- **DEVICE** : tên card mạng đã được liệt kê ở phần 1, nên điền chính xác tên interface thì hệ thống mới nhận biết được interface nào để cấu hình cho nó.

- **NAME** : nội dung y như phần DEVICE.

- **ONBOOT** : phải để option _**yes**_ thì khi reboot hệ thống, network mới tự động được bật lên với cấu hình interface tương ứng.

- **BOOTPROTO** : cấu hình IP tĩnh hay DHCP. Nếu là DHCP thì để giá trị _**dhcp**_.

- **IPV6INIT** : tắt chức năng hỗ trợ sử dụng IPv6 trên interface

- **IPADDR** : địa chỉ IP tĩnh.

- **PREFIX** : subnet mask của lớp mạng IP sử dụng.

- **GATEWAY** : địa chỉ IP cổng gateway.

- **DNS1** : thông tin DNS server.

## DNS là gì ?

DNS (tên tiếng anh: Domain Name System, dịch là hệ thống phân giải tên miền), là một hệ thống cho phép thiết lập tương ứng giữa địa chỉ IP và tên miền trên Internet. Hệ thống này được ra đời vào năm 1984.

Hệ thống phân giải tên miền giúp truy cập vào địa chỉ IP của website mà bạn muốn dễ dàng và nhanh chóng hơn. Hiểu đơn giản, DNS giống như danh bạ điện thoại, trong đó, địa chỉ IP tương ứng với số điện thoại còn tên miền của website tương ứng với tên chủ nhân số điện thoại đó.

### Cách thức hoạt động của DNS

Để giải thích cơ chế hoạt động của DNS, chúng ta sẽ tìm hiểu quy trình khi một máy tính cá nhân (client) muốn truy cập vào địa chỉ example.vn, cụ thể như sau:

- **Bước 1** : Máy client của người dùng sẽ gửi truy vấn về tên miền example.vn tới máy chủ quản lý tên miền (name server) cục bộ để tìm ra IP của example.vn

- **Bước 2** : Máy chủ tên miền cục bộ này sẽ tiến hành rà soát trong cơ sở dữ liệu của nó xem có thông tin về tên miền example.vn ứng với IP nào hay không. Nếu có, nó sẽ trả ngay lại IP của example.vn cho client. Nếu không, nó sẽ gửi truy vấn tới ROOT Name Server.

- **Bước 3** : Tuy nhiên, Root Name Server không có chứa dữ liệu về tên miền cũng như IP, mà nó chỉ có dữ liệu về máy chủ quản lý tên miền đó (.vn). Nên Root Name Server sẽ gửi thông tin về địa chỉ máy chủ quản lý các tên miền .VN về cho máy chủ tên miền cục bộ.

- **Bước 4** : Tiếp theo, Máy chủ tên miền cục bộ lại gửi yêu cầu đến máy chủ quản lý tên miền .vn để tìm example.vn.

- **Bước 5** : Vì máy chủ quản lý tên miền VN có chứa CSDL của tất cả tên miền .vn nên nó sẽ trả lại địa chỉ IP của tên miền example.vn cho máy chủ tên miền cục bộ.

- **Bước 6** : Máy chủ tên miền cục bộ sẽ gửi thông tin này đến máy client, máy client tiếp tục sử dụng ip vừa được cung cấp để truy cập tới server của example.vn.

### Các loại DNS Server

#### Recursor nameserver

Khi người dùng thực hiện truy vấn đến 1 tên miền, đầu tiên nó sẽ đi đến server DNS Recursor. Khi nhận được truy vấn, server DNS Recursor sẽ trả lại cho người dùng kết quả của truy vấn trong bộ nhớ đệm của nó (nếu có) hoặc nó sẽ giúp người dùng gửi các truy vấn đến Root nameserver, TLD nameserver và Authoritative nameserver để lấy kết quả, sau đó nó sẽ trả lời cho người dùng kết quả nó nhận được. Sau quá trình truy vấn, DNS Recursor sẽ lưu lại kết quả trong bộ nhớ đệm, và khi có người dùng khác truy vấn lại đến tên miền đó, nó sẽ có thể trả lại kết quả ngay mà không cần phải thực hiện lại quá trình truy vấn.

#### Root nameserver

Là nameserver nằm trên đỉnh của hệ thống phân cấp DNS và trên thế giới có khoảng 12 DNS Root Nameserver. Nó sẽ chứa toàn bộ các thông tin về domain và IP của các Top Level Domain (TLD) Nameserver. Khi có truy vấn được gửi đến nó, root nameserver sẽ trả lại thông tin của TLD Nameserver để client tiếp tục truy vấn kết quả.

#### TLD (Top Level Domain) Nameserver

Là nameserver chứa toàn bộ thông tin về mọi tên miền cùng chung phần mở rộng tên miền như .com, .vn, .net,… Khi nhận được truy vấn, TLD nameserver sẽ trả lại cho client thông tin của Authoritative Nameserver quản lý tên miền đang được truy vấn.

#### Authoritative Nameserver

Là máy chủ chứa toàn bộ thông tin về tên miền mà nó quản lý . Tại đây , việc phân giải tên miền diễn ra. Nó sẽ đưa cho Recursor nameserver địa chỉ IP cần thiết tìm thấy trong danh mục các bản ghi của nó.

### Các loại Query trong DNS

- **Recursive query**: DNS client yêu cầu máy chủ DNS (thường là Recursor nameserver). Sẽ trả lời máy khách bằng bản ghi tài nguyên được yêu cầu. Hoặc thông báo lỗi nếu resolver không thể tìm thấy bản ghi.

- **Iterative query**: Là truy vấn mà DNS Server có thể cung cấp câu trả lời hoặc 1 phần câu trả lời (như 1 lời giới thiệu) cho clients (hoặc đưa ra thông báo lỗi). Với truy vấn này, nếu DNS Server có câu trả lời cho truy vấn trong bộ nhớ đệm của nó, nó sẽ trả lại kết quả cho người dùng, nếu không, nó sẽ trả lại lời giới thiệu đến DNS Server biết được câu trả lời của truy vấn, để người dùng tự truy vấn.

- **Non-recursive query**: Thông thường điều này sẽ xảy ra khi DNS resolver client truy vấn máy chủ DNS một record mà server có quyền truy cập hoặc bản ghi tồn tại bên trong bộ đệm của server. Thông thường, một máy chủ DNS sẽ lưu các bản ghi DNS để ngăn chặn việc tiêu thụ thêm băng thông và giảm tải cho các máy chủ DNS khác.

### Các DNS Record thường dùng

- **SOA record** : Là bản ghi chứa các thông tin quan trọng về tên miền như email admin, time to live mặc định,… Một tệp tin zone chỉ được phép chứa một mẩu tin SOA và phải nằm ở vị trí đầu tiên trước các mẩu tin khác.

- **NS record** : Là bản ghi chỉ tới IP của Authoriative Name Server, có thể có nhiều NS Record. Một tên miền thường có nhiều bản ghi NS chỉ đến nhiều Authoriative Name Server khác nhau nhằm mục đích dự phòng khi có sự cố xảy ra.

- **A record** : Là DNS record đơn giản nhất và được dùng nhiều nhất dùng để trỏ tên miền tới một địa chỉ IPv4 cụ thể.

- **AAAA record** : Cũng giống như bản ghi A dùng để ánh xạ một tên miền tới một địa chỉ, nhưng khác với bản ghi A trỏ tới địa chỉ IPv4 thì bản ghi AAAA sẽ trỏ tới địa chỉ IPv6.

- **PTR Record** : Là bản ghi ngược lại hoàn toàn với A Record, bản ghi này map từ IP sang tên domain.

- **CNAME record** : Là bản ghi tạo một bí danh (alias) cho một tên miền cụ thể, để điều hướng một domain tới một domain khác, vì thế nó có value luôn là tên một domain chứ không phải IP.

- **SRV record** : Là bản ghi chứa thông tin về host và port của các dịch vụ như là VoIP, instant messaging,...

- **MX record** : Là bản ghi sử dụng để trỏ tên miền đến mail server. MX Record chỉ định server nào quản lý các dịch vụ Email của tên miền đó.

- **TXT Record** : Là bản ghi chứa thông tin mà con người có thể đọc hiểu được về một domain, có thể có nhiều TXT Record cho một domain.

## Khái niệm DHCP

DHCP là viết tắt của Dynamic Host Configuration Protocol, là một giao thức mạng được sử dụng để tự động cấp phát các thông số mạng như địa chỉ IP, địa chỉ Gateway, địa chỉ DNS cho các thiết bị trên mạng.

DHCP cung cấp một cách dễ dàng và tiện lợi để quản lý địa chỉ IP trong mạng, giúp giảm tải cho quản trị viên mạng và tránh sự xung đột giữa các địa chỉ IP trong mạng. Nó cũng hỗ trợ tính năng như tự động cấp lại địa chỉ IP khi cần, giữ lại cấu hình mạng cho máy tính khi nó được tắt và bật lại.

DHCP giao tiếp bằng UDP và sử dụng port 67 và 68. DHCP server sử dụng port 67 để nghe thông tin từ các client và sử dụng port 68 để reply thông tin

### Các thông điệp giao tiếp giữa DHCP server và DHCP client

- **DHCP Discover** : Đây là gói tin yêu cầu cấp phát địa chỉ IP để truy cập mạng của DHCP client gửi đến DHCP server.

- **DHCP Offer** : Đây là gói tin phản hồi của DHCP Server gửi cho client sau khi nhận được gói DISCOVER. Gói tin này chứa địa chỉ IP và các thông tin cấu hình TCP/IP bổ sung.

- **DHCP Request** : Đây là gói tin Client gửi cho DHCP server về việc đã nhận được thông tin địa chỉ IP trong gói DHCP Offer.

- **DHCP Acknowledge** : Đây là gói tin mà DHCP Server gửi cho client để xác thực việc client chấp nhận DHCP Request. Khi này, DHCP Server sẽ tiến hành định hướng các thông số cài đặt để client có thể kết nối mạng TCP/IP và hoàn thành quy trình cấp phát.

- **DHCP Nak** : Đây là gói tin mà DHCP server gửi cho Client trong trường hợp địa chỉ IP đã được sử dụng, hoặc hết giá trị. Đồng thời yêu cầu Client phải thực hiện quy trình cấp phát lại từ đầu.

- **DHCP Decline** : Đây là gói tin từ các thiết bị client gửi đến cho DHCP Server khi mà các thông tin được trả về từ DHCP Server không có giá trị. Nó sẽ tiến hành gửi các yêu cầu mới cho đến khi nhận được ip thành công.

- **DHCP Release** : Là gói tin mà DHCP Client gửi đến một DHCP Server để giải phóng địa chỉ IP, các thông tin khác và xóa tất cả những thông tin đã được cấp phát.

### Các bước hoạt động của DHCP :

- **Bước 1**: Khi muốn kết nối với mạng thiết bị sẽ gửi yêu cầu DHCP DISCOVER đến máy chủ.

- **Bước 2**: Sau khi DHCP Server nhận được gói tin nó sẽ tìm địa chỉ IP khả dụng rồi cung cấp cho thiết bị cùng với gói DHCP OFFER.

- **Bước 3**: Sau khi nhận được địa chỉ, thiết bị sẽ phản hồi với máy chủ bằng một gói tin DHCP REQUEST.

- **Bước 4**: Client nhận dữ liệu từ Port 68 và đưa IP vào DHCP Client. Sau đó DHCP Client sẽ gửi lại một bản tin Request là đồng ý sử dụng IP đó để DHCP Server xác nhận

- **Bước 5**: DHCP Server nhận được thông tin từ DHCP Client sẽ gửi lại một bản tin ACK để xác nhận là quá trình đã thành công.

## Tổng quan về SSH

SSH (hay Secure Shell) là một giao thức mạng được mã hoá để vận hành các dịch vụ mạng một cách an toàn. Giao thức này cung cấp một kênh kết nối bảo mật trong mô hình kết nối client-server. SSH sử dụng cổng TCP tiêu chuẩn là 22. Việc sử dụng giao thức SSH để kết nối sẽ tránh được các rủi ro trong việc nghe lén và đánh cắp thông tin.

Để thực hiện kết nối SSH, có thể làm một vài cách như sau:

- Sử dụng mật khẩu để xác thực.
- Sử dụng cơ chế Key pairs.

### Thực hiện SSH bằng mật khẩu

Sử dụng lệnh :

`ssh <user>@<ip-address>`

![](https://news.cloud365.vn/wp-content/uploads/2019/07/ssh03new.png)

Nếu là lần kết nối đầu tiên, thì máy sẽ hỏi lại có muốn tiếp tục hay không. Chỉ cần gõ YES, sau đó nhập pass. Như vậy, đã thực hiện xong việc kết nối.

**Lưu ý** : Nếu cổng kết nối khác 22 , ta có thể sử dụng option `-p` để chọn cổng :

```
ssh -p <port-number> <user>@<ip-address>
```

### Thực hiện SSH bằng Key pairs

Cơ bản thì ở máy khách sẽ tiến hành tạo cặp key là private key và public key, sau đó sẽ gửi key public tới máy chủ và giữ lại private key. Khi muốn thực hiện đăng nhập từ xa, máy khách sẽ gửi yêu cầu kèm key private tới máy chủ. Máy chủ sẽ tiến hành kiểm tra private key có trùng với public Key không. Nếu có thì sẽ đăng nhập thành công.

#### Bước 1 : Tạo key pairs

Tạo cặp khóa bằng câu lệnh `ssh-keygen`

![](https://news.cloud365.vn/wp-content/uploads/2019/07/ssh05new.png)

Ở ô hỏi đầu tiên, yêu cầu nhập thư mục lưu trữ file key (mặc định là `/home/<user>/.ssh/id_rsa`). Tiếp theo là mật khẩu cho key (passphrase), bước này sẽ khiến bạn phải xác thực lại key bằng mật khẩu. Nếu không muốn nhập mật khẩu, nhấn Enter để bỏ qua.

#### Bước 2 : Gửi key public

Bước này có thể thực hiện bằng cách sao chép thủ công, tuy nhiên có thể sử dụng câu lệnh `ssh-copy-id`

```
ssh-copy-id <user>@<ip address>
```

![](https://news.cloud365.vn/wp-content/uploads/2019/07/ssh06new.png)

Máy yêu cầu cần xác thực bạn có muốn tiếp tục kết nối hay không. Bạn chỉ cần gõ **YES**. Tiếp tục, máy yêu cầu bạn nhập mật khẩu cho máy nhận public key (máy chủ), nhập mật khẩu vào là bạn đã hoàn thành xong việc gửi public key tới máy nhận.

Key public được gửi tới sẽ nằm trong thư mục `/home/<user>/.ssh/authorized_keys`

### Quản lý khóa bằng SSH Agent

SSH Agent được sử dụng để quản lý việc truy cập vào các máy tính sử dụng các khóa private và các passphrase. Khi đã thêm các khóa vào ssh-agent thì lúc truy cập chúng ta không cần phải khai báo passphrase một lần nữa.

Thông thường SSH Agent sẽ tự động khởi động, nếu không có thể sử dụng câu lệnh sau :

```
eval $(ssh-agent)
```

Sau đó sử dụng câu lệnh `ssh-add` để thêm khóa vào ssh-agent

```
ssh-add <private-key-folder>
```

### Đơn giản hóa kết nối SSH bằng file config

ssh (ssh client) khi chạy, thực hiện các kết nối - nó sẽ tìm file cấu hình tại đường dẫn `home/<user>/.ssh/config` (theo mặc định, nó không có sẵn nên ta sẽ phải tạo), nếu có file này nó dùng file đó thiết lập các thông tin bổ sung kết nối.

Cấu trúc của file config như sau :

```
Host ten-rat-dep // Đặt tên
    Port 2222 // Số port
    HostName 192.168.1.52 // Địa chỉ remote server
    User testuser // User sẽ đăng nhập
    PreferredAuthentications publickey // Bật chế độ xác thực bằng SSH key trước
    IdentityFile "\id_rsa"  // Vị trí private key
```

## Tổng quan về rsync

Rsync (Đồng bộ hóa từ xa) là lệnh được sử dụng phổ biến nhất để sao chép và đồng bộ hóa các tệp và thư mục từ xa cũng như cục bộ trong các hệ thống Linux/Unix.

### Một số ưu điểm và tính năng của lệnh rsync

- Nó giúp sao chép và đồng bộ hóa hiệu quả các tập tin đến hoặc từ một hệ thống từ xa.
- Hỗ trợ sao chép liên kết, thiết bị, chủ sở hữu, nhóm và quyền.
- Nó nhanh hơn scp (Bản sao an toàn) vì rsync sử dụng giao thức cập nhật từ xa cho phép chỉ chuyển sự khác biệt giữa hai tập hợp tệp. Lần đầu tiên, nó sao chép toàn bộ nội dung của một tệp hoặc một thư mục từ nguồn đến đích nhưng từ lần sau, nó chỉ sao chép các khối và byte đã thay đổi tới đích.
- Rsync tiêu thụ ít băng thông hơn vì nó sử dụng phương pháp nén và giải nén trong quá trình gửi và nhận dữ liệu ở cả hai đầu.

### Cú pháp cơ bản của lệnh Rsync

```
rsync [options] <source> <destination>
```

Một số tùy chọn phổ biến được sử dụng với lệnh Rsync :

- **`-v`** : chi tiết
- **`-r`** : sao chép dữ liệu một cách đệ quy (nhưng không bảo toàn dấu thời gian và quyền trong khi truyền dữ liệu.)
- **`-a`** : chế độ lưu trữ, cho phép sao chép các tệp một cách đệ quy và nó cũng lưu giữ các liên kết tượng trưng, quyền đối với tệp, quyền sở hữu của người dùng và nhóm và dấu thời gian.
- **`-z`** : nén dữ liệu tập tin.
- **`-h`** : hỗ trợ đầu ra ở định dạng mà con người có thể đọc được.

### Sao chép và đồng bộ hóa tệp/thư mục cục bộ

```
rsync -avzh backup.tar /tmp/backups/
```

Lênh trên sẽ copy file `backup.tar` vào thư mục `/tmp/backups/` . Nếu thư mục đích chưa có sẽ được tạo tự động.

### Sao chép/đồng bộ hóa tệp và thư mục đến (hoặc từ) máy chủ

```
rsync -avzh rpmpkgs/ root@10.10.10.12:/home/
```

Lệnh trên copy thư mục `rpmpkgs` từ Server Local lên Remote Server có IP `10.10.10.12`, lưu ở thư mục `/home/`

```
rsync -avzh root@10.10.10.12:/home/tarunika/rpmpkgs /tmp/myrpms
```

Lệnh trên sẽ copy dữ liệu ở thư mục `/home/tarunika/rpmpkgs` trên Remote Server `10.10.10.12` về máy Server Local lưu ở thư mục `/tmp/myrpms`

### Copy file/folder từ Remote Server về Local Server qua SSH

Với Rsync, bạn có thể transfer qua giao thức SSH, qua đó dữ liệu được bảo mật an toàn hơn. Để xác định giao thức sẽ sử dụng với rsync, bạn cần thêm tùy chọn `-e` cùng với tên giao thức, ở đây là ssh.

```
rsync -avzhe ssh root@10.10.10.12:/root/access.log /home/zhost/log/
```

Lệnh trên copy file `/root/access.log` trên Remote Server `10.10.10.12` về thư mục `/home/zhost/log/` trên máy Local.

Copy file/folder từ Local lên Remote Server qua SSH, ta cũng sẽ làm tương tự :

```
rsync -avzhe ssh /home/zhost/data.tar root@10.10.10.12:/backups/
```

### Hiển thị tiến trình trong khi Copy dữ liệu

Để hiển thị tiến độ transfer dữ liệu, bạn có thể sử dụng option `--progress`

```
rsync -avzhe ssh --progress /home/rpmpkgs root@10.10.10.12:/root/rpmpkgs
```

### Tùy chọn --include, --exclude, --delete

Hai tùy chọn `--include` và `--exclude` cho phép chúng ta thêm/bớt file hoặc thư mục trong quá trình đồng bộ dữ liệu.

```
rsync -avze ssh --include 'R*' --exclude '*' root@10.10.10.12:/var/lib/rpm/ /root/rpm
```

Tuỳ chọn `--delete` cho phép bạn xóa một file hoặc thư mục không có ở thư mục nguồn, mà lại xuất hiện ở thư mục đích trong quá trình copy.

```
rsync -avzhe ssh --progress  --delete /home/rpmpkgs root@10.10.10.12:/root/rpmpkgs
```

### Xóa dữ liệu ở nguồn sau khi copy thành công

Để rsync tự động xóa dữ liệu sau khi đồng bộ lên server đích thành công, bạn có thể sử dụng option `--remove-source-files`

```
rsync -avzhe ssh --remove-source-files /home/rpmpkgs root@10.10.10.12:/root/rpmpkgs
```

## Tổng quan về scp

SCP (secure copy – bản sao an toàn) là một tiện ích dòng lệnh cho phép người dùng sao chép các tệp và thư mục trên Linux hệ thống cục bộ đến một hệ thống từ xa và ngược lại, hoặc giữa hai hệ thống từ xa từ hệ thống cục bộ.

SCP dùng ssh để di chuyển dữ liệu nên cả thông tin và mật khẩu tệp đều được mã hoá để bảo vệ quyền riêng tư của chủ sở hữu.

### Cú pháp cơ bản của scp

```
scp [options] <source> <destination>
```

Một số Option thường sử dụng trong SCP như:

- **`-r`** : Sử dụng cho việc truyền các thư mục.
- **`-P`** : Sử dụng để khai báo cổng ssh máy chủ từ xa.
- **`-p`** : sử dụng sẽ giúp file giữ nguyên các thuộc tính như thời gian chỉnh sửa file, thời gian truy cập file…
- **`-C`** : Sử dụng để nén dữ liệu trước khi gửi.
- **`-c`** : Sử dụng để chọn thuật toán mã hoá để truyền dữ liệu.
- **`-v`** : Cho ra kết quả output với nhiều thông tin hơn về những gì chương trình thực thi ở background.Điều này thường sẽ có ích khi chương trình lỗi hoặc không thể hoàn tất request đến.

### Copy file từ Local Server sang Remote Server

Copy file `test1.txt` từ Local server sang Remote server – `10.10.10.12`:

```
scp test1.txt root@10.10.10.12:/root
```

Trong đó:

- **`test1.txt`** là Source file
- **`root`** là user trên Remote server
- **`10.10.10.12`** là IP của Remote server
- **`/root`** là đường dẫn đích trên Remote server mà file `test1.txt` được copy đến.

### Copy file từ Remote Server sang Local Server

```
scp root@10.10.10.12:/root/test2.txt /home
```

Lệnh trên copy file `test2.txt` từ thư mục `/root` của Remote server về thư mục `/home` của Local server.

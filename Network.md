## Mô hình OSI

![](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8d/OSI_Model_v1.svg/476px-OSI_Model_v1.svg.png)

Mô hình OSI (Open Systems Interconnection Reference Model)

### Tầng ứng dụng (Application Layer)

Tầng ứng dụng là lớp trên cùng, xác định giao diện giữa người sử dụng và môi trường OSI. Tầng ứng dụng được sử dụng bởi phần mềm người dùng cuối như trình duyệt web và ứng dụng email. Nó cung cấp các giao thức cho phép phần mềm gửi, nhận thông tin và trình bày dữ liệu có ý nghĩa cho người dùng.

1 vài ví dụ về giao thức ở lớp ứng dụng là HTTP, POP, SMTP, DNS, FTP...

### Tầng trình bày (Presentation Layer)

Tầng này sẽ giải quyết các vấn đề liên quan đến các cú pháp và ngữ nghĩa của thông tin được truyền, nhằm biểu diễn thông tin phù hợp với thông tin làm việc của mạng và ngược lại.
Nó cung cấp các dịch vụ và các cơ chế chuyển đổi, mã hóa, nén và định dạng dữ liệu để đảm bảo rằng dữ liệu được truyền và nhận một cách chính xác, an toàn và hiệu quả giữa các ứng dụng và hệ thống khác nhau.

### Tầng phiên (Session Layer)

Đây là lớp chịu trách nhiệm đóng mở giao tiếp giữa hai thiết bị. Tầng phiên đảm bảo rằng phiên vẫn mở đủ lâu để chuyển tất cả dữ liệu đang được trao đổi, và sau đó nhanh chóng đóng phiên để tránh lãng phí tài nguyên.

Tầng này cung cấp liên kết giữa hai đầu cuối sử dụng dịch vụ phiên để đồng bộ trao đổi dữ liệu và khi kết thúc thì giải phóng liên kết. Trong phương thức truyền đồng thời hay luân phiên, quá trình này sử dụng token để truyền dữ liệu, đồng bộ hóa và hủy bỏ liên kết. Nhờ thiết lập nhiều điểm đồng bộ hóa trong hội thoại nên khi xảy ra sự cố, hội thoại có thể được khôi phục từ một điểm đồng bộ hóa đã thỏa thuận.

### Tầng vận tải (Transport Layer)

Tầng này chịu trách nhiệm quản lý (giao tiếp) đầu cuối end - to - end. Điều này bao gồm việc lấy dữ liệu từ lớp phiên và chia nó thành các phần được gọi là phân đoạn trước khi gửi đến tầng Network. Ở phía nhận, tầng này có trách nhiệm tập hợp các phân đoạn thành dữ liệu mà tầng phiên có thể hiểu được.
Tầng vận tải cũng chịu trách nhiệm kiểm soát luồng và kiểm soát lỗi. Tầng này còn có thể thực hiện việc ghép kênh một vài liên kết vào chung một liên kết nối giúp giảm giá thành.

### Tầng mạng (Network Layer)

Trách nhiệm của lớp mạng Network là quyết định xem dữ liệu sẽ đến đi thiết bị ở mạng khác như thế nào. Lớp này nắm các thành phần như việc xác định tuyến, địa chỉ và các giao thức logic. Nếu hai thiết bị giao tiếp trên cùng một mạng, thì tầng mạng là không cần thiết

Tầng mạng chia nhỏ các phân đoạn từ lớp truyền tải thành các đơn vị nhỏ hơn, được gọi là gói, trên thiết bị của người gửi và tập hợp lại các gói này trên thiết bị nhận. Tầng mạng cũng tìm ra con đường vật lý tốt nhất để dữ liệu đến đích của nó; điều này được gọi là định tuyến.

### Tầng Liên kết dữ liệu (Data Link Layer)

Tầng này rất giống tầng mạng, ngoại trừ tầng này sẽ quyết định xem dữ liệu đi đến thiết bị nằm trong một mạng như thế nào (node to node).Tầng liên kết dữ liệu lấy các gói từ tầng mạng và chia chúng thành các phần nhỏ hơn gọi là khung . Tầng liên kết dữ liệu cũng chịu trách nhiệm điều khiển luồng và điều khiển lỗi trong giao tiếp nội mạng

### Tầng vật lý (Physical Layer)

Tại đây thì các đối tượng thực hiện giao tiếp với nhau thông qua một đường truyền vật lý. Lớp này bao gồm các thiết bị vật lý liên quan đến việc truyền dữ liệu, chẳng hạn như cáp và thiết bị chuyển mạch. Đây cũng là lớp nơi dữ liệu được chuyển đổi thành một luồng bit, là một chuỗi gồm các số 1 và 0. Lớp vật lý của cả hai thiết bị cũng phải đồng ý về một quy ước tín hiệu để các số 1 có thể được phân biệt với các số 0 trên cả hai thiết bị.

## Mô hình TCP/IP

![](https://media.geeksforgeeks.org/wp-content/uploads/20230417045622/OSI-vs-TCP-vs-Hybrid-2.webp)

### Tầng ứng dụng (Application Layer)

- Tầng Ứng dụng cung cấp các ứng dụng cho phép trao đổi dữ liệu chuẩn hóa giữa 2 máy khác nhau thông qua các dịch vụ mạng khác nhau như HTTP, HTTPS, FTP, SSH, SMTP.

### Tầng giao vận (Transport Layer)

- Chịu trách nhiệm duy trì thông tin liên tạc end-to-end trên toàn mạng.

- Tầng này có 2 giao thức chính là TCP và UDP :

  - TCP sẽ đảm bảo chất lượng truyền gửi gói tin, nhưng tốn khá nhiều thời gian để kiểm tra đầy đủ thông tin từ thứ tự dữ liệu cho đến việc kiểm soát vấn đề tắc nghẽn lưu lượng dữ liệu

  - UDP có thấy tốc độ truyền tải nhanh hơn nhưng lại không đảm bảo được chất lượng dữ liệu được gửi đi

### Tầng mạng (Internet Layer)

- Trong tầng này sẽ có nhiệm vụ xử lý các network packet và kết nối các mạng độc lập. Từ đó xác định tuyến đường (định tuyến) vận chuyển các packet qua network

- Các giao thức tần này bao gồm : IP, ICMP,..

### Tầng vật lý (Network Access Layer - Link Layer)

- Có khá nhiều cách gọi như Network Access Layer, Link Layer, Physical Layer

- Nó là sự kết hợp tầng Data Link và Physical trong mô hình OSI. Chịu trách nhiệm truyền dữ liệu giữa hai thiết bị trong cùng một mạng. Tại đây, các gói dữ liệu được đóng vào khung (gọi là Frame) và được định tuyến đi đến đích đã được chỉ định ban đầu.

## So sánh mô hình OSI và TCP/IP

| Mô hình OSI                                                                                                                     | Mô hình TCP/IP                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nhiều người cho rằng đây là mô hình cũ, chỉ để tham khảo, số người sử dụng hạn chế hơn so với TCP/IP                            | Được chuẩn hóa, nhiều người tin cậy và sử dụng phổ biến trên toàn cầu                                                                                                 |
| Mỗi tầng khác nhau sẽ thực hiện một nhiệm vụ khác nhau, không có sự kết hợp giữa bất cứ tầng nào                                | Tầng ứng dụng là sự kết hợp của tầng ứng dụng, trình bày, phiên trong mô hình OSI. Tầng vật lý là sự kết hợp của tầng vật lý, tầng liên kết dữ liệu trong mô hình OSI |
| Phát triển mô hình trước sau đó sẽ phát triển giao thức                                                                         | Các giao thức được thiết kế trước sau đó phát triển mô hình                                                                                                           |
| Tiếp cận theo chiều dọc. Nghĩa là các tầng phải giao tiếp với nhau theo thứ tự cụ thể từ tầng trên xuống tầng dưới và ngược lại | Tiếp cận theo chiều ngang. Nghĩa là các tầng có thể giao tiếp trực tiếp với nhau, không cần phải qua các tầng trung gian                                              |

## Giao thức TCP

- là giao thức hướng kết nối nghĩa là khi muốn truyền dữ liệu thì phải thiết lập kết nối trước

- Hỗ trợ cơ chế Full-duplex (truyền và nhận dữ liệu cùng 1 lúc)

- Cung cấp cơ chế đánh số thứ tự gói tin (sequencing) cho các đơn vị dữ liệu được truyền, sử dụng để sắp xếp các gói tin chính xác ở điểm nhận và loại bỏ gói tin trùng lặp.

- Cung cấp cơ chế báo nhận (Acknowledgement) : Khi A gửi dữ liệu cho B, B nhận được thì gửi gói tin cho A xác nhận là đã nhận. Nếu không nhận được tin xác nhận thì A sẽ gửi cho đến khi B báo nhận thì thôi.

- Phục hồi dữ liệu bị mất trên đường truyền ( A gửi B mà không thấy xác nhận sẽ gửi lại) .

- Có các cơ chế điều khiển luồng thích hợp (flow control) để tránh nghẽn xảy ra.

### Quá trình thiết lập kết nối (Three-way handshake)

![](https://blog.confirm.ch/wp-content/uploads/2018/06/tcp_states_connect.jpg)

1. Đầu tiên, server sẽ phải ở trạng thái kết nối Listen. Nó sẽ đợi kết nối từ một TCP và cổng bất kỳ ở xa.

2. Khi client muốn thực hiện một phiên kết nối tới server, client sẽ gửi một TCP segment với cờ SYN được thiết lập. Trạng thái kết nối lúc này sẽ là SYN_SENT

3. Sau khi nhận được TCP segment của client, server phản hồi cho client gói TCP segment với cờ SYN/ACK được thiết lập. Trạng thái kết nối lúc này là SYN_RECEIVED

4. Client sau khi nhận TCP segment của server, nó phản hồi cho server gói TCP segment với cờ ACK được thiết lập. Trạng thái kết nối lúc này là ESTABLISHED

5. Lúc này, client và server có thể tiến hành gửi dữ liệu

### Quá trình hủy kết nối (Four-way Handshake)

![](https://blog.confirm.ch/wp-content/uploads/2018/06/tcp_states_terminate.jpg)

Quá trình đóng kết nối có thể thực hiện bởi một trong hai bên, ở đây giả sử trường hợp phía client là bên yêu cầu đóng kết nối.

1. Phía client gửi TCP segment với cờ FIN được thiết lập tới server và chuyển trạng thái sang FIN_WAIT_1

2. Server nhận được yêu cầu đóng kết nối từ client và phản hồi với TCP segment với cờ ACK được thiết lập. Sau đó, nó chuyển trạng thái kết nối sang CLOSE_WAIT

3. Khi nhận được TCP segment từ server, client sẽ chuyển sang trạng thái FIN_WAIT_2. Tại thời điểm này, client đã đóng kết nối.

4. Sau khi server gửi TCP segment với cờ ACK được thiết lập, nó sẽ tiếp tục gửi 1 TCP segment với cờ FIN được thiết lập tới client. Sau đó chuyển sang trạng thái LAST_ACK

5. Client nhận được segment và phản hồi bằng một segment với cờ ACK được thiết lập, trạng thái lúc này của client là TIME_WAIT.

6. Server sau khi nhận được segment sẽ đóng kết nói , trạng thái lúc này là CLOSED.

7. Client ở trạng thái TIME_WAIT trong một khoảng thời gian sau đó chuyển sang trạng thái CLOSED

## Giao thức UDP

- là giao thức truyền tải hướng không kết nối (nghĩa là có gói tin nào đẩy ngay vào đường truyền mà không cần thiết lập kết nối trước)

- Không đảm bảo tính tin cậy khi truyền dữ liệu và không có cơ chế phục hồi dữ liệu ( nó không quan tâm gói tin có đến đích hay không, không biết gói tin có bị mất mát trên đường đi hay không ).

- Không thực hiện các biện pháp đánh số thứ tự cho các đơn vị dữ liệu được truyền

- UDP là lựa chọn tối ưu khi yêu cầu tốc độ và không cần quan tâm đến sửa lỗi

## IPv4

### Cấu trúc địa chỉ IPv4

<span style="display:block;text-align:center">![](https://bkhost.vn/wp-content/uploads/2022/03/cau-truc-dia-chi-ipv4.jpg)</span>

- Địa chỉ IPv4 sử dụng địa chỉ 32 bit và chia ra làm 4 cụm, còn được gọi là octet (1 octet = 1 byte = 8 bit) với các ký tự số được phân cách bằng dấu chấm `.`.

- Địa chỉ IPv4 được biểu diễn bằng 4 con số ở dạng thập phân tượng trưng cho 4 octet.

- Địa chỉ IPv4 gồm 2 phần là phần mạng và phần host.

### Phân lớp địa chỉ IPv4

<span style="display:block;text-align:center">![](https://www.cs.emory.edu/~cheung/Courses/455/Syllabus/4b-internet/FIGS/ip-addresses.gif)</span>

#### Lớp A

- Có phần mạng là 8 bit đầu và phần host là 24 bit sau.
- Bit đầu tiên của phần mạng luôn là 0
- Dải mạng từ: 0.0.0.0 -> 127.255.255.255
- Mạng 127.0.0.0 được sử dụng làm mạng loopback
- Phần host có 24 bit, mạng lớp A có 2^24-2 host

#### Lớp B

- Có phần mạng là 16 bit đầu và phần host là 16 bit sau
- 2 bit đầu tiên của phần mạng luôn là 10
- Dải mạng từ 128.0.0.0 -> 191.255.255.255
- Phần host có 16 bit, mạng lớp B có 2^16-2 host

#### Lớp C

- Có phần mạng là 24 bit đầu và phần host là 8 bit sau
- 3 bit đầu tiên của phần mạng luôn là 110
- Dải mạng từ 192.0.0.0 -> 223.255.255.255
- Phần host có 8 bit, mạng lớp C có 2^8-2 host

#### Lớp D

- 4 Bit đầu của octet đầu tiên là 1110
- Dải mạng từ 224.0.0.0 -> 239.255.255.255
- Được dùng làm địa chỉ multicast. Ví dụ: 224.0.0.5 dùng cho OSPF; 224.0.0.9 dùng cho RIPv2

#### Lớp E

- 4 bit đầu của octet đầu tiên là 1111
- Dải mạng từ 224.0.0.0 trở đi
- Được sử dụng cho mục đích dự phòng

### Cách chia địa chỉ Ipv4

Ta có ví dụ như sau :

<span style="display:block;text-align:center">![](https://study-ccna.com/wp-content/uploads/vlsm.webp)</span>

- `Bước 1` : Xác định số host cần thiết
- `Bước 2` : Xác định lớp địa chỉ dựa trên số host cần thiết
- `Bước 3` : Xác định số bit dành cho host của mỗi mạng con.

- `Bước 4` : Tính subnet mask
- `Bước 5` : Tính bước nhảy với công thức 2^bit dành cho host

- `Bước 6` : Xác định network address, broadcast address và dải địa chỉ.

Áp dụng vào làm vd :

Ta có số lượng host cần như sau :

- HQ LAN : 50 host
- BRANCH 1 : 30 host
- BRANCH 2 : 20 host
- WAN 1 (HQ -> BRANCH 1) : 2 host
- WAN 2 (HQ -> BRANCH 2) : 2 host
- WAN 3 (BRANCH 1 -> BRANCH 2) : 2 host

Ở ví dụ trên, cần tổng cộng 106 host , do đó ta sẽ sử dụng địa chỉ Lớp C. Ta sẽ sử dụng địa chỉ 192.168.1.0/24

Sau đó , tính toán số bit dành cho host của mỗi mạng con :

- HQ LAN (50 host) => cần 6 bit dành cho host (2^6 -2 sẽ cho ta 62 địa chỉ khả dụng dành cho host)
- BRANCH 1 (30 host), BRANCH 2 (20 host) => cần 5 bit dành cho host (2^5 -2 sẽ cho ta 30 địa chỉ khả dụng dành cho host)
- WAN 1, WAN 2, WAN 3 (2 host) => cần 2 bit dành cho host (2^2 -2 sẽ cho ta 2 địa chỉ khả dụng dành cho host)

Tính toán subnet mask :

- HQ LAN : 6 bit dành cho host => Subnet mask : /26 (255.255.255.192)
- BRANCH 1, BRANCH 2 : 5 bit dành cho host => Subnet mask : /27 (255.255.255.224)
- WAN 1, WAN 2, WAN 3 : 2 bit dành cho host => Subnet mask : /30 (255.255.255.252)

Xác định dải địa chỉ :

- HQ LAN: Bắt đầu với địa chỉ ban đầu là 192.168.1.0/24, ta mượn 2 bit để có 6 bit dành cho host => có 2^2 (4) subnet được chia ra từ địa chỉ ban đầu.

  - Sử dụng địa chỉ mạng 192.168.1.0/26 cho HQ LAN

  - Các subnet còn lại được sử dụng để tiếp tục chia.

- BRANCH 1 : sử dụng subnet tiếp theo 192.168.1.64/26 (Bước nhảy 64) để chia, ta mượn 1 bit để có 5 bit dành cho host => Có 2^1 (2) subnet được chia ra từ địa chỉ 192.168.1.64/26

  - Sử dụng địa chỉ mạng 192.168.1.64/27 cho BRANCH 1

  - Còn lại subnet 192.168.1.96/27 (Bước nhảy 32) được sử dụng để tiếp tục chia.

- BRANCH 2 : sử dụng subnet tiếp theo 192.168.1.96/27 để chia,không cần mượn thêm bit nào để có 5 bit dành cho host => Sử dụng 192.168.1.96/27 cho BRANCH 2

- WAN 1 : Sử dụng subnet tiếp theo được chia từ địa chỉ 192.168.1.0/24 là 192.168.1.128/26 để chia, ta mượn 4 bit để có 2 bit dành cho host => có 2^4 (16) subnet được chia từ địa chỉ 192.168.1.128/26

  - sử dụng địa chỉ mạng 192.168.1.128/30 cho WAN1

  - Các subnet còn lại được sử dụng để tiếp tục chia.

- WAN 2 : sử dụng subnet tiếp theo 192.168.1.132/30 để chia không cần mượn thêm bit nào để có 2 bit dành cho host => Sử dụng 192.168.1.132/30 cho WAN 2

- WAN 3 : sử dụng subnet tiếp theo 192.168.1.136/30 để chia không cần mượn thêm bit nào để có 2 bit dành cho host => Sử dụng 192.168.1.136/30 cho WAN 3

Tổng quát lại :

| Tên      | Số host yêu cầu | Số host khả dụng | Địa chỉ       | Subnet mask           | Dải địa chỉ khả dụng          | Broadcast     |
| -------- | --------------- | ---------------- | ------------- | --------------------- | ----------------------------- | ------------- |
| HQ LAN   | 50              | 62               | 192.168.1.0   | 255.255.255.192 (/26) | 192.168.1.1 - 192.168.1.62    | 192.168.1.63  |
| BRANCH 1 | 30              | 30               | 192.168.1.64  | 255.255.255.224 (/27) | 192.168.1.65 - 192.168.1.94   | 192.168.1.95  |
| BRANCH 2 | 20              | 30               | 192.168.1.96  | 255.255.255.224 (/27) | 192.168.1.97 - 192.168.1.126  | 192.168.1.127 |
| WAN 1    | 2               | 2                | 192.168.1.128 | 255.255.255.252 (/30) | 192.168.1.129 - 192.168.1.130 | 192.168.1.131 |
| WAN 2    | 2               | 2                | 192.168.1.132 | 255.255.255.252 (/30) | 192.168.1.133 - 192.168.1.134 | 192.168.1.135 |
| WAN 3    | 2               | 2                | 192.168.1.136 | 255.255.255.252 (/30) | 192.168.1.137 - 192.168.1.138 | 192.168.1.139 |

## IPv6

IPv6 là giao thức Internet Protocol (IP) tiếp theo, được thiết kế để giải quyết vấn đề về hạn chế số lượng địa chỉ IP có sẵn trong IPv4, vì nó chỉ có khoảng 4,3 tỷ địa chỉ khả dụng

### Cấu trúc IPv6

Địa chỉ IPv6 dài 128 bit, được chia làm 8 nhóm, mỗi nhóm gồm 16 bit (2 byte), được ngăn cách với nhau bằng dấu hai chấm “:”. Mỗi nhóm được biểu diễn bằng 4 số hexa.

Ví dụ: FEDC:BA98:768A:0C98:FEBA:CB87:7678:1111

<span style="display:block;text-align:center">![](https://docs.oracle.com/cd/E18752_01/html/816-4554/figures/basic-IPv6-address.png)</span>

Địa chỉ IPv6 có 3 thành phần :

- Site Prefix : được biểu thị trong 3 octet đầu tiên. Đây là phần định danh cho mạng được quảng bá trên Internet, tương tự với phần mạng trong IPv4

- Subnet ID: là phần định danh mạng con. Nó làm việc tương tự như cách làm việc của mạng con trong IPv4

- Interface ID: được biểu thị trong 4 octet cuối. Đây là phần định danh cho cổng mạng (thiết bị mạng). Interface ID chỉ nhận dạng duy nhất một Host riêng trong mạng

Có thể rút gọn địa chỉ IPv6 theo quy tắc sau :

- Cho phép bỏ các số 0 nằm trước mỗi nhóm (octet)

- Thay bằng số 0 cho nhóm có toàn số 0

- Thay bằng dấu “::” cho các nhóm liên tiếp nhau có toàn số 0. Chú ý: Dấu “::” chỉ sử dụng được 1 lần trong toàn bộ địa chỉ IPv6.

### Phân loại địa chỉ IPv6

Ipv6 được chia thành 3 loại chính :

- Unicast : là loại địa chỉ IPv6 được sử dụng trong một mạng nội bộ (private network). Địa chỉ local unicast không được phân bố trên toàn cầu và chỉ có thể được sử dụng trong mạng cụ thể đó.

- Multicast : là loại địa chỉ IPv6 được sử dụng để gửi tin tới nhiều thiết bị cùng một lúc. Địa chỉ multicast được dạng bắt đầu bằng FF.

- Anycast : là loại địa chỉ được sử dụng để gửi tin tới một thiết bị duy nhất trong một nhóm các thiết bị. Khi thông tin được gửi đến thông qua địa chỉ anycast, thông tin này sẽ được di chuyển một trong các thiết bị đó, thông thường sẽ là thiết bị gần nhất

## Cơ chế bonding

bonding là cơ chế nhóm từ 2 đến nhiều interface vật lý kết hợp thành 1 interface ảo gọi là bonding interface bằng cách sử dụng module kernel "bonding" của Linux nhằm tăng khả năng chịu lỗi, cân bằng tải , tăng băng thông của hệ thống.

### Các bonding mode

Có tổng cộng 7 bonding mode :

| Mode | <div style="width:100px">Tên mode</div> | Mô tả                                                                                                                                                                                                                                                                                                                                                                 | Khả năng chịu lỗi | Cân bằng tải |
| :--: | --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------: | :----------: |
|  0   | balance-rr                              | Áp dụng cơ chế Round-robin. Nó truyền các gói tin theo thứ tự tuần tự từ slave đầu tiên đến cuối cùng.Nếu có 2 interface thật và 2 gói tin đến, thì gói tin đầu tiên sẽ đi vào interface1 và gói tin thứ 2 sẽ đi vào interface2                                                                                                                                       |        Có         |      Có      |
|  1   | active-backup                           | Áp dụng cơ chế Active-backup. Chế độ này đặt một trong các interface vào trạng thái backup và sẽ chỉ hoạt động nếu interface đang hoạt động bị lỗi. Chỉ có một slave hoạt động trong một thời điểm. Một slave khác nhau sẽ được kích hoạt chỉ khi slave đang hoạt động bị lỗi                                                                                         |        Có         |    Không     |
|  2   | balance-xor                             | Áp dụng phép XOR: Thực hiện XOR giữa source MAC nguồn với source MAC đích. Nó sẽ lựa chọn cùng 1 slave cho 1 địa chỉ MAC. Cung cấp cân bằng tải và khả năng chịu lỗi                                                                                                                                                                                                  |        Có         |      Có      |
|  3   | broadcast                               | Toàn bộ gói tin sẽ được truyền trên tất cả slave interface. Chế độ này ít được sử dụng                                                                                                                                                                                                                                                                                |        Có         |    Không     |
|  4   | 802.3ad                                 | Tạo nhóm tập hợp các interface chia sẻ chung tốc độ và duplex. Có thể truyền và nhận gói tin trên các cổng đang hoạt động. Yêu cầu cần phải có switch tương thích với chuẩn 802.3ad                                                                                                                                                                                   |        Có         |      Có      |
|  5   | balance-tlb                             | Cân bằng tải thích ứng với quá trình truyền tin. Lưu lượng đi ra ngoài (outgoing) phân tán dựa trên tải hiện tại trên mỗi slave (tính toán liên quan tới tốc độ). Lưu lượng tới (Incomming) nhận bởi slave active hiện tại, nếu slave này bị lỗi khi nhận gói tin, các slave khác sẽ thay thế, MAC address của đường bond sẽ chuyển sang một trong các slave còn lại. |        Có         |      Có      |
|  6   | balance-alb                             | Cân bằng tải thích ứng. Là sự kết hợp giữa balance-tlb và receive load balancing(rlb) cho lưu lượng của ipv4. Cân bằng tải nhận đạt được nhờ kết hợp với ARP. Bondin driver sẽ chặn các bản tin phản hồi ARP gửi bởi hệ thống cụ bộ trên đường ra và ghi đè địa chỉ MAC nguồn bằng địa chỉ MAC của một trong các slaves trên đường bond.                              |        Có         |      Có      |

### Cấu hình

```
network:
  ethernets:
    enp1s0:
      dhcp4: false
      dhcp6: false
    enp7s0:
      dhcp4: false
      dhcp6: false
  bonds:
    bond0:
      addresses: [10.0.0.30/24]
      routes:
        - to: default
          via: 10.0.0.1
          metric: 100
      nameservers:
        addresses: [10.0.0.10]
      interfaces:
        - enp1s0
        - enp7s0
      parameters:
        mode: active
        mii-monitor-interval: 100
  version: 2
```

## Định tuyến là gì ?

là quá trình xác định đường đi đi của một gói tin và chuyển tiếp tới địa chỉ mạng đích. Việc định tuyến dựa vào một công cụ gọi là bảng định tuyến (routing table). Nguyên tắc là mọi gói tin IP khi đi đến router sẽ đều được tra bảng định tuyến, nếu đích đến của gói tin thuộc về một entry có trong bảng định tuyến thì gói tin sẽ được chuyển đi tiếp, nếu không, gói tin sẽ bị loại bỏ

### Định tuyến động vs định tuyến tĩnh

- Định tuyến tĩnh (static route):
  - Quản trị viên mạng nhập thủ công các tuyến tĩnh vào router.
  - Thay đổi cấu trúc liên kết mạng yêu cầu cập nhật thủ công cho tuyến.
  - Hành vi định tuyến có thể được kiểm soát chính xác.
- Định tuyến động(Dynamic route):
  - Giao thức định tuyến mạng tự động điều chỉnh các tuyến đường động khi cấu trúc liên kết hoặc lưu lượng thay đổi.
  - Bộ định tuyến tìm hiểu và duy trì các tuyến đường đến các điểm đến từ xa bằng cách trao đổi các bản cập nhật định tuyến.
  - Bộ định tuyến khám phá các mạng mới hoặc các thay đổi khác trong cấu trúc liên kết bằng cách chia sẻ thông tin bảng định tuyến

### Cấu hình định tuyến tĩnh LINUX

#### Xem bảng định tuyến :

```
route -n
```

![](https://media.geeksforgeeks.org/wp-content/uploads/20200512153837/To-display-routing-table-in-full-numeric-form.png)

Trong đó :

- Destination : Đích đến của mạng hoặc của host

- Gateway : Địa chỉ của gateway , gói tin sẽ được gửi qua địa chỉ này. Nếu có giá trị là \* (0.0.0.0) tức đây là địa chỉ mạng được kết nối trực tiếp, không cần chuyến gói tin ra gateway.

- Genmask : Subnet mask của địa chỉ đích (0.0.0.0 dành cho default route)

- Flag : Cờ hiệu

- Metric : Khoảng cách tới đích, thường dùng để so sánh các route

- Iface : interface của mạng

#### Thêm route

Với `ip route` :

```
sudo ip route add {destination_ip} via {gateway_ip} dev {interface}
```

Với `route` :

```
sudo route add -net {destination_ip} netmask {netmask_address} gw {gateway_ip}
```

với `netplan` (với cách này, sau khi hệ thống khởi động lại route vẫn được duy trì):

```
routes:
 - to: {destination_ip}
  via: {gateway_ip}
```

#### Xóa route

Với `ip route` :

```
sudo ip route del {destination_ip} dev {interface}
```

Với `route` :

```
sudo route del -net {destination_ip} netmask {netmask_address} gw {gateway_ip}
```

## Tổng quan về Iptables

### IpTables là gì ?

Iptables là một công cụ trong hệ điều hành Linux được sử dụng để quản lý bảng quy tắc của hệ thống tường lửa. Nó giúp kiểm soát việc chuyển tiếp dữ liệu giữa các giao diện mạng trên hệ thống, từ chặn hoặc chấp nhận gói tin dựa trên các quy tắc được xác định trước. Iptables có khả năng thực hiện các chức năng như chuyển đổi địa chỉ IP (NAT), quản lý các kết nối (connection tracking), và bảo vệ hệ thống khỏi các tấn công mạng.

Iptables gồm 2 phần là Netfilter ở trong nhân Linux và Iptables nằm ngoài nhân. Iptables chịu trách nhiệm giao tiếp với người dùng và sau đó đẩy các luật của người dùng vào cho Netfiler xử lí. Netfilter tiến hành lọc các gói dữ liệu ở mức IP. Netfilter làm việc trực tiếp trong nhân, nhanh và không làm giảm tốc độ của hệ thống.

### Các thành phần cấu tạo của Iptables

Gồm có 3 thành phần :

- Tables : Mỗi tables định nghĩa không gian lưu trữ của các quy tắc.

- Chains : Mỗi bảng chứa nhiều Chains và các chains quy định các điều kiện và hành động được áp dụng cho các gói tin.

- Target : Mỗi chain sẽ chứa nhiều target. Target có thể được coi là quy tắc (hành động) cụ thể mà gói tin được xử lý.

#### Tables

Iptable được chia làm 4 bảng :

- Bảng filter: là bảng dùng để áp dụng các chính sách lọc gói tin , có cho phép các gói tin đi qua hay không

- Bảng NAT : dùng để thay đổi đích, nguồn, port của các gói tin

- Bảng mangle : để thay đổi QoS của gói tin như thay đổi các tham số TOS,TTL,..

- Bảng RAW : 1 gói tin có thể thuộc một kết nối mới hoặc cũng có thể là của 1 một kết nối đã tồn tại. Table raw cho phép làm việc với gói tin trước khi kernel kiểm tra trạng thái gói tin

#### Chains

- PREROUTING : Các rule thuộc chain này sẽ được áp dụng ngay khi gói tin vừa vào đến Network interface, trước khi nó được định tuyến. Chain này chỉ có ở table NAT, raw và mangle

- INPUT : các rule trong chain này được thực thi ngay trước khi gói tin được vào hệ thống ( trước khi gặp tiến trình). Chain này chỉ tồn tại ở table mangle và nat.

- OUTPUT : Các rule trong chain này được thực thi ngay sau khi gói tin đi ra từ hệ thống (được tiến trình tạo ra). Chain này tồn tại ở các table: raw, mangle, nat và filter.

- FORWARD: Các rule trong chain này thực thi cho các gói tin được định tuyến qua host hiện tại. Chain này chỉ tồn tại ở table mangle và filter

- POSTROUTING: Các rule trong chain này thực thi ngay khi gói tin rời Network interface. Chain này chỉ tồn tại ở table mangle và nat.

#### Target

- ACCEPT : Chấp nhận gói tin, cho phép gói tin đi vào hệ thống

- DROP : Loại bỏ gói tin, không có gói tin trả lời, giống như là hệ thống không tồn tại

- REJECT : Loại bỏ gói tin nhưng vẫn gửi gói tin phải hồi tới người gửi

- LOG : Chấp nhận gói tin nhưng có ghi lại log

Lưu ý : Gói tin sẽ đi qua tất cả các rule chứ không dừng lại khi đã đúng với 1 rule đặt ra. Đối với những gói tin không khớp với rule nào cả mặc định sẽ được chấp nhận

### Thiết lập iptables

#### Hiển thị trong iptables

Để hiển thị iptables, ta sử dụng lệnh :

```
sudo iptables -t {table} -L -v
```

Nếu không dùng tùy chọn `-t` thì mặc định sẽ hiển thị filter table:
![](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2023/01/List-rules.png?lossy=2&strip=1&webp=1)

Trong đó :

- pkts : tổng số lượng package khớp với rule
- bytes : tổng số bytes khớp với rule
- target : target (hành động) sẽ thực thi
- prot : các protocol sẽ được áp dụng để thực thi rule này. Có 3 lựa chọn : all, tcp, udp
- in : chỉ ra rule sẽ được áp dụng cho các gói tin đi vào từ interface nào (any thì sẽ áp dụng cho tất cả interface)
- out : tương tự như in, nhưng áp dụng cho gói tin đi ra từ interface
- source : chỉ áp dụng rule cho nhưng gói tin đến từ địa chỉ IP này (anywhere thì áp dụng cho tất cả địa chỉ)
- destination : tương tự như source nhưng áp dụng cho gói tin có đích từ địa chỉ IP này

#### Các tùy chọn làm việc cùng iptables

##### Tùy chọn chỉ định thông số Iptables

| Tùy chọn               | Ý nghĩa                                  |
| ---------------------- | ---------------------------------------- |
| `-p`,`--protocol`      | Chỉ định loại giao thức                  |
| `-i`,`--in-interface`  | Chỉ định interface đầu vào               |
| `-o`,`--out-interface` | Chỉ định inteface đầu ra                 |
| `-s`,`--source`        | Chỉ định địa chỉ IP nguồn                |
| `-d`,`--destination`   | Chỉ định địa chỉ IP đích                 |
| `--sport`              | Chỉ định cổng nguồn                      |
| `--dport`              | Chỉ định cổng đích                       |
| `-j`,`--jump`          | Chỉ định target (hành động) được áp dụng |

##### Tùy chọn thao tác với chain trong Iptables

| Tùy chọn | Ý nghĩa                                                                                                                                           |
| -------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-N`     | Tạo chain mới                                                                                                                                     |
| `-L`     | Liệt kê các rule có trong chain                                                                                                                   |
| `-X`     | Xóa tất cả các quy tắc (do người dùng) đã tạo trong chain                                                                                         |
| `-F`     | Xóa tất cả các quy tắc có trong chain chỉ định, nếu không có chain chỉ định, xóa mọi rule trong tất cả chain                                      |
| `-P`     | Thiết lập chính sách mặc định cho 1 chain, nếu gói tin được duyệt qua toàn bộ chain mà không khớp với quy tắc nào, nó sẽ chỉ định 1 target cụ thể |
| `-Z`     | Thiết lập bộ đếm byte và packet ở tất cả các chain trên 1 bảng cụ thể                                                                             |

##### Tùy chọn thao tác với rule trong Iptables

| Tùy chọn         | Ý nghĩa                             |
| ---------------- | ----------------------------------- |
| `-A`,`--append`  | Thêm một rule vào cuối chain        |
| `-I`,`--insert`  | Thêm một rule vào đầu chain         |
| `-D`,`--delete`  | Xóa một rule chỉ định ra khỏi chain |
| `-R`,`--replace` | Thay thế một rule chỉ định          |

##### Connection tracking trong iptables

Đây là những trạng thái mà hệ thống connection tracking (module conntrack của IPtables) theo dõi trạng thái của các kết nối:

- NEW: Khi có một gói tin mới được gởi tới và không nằm trong bất kỳ connection nào hiện có, hệ thống sẽ khởi tạo một kết nối mới và gắn nhãn NEW cho kết nối này. Nhãn này dùng cho cả TCP và UDP.

- ESTABLISHED: Trạng thái chuyển NEW to ESTABLISHED khi nhận được phản hồi hợp lệ từ phía đối diện của kết nối. Với kết nối TCP, nó chính là SYN/ACK và với UDP/ICMP, là phản hồi mà ở đó địa chỉ nguồn và địa chỉ đích được hoán đổi.

- RELATED: Gói tin được gởi tới không thuộc về một kết nối hiện có nhưng có liên quan đến một kết nối đang có trên hệ thống. Đây có thể là một kết nối phụ hỗ trợ cho kết nối chính, ví dụ như giao thức FTP có kết nối chính dùng để chuyển lệnh và kết nối phụ dùng để truyền dữ liệu.

- INVALID: Gói tin được đánh dấu INVALID khi gói tin này không có bất cứ quan hệ gì với các kết nối đang có sẵn, không thích hợp để khởi tạo một kết nối mới hoặc đơn giản là không thể xác định được gói tin này, không tìm được kết quả trong bảng định tuyến.

- UNTRACKED: Gói tin có thể được gắn hãn UNTRACKED nếu gói tin này đi qua bảng raw và được xác định ( gắn cờ ) là không cần theo dõi gói này trong bảng connection tracking.

- SNAT: Đó là trạng thái sẽ được đánh dấu khi gói tin được chỉnh sửa phần source address bởi quá trình NAT. Nó được dùng bởi hệ thống Connection tracking để thay đổi lại source address ở gói tin phản hồi lại.

- DNAT: Đó là trạng thái sẽ được đánh dấu khi gói tin được chỉnh sửa phần destination address bởi quá trình NAT. Nó được dùng bởi hệ thống Connection tracking để thay đổi lại destination address ở gói tin phản hồi lại.

#### Thực hành tạo một số rule cơ bản

Tạo rule chấp nhận tất cả các gói tin có địa chỉ IP thuộc 192.168.1.0/24 đến từ interface ens33 :

```
iptables -t filter -A INPUT -i ens33 -s 192.168.1.0/24 -j ACCEPT
```

Tạo rule từ chối gói tin gửi tới địa chỉ IP 192.168.1.3/32

```
iptables -t filter -A OUTPUT -d 192.168.1.3/32 -j REJECT
```

Tạo rule từ chối gói tin sử dụng tcp gửi đi có destination port là 2024 :

```
iptables -A OUTPUT -p tcp --dport 2024
```

Tạo rule từ chối tất cả gói tin chỉ chấp nhận gói tin tcp gửi đi từ destination port là 22 (ssh)

```
# Đầu tiên chặn tất cả gói tin đến theo mặc định với lệnh :

iptables -P INPUT REJECT

# Sau đó, cho phép gói tin đến từ cổng 22 :

iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

## Tổng quan về Keepalived

Đối với những mô hình dịch vụ cần đảm bảo tính sẵn sàng cao (High Availability – HA), thì việc hệ thống bị down là không thể chấp nhận được.

Keepalived là một chương trình dịch vụ trên Linux cung cấp khả năng tạo độ sẵn sàng cao (High Availability) cho hệ thống dịch vụ và khả năng cân bằng tải (Load Balancing) đơn giản, keepalived cho phép nhiều máy tính cùng chia sẻ một địa chỉ IP ảo với nhau theo mô hình Active – Passive. Khi người dùng cần truy cập vào dịch vụ, người dùng chỉ cần truy cập vào địa chỉ IP ảo dùng chung này thay vì phải truy cập vào những địa chỉ IP thật của các thiết bị kia

Tóm gọn lại, keepalived có 2 chức năng chính :

- Cân bằng tải: với chức năng health checking (kiểm tra tình trạng sức khoẻ) của các máy chủ trong mô hình HA và các phương thức cân bằng tải xuống server backend.

- Tạo độ sẵn sàng cao (High Avaiability) : chức năng VRRP đảm nhận quản lý khả năng chịu lỗi của cụm server (Failover) với Virtual IP.

### Cách hoạt động của Keepalived

Keepalived sẽ gom nhóm các máy chủ dịch vụ nào tham gia cụm HA, khởi tạo một Virtual Server đại diện cho một nhóm thiết bị đó với một Virtual IP (VIP) và một địa chỉ MAC vật lý của máy chủ dịch vụ đang giữ Virtual IP đó. Vào mỗi thời điểm nhất định, chỉ có một server dịch vụ dùng địa chỉ MAC này tương ứng Virtual IP. Khi có ARP request gởi tới virtual IP thì server dịch vụ đó sẽ trả về địa chỉ MAC này.

Các máy chủ dịch vụ sử dụng chung VIP phải liên lạc với nhau bằng địa chỉ multicast 224.0.0.18 bằng giao thức VRRP. Các máy chủ sẽ có độ ưu tiên (priority) trong khoảng từ 1 – 254, và máy chủ nào có độ ưu tiên cao nhất sẽ thành Master, các máy chủ còn lại sẽ thành các Slave/Backup, hoạt động ở chế độ chờ.

Cơ chế failover được xử lý bởi giao thức VRRP, khi khởi động dịch vụ, toàn bộ các server cấu hình dùng chung VIP sẽ gia nhập vào một nhóm multicast. Nhóm multicast này dùng để gửi/nhận các gói tin quảng bá VRRP. Các server sẽ quảng bá độ ưu tiên (priority) của mình, server với độ ưu tiên cao nhất sẽ được chọn làm MASTER. Một khi nhóm đã có 1 MASTER thì MASTER này sẽ chịu trách nhiệm gởi các gói tin quảng bá VRRP định kỳ cho nhóm multicast.

Nếu vì một sự cố gì đó mà các server BACKUP không nhận được các gói tin quảng bá từ MASTER trong một khoảng thời gian nhất định thì cả nhóm sẽ bầu ra một MASTER mới. MASTER mới này sẽ tiếp quản địa chỉ VIP của nhóm và gởi các gói tin ARP báo là nó đang giữ địa chỉ VIP này. Khi MASTER cũ hoạt động bình thường trở lại thì server này có thể lại trở thành MASTER hoặc trở thành BACKUP tùy theo cấu hình độ ưu tiên của các router.

### Cấu hình Keepalived

Để cấu hình dịch vụ keepalived, ta cần phải chỉnh sửa file /etc/keepalived/keepalived.conf. Một số block cấu hình đáng chú ý trong file này như sau:

- global_defs: cấu hình thông tin toàn cục (global) cho keepalived như gởi email thông báo tới đâu, tên của cụm đang cấu hình.

- vrrp_script: chứa script, lệnh thực thi hoặc đường dẫn tới script kiểm tra dịch vụ (Ví dụ: nếu dịch vụ này down thì keepalived sẽ tự chuyển VIP sang 1 server khác).

- vrrp_instance: thông tin chi tiết về 1 server vật lý trong nhóm dùng chung VRRP. Gồm các thông tin như interface dùng để liên lạc của server này, độ ưu tiên để, virtual IP tương ứng với interface, cách thức chứng thực, script kiểm tra dịch vụ….

```
global_defs {
   notification_email {
        [email protected]
   }
   notification_email_from [email protected]
   smtp_server x.x.x.x
   smtp_connect_timeout 30

}

vrrp_script chk_haproxy {
        script "command"
        interval <time>
        weight <n>
}

vrrp_instance string {
    state MASTER|BACKUP
    interface string
    mcast_src_ip @IP
    virtual_router_id num
    priority num
    advert_int num
    smtp_alert
    authentication {
        auth_type PASS|AH
        auth_pass string
    }
    virtual_ipaddress { # Block limited to 20 IP addresses
        @IP
        @IP
    }
    notify_master "/path_to_script/script_fault.sh <arg_list>"
    notify_backup "/path_to_script/script_fault.sh <arg_list>"
    notify_fault "/path_to_script/script_fault.sh <arg_list>"
}
```

#### global_defs

- notification_email : email nhận được thông báo
- notification_email_from : email được sử dụng khi xử lý câu lệnh "MAIL FROM:" SMTP
- smtp_server : SMTP server dùng để gửi email thông báo
- smtp_connection_timeout: timeout cho tiến trình xử lý SMTP

#### vrrp_instance

- state : Chỉ trạng thái Master hoặc Backup được sử dụng bởi máy chủ.
- interface: chỉ định interface nào sẽ sử dụng cho hoạt động IP failover - VRRP
- mcast_src_ip : Địa chỉ multicast
- virtual_router_id : Mã định danh cho các router (mà ở đây là các máy chủ) cùng thuộc nhóm VRRP.
- priority: Độ ưu tiên của VRRP router ( tức máy chủ ) trong quá trình bầu chọn. Có giá trị từ 0 -> 255
- advert_int : thời gian giữa các lần gởi gói tin VRRP advertisement (đơn vị giây).
- smtp_alert: kích hoạt thông báo bằng email SMTP khi trạng thái MASTER có sự thay đổi.
- authentication: chỉ định hình thức chứng thực trong VRRP. ‘auth_type‘, sử dụng hình thức mật khẩu plaintext hay mã hoá AH
- virtual_ipaddress: Địa chỉ IP ảo của nhóm VRRP đó (Chính là địa chỉ dùng làm gateway cho các host). Các gói tin trao đổi, làm việc với host đều sử dụng địa chỉ ảo này.
- notify_master: chỉ định chạy shell script nếu có sự kiện thay đổi về trạng thái MASTER.
  notify_backup: chỉ định chạy shell script nếu có sự kiện thay đổi về trạng thái BACKUP.
  notify_fault: chỉ định chạy shell script nếu có sự kiện thay đổi về trạng thái thất bại (fault).

## Tool debug, config network

### Ip Link

Hiển thị danh sách các network interface :

```
ip link
```

Hiển thị thông tin về interface cụ thể :

```
ip link show {interface}
```

Kích hoạt/Tắt interface cụ thể :

```
ip link set {interface} up/down
```

Thay đổi địa chỉ MAC của interface :

```
ip link set {interface} address {MAC address}
```

### Ip route

Hiển thị routing table :

```
ip route
```

Thêm default route :

```
ip route add default via {gateway_ip}
```

hoặc

```
ip route add default dev {interface}
```

Thêm static route :

```
ip route add {destination_ip} via {gateway_ip} dev {interface}
```

Xóa static route :

```
sudo ip route del {destination_ip} dev {interface}
```

Thay đổi/Thay thế static route :

```
ip route {change|replace} {destination_ip} via {gateway_ip} dev {interface}
```

Hiển thị tuyến đường sẽ được dùng để đi tới địa chỉ IP cụ thể :

```
ip route get {destination_ip}
```

### Ip address

Hiển thị danh sách các interface và địa chỉ ip trên các interface đó :

```
ip address
```

Hiển thị danh sách các interface đang hoạt động :

```
ip address show up
```

Hiển thị thông tin về 1 inteface cụ thể :

```
ip address show dev {interface}
```

Gán địa chỉ IP cho 1 interface :

```
ip address add {ip_address} dev {interface}
```

Xóa địa chỉ IP trên 1 interface :

```
ip address delete {ip_address} dev {interface}
```

### arp

Hiển thị ARP table :

```
arp -a
```

Xóa một entry chỉ định :

```
arp -d {address}
```

Thêm một entry mới vào ARP table :

```
arp -s {address} {mac_address}
```

### telnet

Kiểm tra xem port nào đang mở :

```
telnet {ip address} {port}
```

### ping

ping tới host :

```
ping {ip address/host}
```

ping tới host với số lần cụ thể :

```
ping -c {count} {ip address/host}
```

ping tới host với khoảng thời gian cụ thể giữa các request :

```
ping -i {second} {ip address/host}
```

### traceroute (Truy vết gói tin trên mạng, xem gói tin đã đi qua những node nào)

Hiển thị tuyến đường mà gói tin đã đi qua mạng

```
traceroute {ip address/host}
```

Hiển thị tuyến đường gói tin đi qua nhưng chỉ hiện thị Ip address mà không hiện hostname

```
traceroute -n {ip address/host}
```

### mtr (Kết hợp giữa traceroute và ping)

Traceroute một host và tiếp tục ping tới tất cả các hops trung gian :

```
mtr {ip address/host}
```

Vô hiệu hóa hostname mapping :

```
mtr --no-dns {ip address/host}
```

Hiển thị kết quả sau khi ping tới mỗi hop 10 lần :

```
mtr --report-wide {ip address/host}
```

Hiển thị cả địa chỉ IP và Hostname :

```
mtr --show-ips {ip address/host}
```

### netstat

Liệt kê tất cả các port đang hoạt động :

```
netstat -a
```

Output của lệnh netstat :

- `Proto`: Gia thức (TCP, UDP, raw) được sử dụng bởi socket
- `Recv-Q`: (Receive Queue) cho biết có bao nhiêu data đang nằm trong hàng chờ trong buffer của socket để chờ đuợc nhận
- `Send-Q`: (Send Queue) cho biết có bao nhiêu data đang nằm trong hàng chờ trong buffer của socket để chờ đuợc gửi đi
- `Local Address`: Địa chỉ và port của máy local mà socket đã kết nối
- `Foreign Address` : Địa chỉ và port của máy remote mà socket đã kết nối
- `State` : Trạng thái của socket
  - `ESTABLISHED` : trạng thái đã thiết lập kết nối
  - `SYN_SENT` : trạng thái mở kết nối
  - `SYN_RECV` : trạng thái nhận được yêu cầu kết nối
  - `FIN_WAIT1` : trạng thái socket đã đóng nhưng kết nối đang shutdown
  - `FIN_WAIT2` : trạng thái kết nối đã đóng, socket đang để tắt bên phía máy remote
  - `TIME_WAIT` : socket đang chờ sau khi đóng để để xử lý các packet vẫn còn trong mạng
  - `CLOSE` : socket không còn được sử dụng
  - `CLOSE_WAIT` : máy remote đã shutdown, đang chờ socket đóng
  - `LASK_ACK` : máy remote đã shutdown, socket đã shutdown. Đang chờ ACK
  - `LISTEN` : socket đang lắng nghe các kết nối đến.
  - `CLOSING` : Cả 2 socket đều đóng nhưng vẫn chưa gửi bất kỳ dữ liệu nào
  - `UNKNOWN` : trạng thái của socket là không rõ

### tcpdump

là công cụ cho phép bắt và lưu trữ lại gói tin bắt được trong mạng (packet sniffer), từ đó chúng ta có thể sử dụng để phân tích

Sau khi kết thúc việc bắt các gói tin, tcpdump sẽ báo cáo các cột sau:

- Packet capture: số lượng gói tin bắt được và xử lý.
- Packet received by filter: số lượng gói tin được nhận bởi bộ lọc.
- Packet dropped by kernel: số lượng packet đã bị dropped bởi cơ chế bắt gói tin của hệ điều hành.

Liệt kê các interface khả dụng cho việc bắt gói tin :

```
sudo tcpdump -D
```

Bắt gói tin trên tất cả các interface đang hoạt động :

```
sudo tcpdump -i any
```

Bắt gói tin trên interface cụ thể :

```
sudo tcpdump -i {interface}
```

Giới hạn số lượng gói tin được bắt :

```
sudo tcpdump -c {count}
```

Theo mặc định, tcpdump phân giải IP address và port thành name, đề vô hiệu hóa :

```
sudo tcpdump -nn
```

Tcpdump có khả năng bắt nhiều loại gói tin sử dụng các giao thức khác nhau như TCP, UDP, ICMP... ở đây ta sẽ nói với output format của gói tin TCP.

Gói tin TCP được tcpdump bắt được có format như sau :

```
08:41:13.729687 IP 192.168.64.28.22 > 192.168.64.1.41916: Flags [P.], seq 196:568, ack 1, win 309, options [nop,nop,TS val 117964079 ecr 816509256], length 372
```

- `08:41:13.729687` : Trường này biểu diễn thời gian bắt được gói tin dựa trên local clock.

- `IP` : thể hiện rằng nó sử dụng IPv4 , với gói tin IPv6 giá trị sẽ là IP6

- `192.168.64.28.22` : Địa chỉ IP nguồn và port

- `192.168.64.1.41916` : Địa chỉ Ip đích và port

- `Flags [P.]` : Giá trị này thể hiện TCP Flag, các giá trị này có thể thể kết hợp với nhau :

  - S (SYN) : Bắt đầu kết nối
  - F (FIN) : Kết thúc kết nối
  - P (PUSH) : Đẩy dữ liệu
  - R (RST) : Khởi động lại kết nối
  - . (ACK) : Acknowledment

- `seq 196:568` : Sequence number. Gói đầu tiền được bắt thì nó là 1 số tuyệt đối. Các gói tiếp theo sử dụng số tương đối giúp việc theo dõi dễ hơn. Ví dụ `seq 196:568` có nghĩa là gói này sẽ chứa các byte từ 196 đến 568 của luồng này.

- `ack 1` : Ack number . Trong trường hợp này, ack sẽ là 1 vì nó đang là bên gửi dữ liệu. Còn nếu nó đang là bên nhận dữ liệu, trường này sẽ biểu diễn số byte dự kiến (data) tiếp theo của luồng.

- `win 309` : Window size. Đại diện cho số byte có sẵn trong receiving buffer

- `option` : theo sau là các tùy chọn của TCP như MSS (Maximum Segment Size) hoặc Window Scale

- `length` : Độ dài của payload data. Sẽ là hiệu của byte cuối và byte đầu của Sequence number

Lọc gói tin dựa trên giao thức :

```
sudo tcpdump -i any {protocol}
```

Lọc gói tin liên quan tới host chỉ định :

```
sudo tcpdump -i any host {ip address / hostname}
```

Lọc gói gói tin dựa trên port :

```
sudo tcpdump -i any port {port number}
```

Lọc gói tin dựa trên source/destination IP :

```
sudo tcpdump -i any src/dst {ip address}
```

Sử dụng các biểu thức phức tạp như `and`, `or` , `not` để lọc. VD :

```
sudo tcpdump -i any -c5 -nn " not port 80 and (src 192.168.122.98 or src 54.204.39.132)"
```

Kiểm tra nội dung của Packet ở dạng mã hex (-x) và ACSII (-A) :

```
sudo tcpdump -x/-A
```

Lưu/Đọc thông tin về các gói tin đã bắt ở file .pcap (packet capture):

```
sudo tcpdump -w/-r toilamlap.pcap
```

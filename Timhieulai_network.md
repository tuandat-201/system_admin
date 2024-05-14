## Bảng định tuyến

Output lệnh `route -n` :

```
Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
0.0.0.0         192.168.1.254   0.0.0.0         UG    0      0        0 ens33
10.1.0.0        0.0.0.0         255.255.0.0     U     0      0        0 ens36
192.168.1.0     0.0.0.0         255.255.255.0   U     0      0        0 ens33
```

Giải thích output :

- `Destination` : Đích đến của gói tin. Nếu có giá trị là `0.0.0.0`, thì đây là default gateway (Khi gói tin không khớp với bất kỳ entry nào trong bảng định tuyến thì gói tin sẽ được chuyển tới default gateway).

- `Gateway`: Nếu đích đến của gói tin khớp với entry nào đó, gói tin sẽ được gửi tới địa chỉ đích thông qua Gateway. Nếu địa chỉ này bằng `0.0.0.0`, tức là không cần gửi qua địa chỉ gateway, vì host hiện tại đang được kết nối với destination network nên nó chỉ cần gửi trực tiếp gói tin tới interface đang được kết nối
  - Ví dụ: Khi host hiện tại nhận được gói tin có đích đến nằm một máy nào đó nằm trong mạng 192.168.1.0/24, nó sẽ tìm địa chỉ MAC được liên kết với IP đích đó bằng ARP request, sau đó chuyển tiếp gói tin tới địa chỉ MAC đó.

- `Genmask`: Subnet mask của địa chỉ đích

- `Flags` : Cờ hiệu
  - `U` : Tuyến đường đang hoạt động
  - `G` : Được định tuyến tới địa gateway
  - `H` : Đây là tuyến đường tới host cụ thể, địa chỉ đích là một địa chỉ hoàn chỉnh
  - `!` : Tuyến đường bị từ chối
- `Metric` : Chi phí tới đích. (Được sử dụng để so sánh giữa các tuyến)
- `Ref` : Số lượng tham chiếu tới tuyến đường này

## Thêm static route

Sử dụng câu lệnh `ip route`:

```
sudo ip route add {destination_ip/netmask} via {gateway_ip} dev {interface}
```

Sử dụng câu lệnh `route`:

```
sudo route add -net {destination_ip} netmask {netmask_address} gw {gateway_ip}
```

## Giá trị 0.0.0.0 ở cột Local Address và Foreign Address trong lệnh netstat

Giá trị `0.0.0.0` trong cột Local Address thể hiện rằng port đó đang lắng nghe kết nối trên tất cả các network interface

Giá trị `0.0.0.0:*` trong cột Foreign Address thể hiện rằng Local host đang lắng nghe từ mọi địa chỉ Ip và từ bất kỳ cổng nào của IP đó

## Không có entry trong ARP table sau khi đã telnet

Vì ARP tables chỉ lưu lại các trường hợp trong cùng 1 broadcast domain

## Ý nghĩa của *** trong lệnh traceroute

Có thể xảy ra do TTL expried, 1 số trường hợp như sau :

- Một số router không phản hồi vì tạm thời bị quá tải do quá bận rộn để phản hồi lại traceroute do nó được coi là low-priority event

- Nếu nó xuất hiện nhiều dấu *** liền nhau, có khả năng là do không thể định tuyến tới host đó.

## Mục dích DHCP cấp phát Subnet Mask và Default gateway

- Cấp subnet mask để định nghĩa phạm vi của dải địa chỉ mạng, tức số lượng địa chỉ cho dải mạng đó là bao nhiêu

- Cấp default gateway để có thể kết nối tới mạng khác, nghĩa là khi thiết bị trên local network muốn gửi dữ liệu tới thiết bị có địa chỉ IP ở 1 mạng khác, nó phải gửi gói tin tới gateway trước, sau đó gateway chuyển tiếp gói tin tới đích đến nằm bên ngoài Local network

## Tìm hiểu địa chỉ IP động và tĩnh

- Địa chỉ ip động: là địa chỉ tạm thời được gán tự động cho các thiết bị mạng và liên tục thay đổi theo thời gian

- Địa chỉ ip tĩnh : là địa chỉ IP cố định được cấu hình thủ công và không thay đổi theo thời gian

Mục đích sử dụng của IP tĩnh :

- Cần sử dụng IP tĩnh cho bất kỳ dịch vụ và tính năng nào yêu cầu kết nối liên tục, vì nếu sử dụng IP động, khi địa chỉ IP thay đổi và gán địa chỉ mới, bất kỳ người dùng nào đã kết nối trước đó đều bị ngắt kết nối và phải đợi để kết nối lại

## Trường hợp xảy ra 2 máy chủ cùng tham gia Keepalived cùng cầm Virtual IP .

Trong keepalived sẽ xảy ra trường hợp 2 máy chủ tham gia keepalived cùng cầm Virtual IP khi máy chủ MASTER gửi gói tin quảng bá VRRP tới máy chủ BACKUP nhưng máy chủ BACKUP không nhận được. Sau khoảng thời gian không nhận được gói tin quảng bá VRRP, nó sẽ tự bầu nó làm máy chủ MASTER mới và cùng lúc giữ địa chỉ Virtual IP với máy chủ còn lại

## Xác định địa chỉ IP có đang hoạt động hay không

Để xác định địa chỉ IP còn hoàn động hay không, ta kiểm tra khi ping đến có nhận được phản hồi từ máy chủ hay không, phải chắc chắn IP phía máy chủ được cấu hình chính xác :

- Nếu nhận được phải hồi => IP đang hoạt động

- Nếu không nhận được phản hồi, có thể do :

  - Gói tin bị drop bởi tường lửa từ 1 hoặc từ cả 2 phía
  - Định tuyến chưa chính xác
  - Xảy ra vấn đề với thiết bị như dây dẫn..

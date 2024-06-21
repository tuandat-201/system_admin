## Storage là gì ?

Kho chứa dữ liệu là kho lưu trữ kỹ thuật số thực hiện việc lưu trữ và bảo vệ thông tin trong hệ thống máy tính. Kho chứa dữ liệu có thể là một kho lưu trữ được kết nối mạng, kho lưu trữ phân tán trên đám mây, ổ cứng vật lý hoặc kho lưu trữ ảo. Nó có thể lưu trữ cả dữ liệu có cấu trúc như bảng thông tin và dữ liệu phi cấu trúc như email, hình ảnh và video. Các tổ chức sử dụng kho chứa dữ liệu để lưu giữ, chia sẻ và quản lý thông tin giữa các đơn vị trong doanh nghiệp.

![](https://res.cloudinary.com/canonical/image/fetch/f_auto,q_auto,fl_sanitize,c_fill,w_2932,h_1617/https://assets.ubuntu.com/v1/09b510e0-UAS_storage_options.png)

## Các dạng Storage
Có 3 cách lưu trữ và tổ chức dữ liệu trong Storage. 

### File Storage

File Storage là hệ thống lưu trữ phân cấp để tổ chức và lưu trữ dữ liệu. Dữ liệu sẽ nằm trên file, files sẽ nằm trong directory. Các thư mục còn có thể chứa các thư mục khác, tạo ra một hệ thống phân cấp các thư mục và các thư mục con. Dữ liệu được lưu trữ trong file được sắp xếp và truy xuất bằng cách sử dụng metadata. Nó sẽ cho máy tính biết chính xác nơi file được lưu trữ.

Mỗi file đều có một path độc nhất bao gồm tên directory, tên subdirectory, tên file.

Ưu điểm :
- Dễ sử dụng và truy cập với cấu trúc thư mục quen thuộc
- Khả năng chia sẻ, quyền truy cập dữ liệu dễ dàng giữa người dùng và thiết bị.
- Bảo mật và sao lưu dữ liệu mạnh mẽ.

Nhược điểm :
- Khó quản lý và truy xuất với số lượng tệp lớn
- Khó làm việc với dữ liệu phi cấu trúc
- Chi phó có thể sẽ có phần đắt đỏ với quy mô lớn

### Block Storage

Block Storage bổ chức dữ liệu bằng chia dữ liệu thành các block có size bằng nhau. Mỗi block chứa một phần dữ liệu tách biệt và có unique identify, identify này là metadata duy nhất được gắn với mỗi block. Kiểu Storage này cho phép truy cập và truy xuất data nhanh chóng, vì nó không phụ thuộc vào file system.

Block Storage thường được thiết lập để tách dữ liệu khỏi enviroment của user, rồi phân tán dữ liệu đó sang các enviroment khác nhau để xử lí dữ liệu đó dễ dàng hơn (như Window, Linux, Mac) .Khi dữ liệu được yêu cầu, block storage sẽ tập hợp chúng và trả lại cho user

Ưu điểm :
- Khả năng truy xuất nhanh chóng
- Có thể phân tán dữ liệu sang các hệ điều hành khác cho phép người dùng tự do điều chỉnh cấu hình dữ liệu của họ.

Nhược điểm :
- Giá thành cao
- Liên kết với 1 máy chủ chỉ định để tại 1 thời điểm cụ thể để lưu trữ dư liệu.
- Metadata của block storage khá hạn chế.

### Object Storage

Object storage quản lý dữ liệu dưới dạng object bao gồm Unique Identify, Data và metadata. 

Những object này bao gồm những mảnh data được lưu trữ bằng cấu trúc phẳng còn được gọi là data pool, thay vì cấu trúc phân cấp. Loại storage, data được truy cập thông qua API hoặc user interface

Data pool (Data Lake) là một kho lưu trữ trung tâm chứa một lượng lớn dữ liệu thô được giữ để sử dụng khi cần thiết

Ưu điểm :
- Có khả năng mở rộng quy mô lớn và hiệu suất cao
- Có khả năng sao lưu, phục hồi dữ liệu tốt và đảm bảo an toàn dữ liệu.
- Chi phí thấp hơn so với File Storage và Block Storage, nhất là với nhu cầu lưu trữ một lượng lớn dữ liệu.
- Dễ dàng tích hợp, phân phối dữ liệu và quản lý metadata.
- Phù hợp cho lưu trữ dữ liệu lớn, phân tán, sao lưu, phục hồi và các ứng dụng đám mây khác

Nhược điểm :
- Không phù hợp cho tính toán và truy vấn dữ liệu.
- Có thể gặp độ trễ cao hơn khi truy cập dữ liệu
- Khó xử lý nhiều object dữ liệu nhỏ hiệu quả.
- Không thể khóa tệp, phân quyền truy cập hạn chế.
- Khó khăn trong di chuyển dữ liệu

#### So sánh

![](https://a.storyblok.com/f/168723/1356x940/453c38c6e0/cloud-storage-types.svg)

| Kiểu Storage | Ưu điểm | Nhược điểm | Ứng dụng |
|-|-|-|-|
| Block Storage | Truy cập dữ liệu nhanh chóng và hiệu quả <br> Có thể mở rộng storage <br> Tương thích với nhiều hệ điều hành | Giá thành cao <br> Liên kết với 1 máy chủ chỉ định để tại 1 thời điểm cụ thể để lưu trữ dư liệu. <br> Metadata của block storage khá hạn chế.| Database <br> Virtual machines <br> Ứng dụng yêu cầu khả năng đọc ghi nhanh |
| File Storage | Thân thiện với người dùng <br> Hỗ trợ chia sẻ file qua nhiều instance <br> Dễ dàng triển khai và quản lý | Hiệu suất thấp hơn so với Block Storage <br> Khả năng mở rộng có giới hạn | File Sharing |
| Object Storage | Dễ dàng mở rộng <br> Storage hiệu quả dành cho Ustructured data <br> Truy cập thông qua API hoặc Web interface | Hiệu suất truy cập dữ liệu thấp <br> Quản lý phức tạp hơn so với file storage | Lưu trữ unstructured data <br> Phân phối data qua nhiều vị trí khác nhau <br>


## Các giải pháp lưu trữ

### DAS (Direct Attached Storage)

![](https://sp-ao.shortpixel.ai/client/to_auto,q_glossy,ret_img,w_544/https://anhngoc.vn/wp-content/uploads/2022/10/Screenshot_3_0-544x400.png)

DAS là cách lưu trữ truyền thống với cơ chế các thiết bị lưu trữ được gắn trực tiếp vào server (máy chủ) thông qua cáp USB hay khay ngoại vi.

DAS sở hữu ưu điểm dễ triển khai và không tốn kém chi phí đầu tư ban đầu cho các thiết bị mạng. Tuy nhiên, phương pháp này cũng tồn tại nhược điểm về khả năng mở rộng dữ liệu hay khi số lượng server tăng lên.

Trường hợp dữ liệu tăng, người dùng buộc phải bổ sung hoặc thiết lập lại dung lượng, bảo trì trên từng server gây khó khăn trong việc quản lý và quy hoạch dữ liệu. Đồng thời, do được kết nối trực tiếp với server nên việc khai thác dữ liệu sẽ bị ảnh hưởng khi server gặp sự cố.

### NAS (Network Attached Storage)

NAS kết nối trực tiếp với mạng thông qua cáp Ethernet (RJ45) có dây cứng hoặc qua Wi-Fi, nên nó tạo ra mạng LAN, được gán với một địa chỉ IP và truyền dữ liệu giữa người dùng, máy chủ và NAS qua TCP/IP. NAS hoạt động với hệ thống tệp truyền thống NTFS hoặc NFS cho các dịch vụ tệp từ xa và chia sẻ dữ liệu. Tất cả bộ nhớ trên thiết bị đều được truy cập ở cấp độ tệp thông qua chia sẻ tệp.

Ưu điểm :
- Khả năng mở rộng: khi người dùng cần thêm dung lượng lưu trữ, các thiết bị lưu trữ NAS mới có thể được bổ sung và lắp đặt vào mạng.
- NAS cũng tăng cường khả năng chống lại sự cố cho mạng. Trong môi trường DAS, khi một máy chủ chứa dữ liệu không hoạt động thì toàn bộ dữ liệu đó không thể sử dụng được. Trong môi trường NAS, dữ liệu vẫn hoàn toàn có thể được truy nhập bởi người dùng. Các biện pháp chống lỗi và dự phòng tiên tiến được áp dụng để đảm bảo NAS luôn sẵn sàng cung cấp dữ liệu cho người sử dụng.

Nhược điểm :
- Với việc sử dụng chung hạ tầng mạng với các ứng dụng khác, việc lưu trữ dữ liệu có thể ảnh hưởng đến hiệu năng của toàn hệ thống (làm chậm tốc độ của LAN), điều này đặc biệt đáng quan tâm khi cần lưu trữ thường xuyên một lượng lớn dữ liệu.

![](https://sp-ao.shortpixel.ai/client/to_auto,q_glossy,ret_img,w_512,h_340/http://giaiphap.anhngoc.vn/wp-content/uploads/2020/12/NAS.gif)

#### Thành phần của NAS

- Phần cứng: là một máy chủ chứa đĩa hoặc ổ lưu trữ, bộ xử lý và RAM. Nó phụ trách thực hiện 2 yêu cầu là lưu trữ dữ liệu và chia sẻ tệp.

- Phần mềm: Được cấu hình sẵn và cài đặt trên phần cứng, triển khai trên hệ điều hành được nhúng trong phần cứng.

- Bộ chuyển đổi mạng: Người dùng truy cập các giao thức qua bộ chuyển đổi mạng, nó như là máy chủ trung tâm kết nối mọi thứ và định tuyến các yêu cầu.

- Protocol: Giao thức TCP kết hợp với các tệp thành gói và gửi chúng qua các giao thức Internet.

### SAN (Storage Area Network)

SAN là viết tắt của Storage Area Network, một loại mạng lưu trữ chuyên dụng cho việc kết nối các thiết bị lưu trữ như ổ cứng, đĩa quang, băng từ với các máy chủ. 
SAN cho phép các máy chủ truy cập vào các thiết bị lưu trữ như thể chúng là ổ đĩa cục bộ, nhưng lại có khả năng mở rộng và quản lý tốt hơn. SAN cũng hỗ trợ các tính năng cao cấp như sao lưu, phục hồi, sao chép và di chuyển dữ liệu giữa các thiết bị lưu trữ.

Sự khác biệt lớn nhất giữa hệ thống NAS và SAN là NAS quản lý chức năng file system của hệ điều hành còn SAN chỉ cung cấp dịch vụ lưu trữ theo khối và để các chức năng file system được thực hiện bởi máy client

![](https://sp-ao.shortpixel.ai/client/to_auto,q_glossy,ret_img,w_378,h_400/http://giaiphap.anhngoc.vn/wp-content/uploads/2020/12/SAN-378x400.gif)

Ưu điểm :

- SAN cung cấp hiệu suất cao hơn so với DAS và NAS vì quá trình xử lý lưu trữ được thực hiện trên một mạng tách biệt với mạng cục bộ (LAN). Di chuyển các tác vụ lưu trữ sang một SAN chuyên dụng đảm bảo rằng hiệu suất trên SAN không bị ảnh hưởng bởi tắc nghẽn lưu lượng trên mạng LAN. Nó cũng loại bỏ lưu lượng lưu trữ khỏi mạng LAN để giải phóng băng thông và cải thiện hiệu suất.

- SAN có thể bao gồm hàng nghìn thiết bị lưu trữ SAN và máy chủ lưu trữ có thể được mở rộng để đáp ứng nhu cầu kinh doanh đang phát triển. Các tổ chức có thể thêm máy chủ và thiết bị lưu trữ mới để xây dựng SAN khi nhu cầu dung lượng tăng lên. 

- Lưu trữ SAN có thể truy cập thông qua nhiều đường dẫn và vẫn độc lập với các ứng dụng mà nó hỗ trợ. Kết cấu mạng SAN có thể sử dụng các đường dẫn thay thế để duy trì tính khả dụng của bộ nhớ nếu xảy ra lỗi giao tiếp, đảm bảo rằng không có điểm lỗi nào giữa máy chủ và thiết bị lưu trữ. 

#### Các giao thức SAN :

Có nhiều giao thức được sử dụng để kết nối server và storage trong SAN, nhưng ba giao thức phổ biến nhất là:

- Fibre Channel (FC): Là một giao thức truyền tải dữ liệu qua cáp quang, có tốc độ cao (từ 1 Gbps đến 128 Gbps) và độ tin cậy cao. FC là giao thức truyền thống của SAN, được sử dụng rộng rãi trong các môi trường yêu cầu hiệu suất cao, như cơ sở dữ liệu, máy chủ ảo hoặc máy chủ lớn.

- Internet Small Computer System Interface (iSCSI): Là một giao thức truyền tải dữ liệu qua mạng Ethernet, có tốc độ thấp hơn FC (từ 1 Gbps đến 40 Gbps) nhưng chi phí thấp hơn và dễ triển khai hơn. iSCSI là giao thức phù hợp cho các môi trường yêu cầu khả năng mở rộng và linh hoạt, như máy chủ nhỏ hoặc máy chủ đám mây.

- Fibre Channel over Ethernet (FCoE): Là một giao thức kết hợp giữa FC và Ethernet, có tốc độ cao (từ 10 Gbps đến 100 Gbps) và chi phí thấp hơn FC. FCoE là giao thức mới của SAN, được sử dụng trong các môi trường yêu cầu hiệu suất cao và tiết kiệm chi phí, như trung tâm dữ liệu.

## Software-Defined Storage

là một hệ thống lưu trữ dữ liệu không phụ thuộc vào phần cứng, mà chúng sử dụng phần mềm để quản lý các thông tin dữ liệu. Với các hệ thống như SAN hoặc NAS thì phần cứng và phần mềm gắn liền với nhau, cùng phối hợp với nhau trong việc lưu trữ dữ liệu.

Sự xuất hiện của Software-Defined Storage giúp các doanh nghiệp có thể kết nối các tủ đĩa lưu trữ của nhiều hãng với nhau, tạo ra một nơi lưu trữ thống nhất và quản lý tất cả tại một nơi. Điều này giúp đơn giản hóa việc quản lý dữ liệu của doanh nghiệp.

Storage truyền thống :
![](https://static.wixstatic.com/media/a7fbb2_7e33798b379d4a07ab9248976d7d2109~mv2.jpg/v1/fill/w_740,h_249,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/a7fbb2_7e33798b379d4a07ab9248976d7d2109~mv2.jpg)

Software Defined Storage :
![](https://static.wixstatic.com/media/a7fbb2_0c4fd59691874d29931f0187c587dc2f~mv2.jpg/v1/fill/w_740,h_289,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/a7fbb2_0c4fd59691874d29931f0187c587dc2f~mv2.jpg)

### Ưu điểm

- Cải thiện bảo mật dữ liệu :
  - Mã hóa dữ liệu khi truyền và lưu trữ
  - Kiểm soát quyền truy cập dựa trên user roles hoặc policies.
  - Giám sát thời gian thực để phát hiện hành vi bất thường.
- Quản lý dữ liệu hiệu quả hơn
- Tính sẵn sàng cao

- Phân cấp dựa trên phần mềm: SDS chuyển tính năng quản lý và điều khiển tài nguyên lưu trữ vào phần mềm độc lập, giúp loại bỏ sự phụ thuộc vào phần cứng cụ thể. Điều này đảm bảo khả năng linh hoạt, tương thích và dễ dàng thay đổi, nâng cấp hoặc thay thế phần cứng.

- Ứng dụng linh hoạt: SDS có thể xử lý nhiều loại tài nguyên lưu trữ khác nhau như hệ thống tệp, đĩa cứng, hệ thống nhớ, đám mây, và cung cấp khả năng quản lý tập trung cho tất cả các tài nguyên này.

- Quản lý đơn giản: SDS mang lại sự đơn giản trong việc quản lý hệ thống lưu trữ. Người quản trị chỉ cần tương tác với giao diện phần mềm để cấu hình, theo dõi và quản lý tất cả các tài nguyên lưu trữ từ một nơi duy nhất.

- Mở rộng dễ dàng: SDS cho phép mở rộng tài nguyên lưu trữ một cách linh hoạt và dễ dàng để đáp ứng nhu cầu tăng trưởng của doanh nghiệp. Người dùng có thể thêm hoặc bớt tài nguyên lưu trữ theo yêu cầu mà không gặp sự cản trở từ phần cứng.

- Tích hợp dễ dàng: SDS có khả năng tích hợp với các công nghệ lưu trữ khác, hệ thống ảo hóa và công nghệ đám mây. Điều này tạo ra sự linh hoạt và tương thích để triển khai SDS cùng với các công nghệ hiện có trong môi trường IT của doanh nghiệp.

### Sự khác biệt giữa SDS và hệ thống lưu trữ truyền thống

- Kiến trúc: Trong hệ thống lưu trữ truyền thống, các tính năng và chức năng quản lý lưu trữ được tích hợp sẵn trong phần cứng. Điều này có nghĩa là doanh nghiệp phụ thuộc vào phần cứng cụ thể và việc quản lý và mở rộng tài nguyên lưu trữ phụ thuộc vào việc thay đổi và nâng cấp phần cứng. Trong khi đó, SDS tách biệt tính năng lưu trữ và quản lý từ phần cứng, cho phép doanh nghiệp quản lý và điều khiển tài nguyên lưu trữ thông qua phần mềm độc lập. Điều này mang lại tính linh hoạt cao hơn và khả năng quản lý tập trung cho SDS.

- Quản lý: Hệ thống lưu trữ truyền thống yêu cầu việc quản lý riêng biệt cho từng khối lượng công việc, ứng dụng hoặc phần cứng. Điều này tạo ra một môi trường phức tạp và cần nhiều công việc quản lý riêng lẻ. SDS cung cấp giao diện quản lý tập trung và đơn giản hóa quá trình quản lý các tài nguyên lưu trữ. Người quản trị có thể cấu hình, theo dõi và quản lý toàn bộ hạ tầng lưu trữ từ một điểm duy nhất, giảm thiểu sự phức tạp và tiết kiệm thời gian.

- Mở rộng: SDS cung cấp khả năng mở rộng linh hoạt và dễ dàng cho tài nguyên lưu trữ. Doanh nghiệp có thể thêm hoặc bớt tài nguyên lưu trữ theo nhu cầu mà không gặp sự cản trở từ phần cứng cụ thể. Trong khi đó, hệ thống lưu trữ truyền thống yêu cầu việc thay đổi hoặc nâng cấp phần cứng để mở rộng tài nguyên lưu trữ, điều này có thể gây ra gián đoạn và tăng chi phí.

- Hiệu suất: SDS thường có các tính năng tăng cường hiệu suất như bộ đệm thông minh, tối ưu hóa I/O và cân bằng tải tự động. Điều này giúp tăng cường hiệu suất hoạt động của hệ thống lưu trữ và cải thiện kết quả làm việc của các ứng dụng và dịch vụ. Trong khi đó, hệ thống lưu trữ truyền thống có thể không có các tính năng này và không có khả năng tối ưu hóa hiệu suất một cách linh hoạt.

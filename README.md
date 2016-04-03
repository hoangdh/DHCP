# Tìm hiểu về DHCP

### 1. Khái niệm

*DHCP là gì? Ưu điểm của DHCP*

**DHCP** là viết tắt của **Dynamic Host Configuration Protocol**, là giao thức Cấu hình Host Động được thiết kế làm giảm thời gian chỉnh cấu hình cho mạng TCP/IP bằng cách tự động gán các địa chỉ IP cho khách hàng khi họ vào mạng. Dich vụ DHCP là một thuận lới rất lớn đối với người điều hành mạng. Nó làm yên tâm về các vấn đề cố hữu phát sinh khi phải khai báo cấu hình thủ công. Nói một cách tổng quan hơn DHCP là dich vụ mang đến cho chúng ta nhiều lợi điểm trong công tác quản trị và duy trì một mạng TCP/IP như: 

- Tập chung quản trị thông tin về cấu hình IP. 
- Cấu hình động các máy. 
- Cấu hình IP cho các máy một cách liền mạch 
- Sự linh hoạt 
- Khả năng mở rộng. 

### 2. Chức năng: 
– Mỗi thiết bị trên mạng cơ sở TCP/IP phải có một địa chỉ IP duy nhất để truy cập mạng và các tài nguyên của nó. Không có DHCP, cấu hình IP phải được thực hiện một cách thủ công cho các máy tính mới, các máy tính di chuyển từ mạng con này sang mạng con khác, và các máy tính được loại bỏ khỏi mạng. 

– Bằng việc phát triển DHCP trên mạng, toàn bộ tiến trình này được quản lý tự động và tập trung. DHCP server bảo quản vùng của các địa chỉ IP và giải phóng một địa chỉ với bất cứ DHCP client có thể khi nó có thể ghi lên mạng. Bởi vì các địa chỉ IP là động hơn tĩnh, các địa chỉ không còn được trả lại một cách tự động trong sử dụng đối với các vùng cấp phát lại.

### 3. Các thuật ngữ trong DHCP:

- **DHCP Server:** máy quản lý việc cấu hình và cấp phát địa chỉ IP cho Client
- **DHCP Client:** máy trạm nhận thông tin cấu hình IP từ DHCP Server
- **Scope:** phạm vi liên tiếp của các địa chỉ IP có thể cho một mạng.
- **Exclusion Scope:** là dải địa chỉ nằm trong Scope không được cấp phát động cho Clients.
- **Reservation:** Địa chỉ đặt trước dành riêng cho máy tính hoặc thiết bị chạy các dịch vụ (tùy chọn này thường được thiết lập để cấp phát địa chỉ cho các Server, Printer,…..)
- **Scope Options:** các thông số được cấu hình thêm khi cấp phát IP động cho Clients như DNS Server(006), Router(003)

### 5. Các thông điệp DHCP:

- **DHCP Discover**: Thời gian đầu tiên một máy tính DHCP Client nỗ lực để gia nhập mạng, nó yêu cầu thông tin địa chỉ IP từ DHCP Server bởi việc broadcast một gói DHCP Discover. Địa chỉ IP nguồn trong gói là 0.0.0.0 bởi vì client chưa có địa chỉ IP. 
- **DHCP Offer**: Mỗi DHCP server nhận được gói DHCP Discover từ client đáp ứng với gói DHCP Offer chứa địa chỉ IP không thuê bao và thông tin định cấu hình TCP/IP bổ sung(thêm vào), chẳng hạn như subnet mask và gateway mặc định. Nhiều hơn một DHCP server có thể đáp ứng với gói DHCP Offer. Client sẽ chấp nhận gói DHCP Offer đầu tiên nó nhận được.
- **DHCP Request**: Khi DHCP client nhận được một gói DHCP Offer, nó đáp ứng lại bằng việc broadcast gói DHCP Request mà chứa yêu cầu địa chỉ IP, và thể hiện sự chấp nhận của địa chỉ IP được yêu cầu.
- **DHCP Acknowledge**: DHCP server được chọn lựa chấp nhận DHCP Request từ Client cho địa chỉ IP bởi việc gửi một gói DHCP Acknowledge. Tại thời điểm này, Server cũng định hướng bất cứ các tham số định cấu hình tuỳ chọn. Sự chấp nhận trên của DHCP Acknowledge, Client có thể tham gia trên mạng TCP/IP và hoàn thành hệ thống khởi động.
- **DHCP Nak**: Nếu địa chỉ IP không thể được sữ dụng bởi client bởi vì nó không còn giá trị nữa hoặc được sử dụng hiện tại bởi một máy tính khác, DHCP Server đáp ứng với gói DHCP Nak, và Client phải bắt đầu tiến trình thuê bao lại. Bất cứ khi nào DHCP Server nhận được yêu cầu từ một địa chỉ IP mà không có giá trị theo các Scope mà nó được định cấu hình với, nó gửi thông điệp DHCP Nak đối với Client. 
- **DHCP Decline**: Nếu DHCP Client quyết định tham số thông tin được đề nghị nào không có giá trị, nó gửi gói DHCP Decline đến các Server và Client phải bắt đầu tiến trình thuê bao lại.
- ****DHCP Release**: Một DHCP Client gửi một gói DHCP Release đến một server để giải phóng địa chỉ IP và xoá bất cứ thuê bao nào đang tồn tại.

### 6. Cơ chế hoạt động

<img src="http://i1363.photobucket.com/albums/r714/HoangLove9z/33550_zpsi3bzo3ua.jpg" />

**B1**: Client gửi một bản tin Discovery - có chứa thông tin client (MAC, Tên máy tính,...) với dạng Broadcast để "truy tìm" một DHCP Server để xin cấp phát địa chỉ IP
**B2**: Khi DHCP Server nhận được một bản tin Discovery sẽ gửi lại cho Client một bản tin Offer - chứa những thông tin IP,thời hạn cho thuê, GW, DNS Server,... dưới dạng Unicast
**B3**: Client gửi lại một bản tin Request cho Server, để xác nhận lại các thông tin
**B4**: Server trả về bản tin ACK để hoàn tất quá trình

### 6. Tham khảo:
- http://vdo.vn/cong-nghe-thong-tin/cac-khai-niem-co-ban-ve-dhcp.html
- https://en.wikipedia.org/wiki/Dynamic_Host_Configuration_Protocol

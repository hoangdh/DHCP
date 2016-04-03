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
##

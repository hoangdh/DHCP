## Hướng dẫn xem gói tin DHCP bằng Wireshark

*Bài viết về <a href="https://github.com/hoangdh/DHCP">DHCP</a>.*

### 1. Khởi động Wireshark

<img src="http://i.imgur.com/4j73Hvo.png" width=50% height=50% />

- Chọn Interface và bấm `Start` để bắt đầu

### 2. Giải phóng IP đang sử dụng

- Sử dụng câu lệnh `ipconfig /release` trên Windows Command Prompt

<img src="http://i.imgur.com/FcZIrGh.png" width=50% height=50% />

### 3. Xin cấp lại địa chỉ IP

- Sử dụng câu lệnh `ipconfig /renew` trên `cmd`

<img src="http://i.imgur.com/VgSgFOc.png" width=50% height=50% />

### 4. Lọc các gói tin DHCP

- Sau khi đã nhận được IP, chúng ta mở lại cửa sổ Wireshark
- Lọc gói tin DHCP bằng cách gõ `bootp` vào ô `Filter` và bấm `Apply`

<img src="http://i.imgur.com/HDMC0WL.png" width=50% height=50% />

### 5. Phân tích từng gói tin

#### Gói DHCP Discover

- Kích đúp chuột trái vào gói tin, ta sẽ xem được chi tiết của gói

Theo lý thuyết, Gói tin này được gửi Broadcast từ client để 'truy tìm' một DHCP Server và nó có thông tin L2 của client đó.

Nhìn vào hình để thấy điều đó là đúng!

<img src="http://i.imgur.com/21nrOLb.png" width=50% height=50% />

Và một số thông tin yêu cầu Server

<img src="http://i.imgur.com/ulVwujl.png" width=50% height=50% />

#### Gói Offer từ server

Gói này được Unicast đến Client

<img src="http://i.imgur.com/jkFGEgC.png" />

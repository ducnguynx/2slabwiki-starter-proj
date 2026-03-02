# Đề tài: Thiết kế hệ thống IoT thu thập dữ liệu cảm biến ánh sáng

## Mục đích

-  Giám sát môi trường.

- Ứng dụng điều chỉnh nguồn sáng thông minh.

- Kết hợp các cảm biến khác đưa ra đánh giá, dự đoán.

## Yêu cầu hệ thống

Thiết kế hệ thống IoT:

- Thu thập dữ liệu cảm biến ánh sáng theo thời gian thực, sử dụng vi điều khiển.

- Gửi và lưu trữ dữ liệu cảm biến lên web server thông qua Wifi.

- Hiển thị và giám sát dữ liệu cảm biến thông qua giao diện web.

### Mô hình hệ thống

![](/StarterProj_SystemOverview.svg)

### Yêu cầu công nghệ

#### 1. Thiết kế thiết bị cảm biến ánh sáng 

a. Cảm biến: module BH1750 

b. MCU + truyền thông WiFi: Module ESP32, không dùng kit 

c. Có 1 nút nhấn reset, 1 nút nhấn khác, 1 led báo (dự phòng thêm chức năng (mở rộng) 

d. Nguồn: 5V (lấy từ dây usb máy tính hoặc adapter 5V) 

e. Vẽ mạch sử dụng Altium, thiết kế nhỏ gọn, hợp lý, kích thước dưới 10x10cm. 

f. Lập trình vi điều khiển kết nối mạng WiFi, đọc cảm biến và gửi dữ liệu định kỳ tới phần mềm ứng dụng Web trên máy tính thông qua giao thức HTTP.  

**Ghi chú:** 

* Đối với sinh viên năm 2 vẽ mạch được sử dụng kit ESP32. 

* Đối với sinh viên năm 3 trở lên: vẽ mạch sử dụng chip ESP32, không sử dụng kit có sẵn.

#### 2. Phần mềm ứng dụng Web trên máy tính 

a. Chạy 1 HTTP server để cảm biến gửi dữ liệu, dữ liệu được lưu trữ vào 1 Database (SQLite, PostgreSQL hoặc MySQL).

b. Giao diện để hiển thị, giám sát dữ liệu cảm biến:

- Hiển thị, quản lý thông tin: vị trí, v.v.. của (các) cảm biến.

- Hiển thị cường độ ánh sáng tại vị trí theo thời gian thực.

- Thống kê, vẽ đồ thị dữ liệu ánh sáng theo thời gian.

c. Viết phần mềm sử dụng NodeJS, C++, hoặc Python Flask (tùy chọn 1 công nghệ để triển khai).

#### 3. (Tùy chọn) Các đầu việc nâng cao:

Sau khi đảm bảo các chức năng cơ bản, các bạn có thể tùy chọn các công việc nâng cao dưới đây để thực hiện:

- Phân tích cấu trúc gói tin TCP và HTTP sử dụng Wireshark.

- Cấu hình ESP32 (Cấu hình wifi, địa chỉ IP server đích) thông qua giao diện.

- Bảo mật cơ bản gói tin truyền nhận, sử dụng TLS/SSL.

- Hoặc có thể tự đề xuất các tính năng khác muốn triển khai với leader.

## Yêu cầu đầu ra

### Sản phẩm đầu ra

- Mạch cứng, phần mềm, file thiết kế mạch cứng và source code phần mềm.

- Demo toàn hệ thống.

- Silde báo cáo

Nâng cao:

- Tài liệu khảo sát, giải thích tín hiệu / cấu trúc gói tin 
truyền thông giữa:

    - Cảm biến và vi điều khiển.

    - Vi điều khiển và server.

### Kiến thức học được

- Cơ bản về 1 hệ thống IoT.

- Nguyên lý cảm biến ánh sáng.

- Cơ bản nguyên lý mạng máy tính và giao thức truyền thông 

- Thiết kế và triển khai mạch cứng, sử dụng các công cụ thiết kế.

- Kỹ thuật lập trình: lập trình vi điều khiển, phần mềm ứng dụng (server, giao diện, cơ sở dữ liệu).

## Tài liệu hướng dần

Tài liệu hướng dẫn xem [ở đây](/README.md)

--- 

🧑‍💻 Happy Hacking! 🧑‍💻

**© 2026 by Thai-Son Nguyen x Anh-Duc Nguyen | Sensor Lab.**
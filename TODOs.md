# TODOs

Dự án này bao gồm việc thiết kế một thiết bị cảm biến cường độ ánh sáng có khả năng kết nối và gửi dữ liệu qua WiFi đến một ứng dụng web trên máy tính, dữ liệu sẽ được lưu vào một cơ sở dự liệu

Dưới đây sẽ là gợi ý các đầu việc để các bạn có thể triển khai dự án một cách mượt mà nhất.

> LƯU Ý: Các giai đoạn có thể triển khai song song với nhau, mỗi bạn có thể làm một phần. Tất nhiên, về mặt kiến thức, các bạn cần có hiểu biết rõ về phần cứng và phần mềm.

---

## Giai đoạn 1: Thiết kế và Chế tạo phần cứng (Mạch cảm biến)

Đây là giai đoạn tập trung vào việc thiết kế và lắp ráp thiết bị vật lý.

### Danh sách công việc:

-   **Linh kiện - Đã chọn:**
    -   Cảm biến ánh sáng: Module BH1750
    -   Vi điều khiển (MCU) + WiFi: Module ESP32 (sinh viên năm 3 trở lên không dùng Kit - tự thiết kế mạch PCB)
    -   Nút nhấn: 1 nút reset, 1 nút boot, 1 nút chức năng
    -   Đèn báo: 1 LED
    -   Nguồn: Mạch nguồn 5V (từ USB hoặc adapter)

-   **Thiết kế mạch:**
    -   Vẽ sơ đồ nguyên lý (schematic) bằng phần mềm Altium.
    -   Thiết kế mạch in (PCB layout) với kích thước dưới 10x10cm, đảm bảo nhỏ gọn và hợp lý.

-   **Lắp mạch - Năm 3:**
    -   Đặt làm mạch in (PCB).
    -   Hàn linh kiện lên bo mạch.
    -   Kiểm tra (đo thông mạch, kiểm tra nguồn).

---

## Giai đoạn 2: Lập trình cho Vi điều khiển

Giai đoạn này tập trung vào việc lập trình cho ESP32 để đọc dữ liệu từ cảm biến và gửi đi.

### Danh sách công việc:

-   **Cài đặt môi trường lập trình:**
-   -   Nếu dùng ESP32 IDF: Cài đặt IDE theo hướng dẫn của hãng.
    <!-- -   Nếu dùng Arduino Framework: Cài đặt Arduino IDE hoặc PlatformIO (với các bạn dùng VSCode là editor chính).
     -->

-   **Lập trình các module chức năng:**
    -   Viết code đọc dữ liệu từ cảm biến BH1750 qua giao tiếp I2C (Thư viện)
    -   Viết code kết nối vào mạng WiFi (Thư viện)
    -   Lập trình chức năng cho các nút nhấn và đèn LED
    -   Viết code gửi dữ liệu cảm biến định kỳ lên server qua giao thức HTTP (hoặc bất kì giao thực nào các bạn nắm rõ)

-   **Tích hợp và Hoàn thiện:**
    -   Kết hợp các module chức năng thành một chương trình hoàn chỉnh.
    -   **[Nâng cao]** Xử lý các edge case (mất kết nối WiFi, cảm biến lỗi,...).

---

## Giai đoạn 3: Lập trình web

Xây dựng một ứng dụng web đơn giản để nhận và hiển thị dữ liệu từ cảm biến.

### Danh sách công việc:

-   **Lựa chọn công nghệ:**
    -   Chọn một trong các ngôn ngữ để xây dựng web, các em chọn cái nào cũng được, nhưng để có sự hỗ trợ tốt nhất: JavaScript, C++, hoặc Python FastAPI

-   **Xây dựng Backend (HTTP Server)**
    -   Tạo một server có khả năng lắng nghe và nhận dữ liệu từ yêu cầu (request) của ESP32
    -   Xử lý dữ liệu nhận được và lưu trữ ở CSDL.

-   **Xây dựng Frontend (Giao diện người dùng)**
    -   Thiết kế một giao diện web đơn giản.
    -   Hiển thị giá trị cường độ ánh sáng nhận được từ cảm biến một cách trực quan.ss

---

## Giai đoạn 4: Hoàn thiện dự án

Đây là giai đoạn cuối cùng để tổng hợp kết quả và chuẩn bị báo cáo.

### Danh sách công việc:

-   **Chuẩn bị báo cáo:**
    -   Viết tài liệu báo cáo chi tiết về quá trình thực hiện, các quyết định thiết kế, và kết quả đạt được.
    -   Chuẩn bị slide thuyết trình để trình bày dự án.

-   **Kiểm tra và Bàn giao:**
    -   Kiểm tra lại toàn bộ hệ thống (mạch và phần mềm) để đảm bảo hoạt động ổn định.
    -   Chuẩn bị sản phẩm cuối cùng bao gồm:
        -   1 mạch cảm biến ánh sáng hoàn chỉnh
        -   Source code 
        -   Slide báo cáo
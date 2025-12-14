# HƯỚNG DẪN BỐ CỤC SLIDE BÁO CÁO CUỐI KỲ

## Lưu ý chung quan trọng
1.  **Tư duy quan trọng hơn kết quả:** Mạch của các em có thể chạy hay không chạy cũng được, ai cũng phải bắt đầu từ đâu đó. Anh nghĩ rằng, nếu mạch các em không chạy, nhưng các em đưa ra các giải thích và phương án hợp lý để làm mạch chạy, các em hoàn toàn đạt yêu cầu.
2.  **Hãy trình bày bằng hình ảnh:** Hạn chế tối đa việc copy-paste code hoặc đoạn văn dài lên slide. Sử dụng sơ đồ khối (Block Diagram), lưu đồ thuật toán (Flowchart) và hình ảnh thực tế.
3.  **Quản lý thời gian:** Các em có 15 phút. Chỉ 15 phút thôi nhé, chủ yếu các em nên nói các vấn đề mình gặp và tư duy giải quyết các vấn đề đó. Nếu có gì hay trong dự án mà các em đã làm được thì cũng nên cho vào.

## Bố cục Slide

Để tránh tình trạng báo cáo lan man, không rõ trọng tâm & rõ ý, các em nên theo bố cục như sau:

### Phần 1: Tổng quan (1-2 Slide)
**Slide 1: Giới thiệu đề tài & Thông tin sinh viên**
* Tên đề tài, Tên sinh viên.

**Slide 2: Sơ đồ khối hệ thống**
* Vẽ sơ đồ kết nối giữa các khối, giải thích luồng hoạt động cơ bản (giải thích dễ hiểu thôi tưởng tượng anh là trẻ con học lớp 1 nhé).

### Phần 2: Thiết kế Phần cứng (3-4 Slide)

**Slide 3: Nguyên lý mạch (Schematic Design)**
* Các em nên có sơ đồ nguyên lý (chụp rõ nét hoặc crop các phần quan trọng).
* Các em có thể nói một số ý sau đây
    * Khối nguồn: Làm sao hạ từ 5V xuống 3.3V cho ESP32? (Dùng LDO nào? Tụ lọc ra sao?).
    * Mạch Boot/Reset: Thiết kế mạch nạp/reset cho ESP32 như thế nào để nó hoạt động ổn định ?
    * vân vân, chủ yếu nếu em bị lỗi phần cứng thì đoạn này giải thích thêm cho anh và thêm phương án nữa.
    

**Slide 4: Thiết kế mạch in**
* Hình ảnh Layout 2D và 3D.
* Các em có thể nói một số ý sau đây
    * Tại sao sắp xếp linh kiện như vậy? (Ví dụ: Đặt tụ lọc gần chân nguồn IC, vân vân, nếu mạch của các em có điểm yếu, các em cũng có thể nói ra ở đây luôn, nhớ lại là anh chấm tư duy, nếu các em có phát hiện ra mà nói được đúng thì vẫn đạt yêu cầu)
    * Kích thước mạch thực tế là bao nhiêu? (Yêu cầu < 10x10cm, em đã tối ưu nhỏ gọn nhất có thể chưa?).

**Slide 5: Hoàn thiện sản phẩm**
* Hình ảnh mạch thực tế sau khi hàn.
* Đánh giá chất lượng mối hàn, độ thẩm mỹ và bố cục.

### Phần 3: Thiết kế Phần mềm - Firmware & Web (3 Slide)

**Slide 6: Lưu đồ thuật toán**
* Vẽ lưu đồ hoạt động của ESP32:
    * Khởi động ➔ Kết nối WiFi ➔ Đọc BH1750 ➔ Gửi HTTP Request ➔ Chờ (Delay) ➔ Lặp lại.
    * Xử lý nút nhấn và LED báo trạng thái như thế nào?
    * vân vân, đoạn này các em nên nói một cách cực kì dễ hiểu về cách các thiết bị hoạt động (sẽ bị hỏi thêm đấy nên các em nhớ xem kĩ nhé)

**Slide 7: Giao thức truyền thông**
* Định dạng dữ liệu gửi đi (JSON hay Plain text?).
* Ví dụ gói tin: `POST /api/data { "lux": 150, "device_id": "esp32_01" }`.
* Tần suất gửi dữ liệu (bao lâu gửi 1 lần?).

**Slide 8: Ứng dụng Web**
* Giao diện Web (Screenshot): Hiển thị giá trị Lux.
* Giải thích ngắn gọn cách Server nhận dữ liệu và hiển thị (API Endpoint).
* Cái này tôi không nghĩ ra gì thêm mấy Sơn giúp tôi nhé

### Phần 4: Kết quả & Thảo luận (2-3 Slide)

**Slide 9: Kết quả thực nghiệm**
* Video ngắn (hoặc Demo trực tiếp) quy trình: Che cảm biến ➔ Web cập nhật giá trị.

**Slide 10: Vấn đề gặp phải & Cách giải quyết (QUAN TRỌNG)**

Tất nhiên nếu các em không có vấn đề gì thì không cần nói nhé. Nhưng nhóm nào mạch không chạy hoặc hệ thống chưa hoàn chỉnh thì rất nên có phần này.

* Ví dụ:
    * *Vấn đề:* ESP32 không nạp được code khi hàn lên mạch.
    * *Nguyên nhân:* Sai chân IO0 hoặc thiếu tụ lặp.
    * *Giải quyết:* Câu dây hoặc thay đổi thiết kế.
    * *Vấn đề:* Giá trị cảm biến bị nhiễu.
    * *Giải quyết:* Lấy trung bình cộng mẫu đo.

**Slide 11: Kết luận & Hướng phát triển**
* Tự đánh giá: Đã hoàn thành bao nhiêu % yêu cầu?
* Mở rộng: Nếu có thêm 2 tuần, bạn sẽ làm gì? (Ví dụ: Vẽ đồ thị thời gian thực trên Web, thêm Database lưu trữ, dùng MQTT thay vì HTTP...).

*Chúc các bạn hoàn thành tốt báo cáo!*
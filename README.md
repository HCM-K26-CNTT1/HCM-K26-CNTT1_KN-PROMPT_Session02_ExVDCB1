# Bài Tập: Sửa Đổi Prompt Thiếu Cấu Trúc Ràng Buộc Định Dạng

---

## Phần 1: Phân tích lỗi của Prompt cũ

Câu lệnh ban đầu: *"Hãy giải thích ngắn gọn các nội dung của CREATE, Few-shot, Ép định dạng JSON/Table."* do không có câu lệnh cấm giao tiếp xã giao và không ép khuôn mẫu trình bày nên AI thường sinh ra 3 phần văn bản thừa thãi sau:

1. **Lời chào mở đầu (Introductory fluff):** Các câu mang tính chất xã giao như *"Chào bạn, rất vui được hỗ trợ bạn tìm hiểu về..."* hoặc *"Dưới đây là phần giải thích ngắn gọn về các khái niệm bạn yêu cầu:"*.
2. **Câu dẫn nối chuyển ý (Filler text):** Các đoạn văn dẫn dắt rườm rà trước và sau mỗi khái niệm thay vì đi thẳng vào định nghĩa cốt lõi.
3. **Lời kết chúc mừng/gợi mở (Closing remarks):** Các câu kết thúc thừa ở cuối như *"Hy vọng những thông tin trên hữu ích cho việc học tập của bạn! Nếu cần thêm ví dụ, hãy cho mình biết nhé."*

*(Tác hại: Khi sao chép vào tài liệu học tập hoặc báo cáo, người dùng mất công bôi đen xóa bỏ các phần thừa này và định dạng lại từ đầu).*

---

## Phần 2: Viết Prompt tối ưu (Đã bổ sung ràng buộc định dạng)

Dưới đây là câu lệnh đã được tối ưu hóa bằng cách thêm các quy tắc ép định dạng gạch đầu dòng và từ khóa cấm viết thừa:

```text
[Nhiệm vụ]
Giải thích súc tích khái niệm và công dụng của 3 kỹ thuật Prompting: Khung CREATE, Few-shot, và Ép định dạng JSON/Table.

[Quy tắc định dạng bắt buộc]
- Trình bày dưới dạng danh sách gạch đầu dòng (bullet points) phân cấp rõ ràng.
- Mỗi khái niệm chỉ gói gọn trong tối đa 2 gạch đầu dòng (1 dòng định nghĩa, 1 dòng ứng dụng thực tế).
- In đậm tên của từng khái niệm.

[Ràng buộc nghiêm ngặt - Cấm viết thừa]
- Đi thẳng ngay vào gạch đầu dòng đầu tiên.
- Tuyệt đối KHÔNG viết lời chào mở đầu, KHÔNG viết câu dẫn chuyển đoạn và KHÔNG viết lời kết thúc hay câu hỏi gợi mở ở cuối.

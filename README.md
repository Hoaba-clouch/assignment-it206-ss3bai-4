# [Phân tích] CHỌN CHIẾN LƯỢC PHÂN RÃ EPIC HỦY CHUYẾN GHÉP

## Phần 1 - Đề xuất 2 chiến lược phân rã Epic

**Epic:** "Hủy chuyến ghép"

### Chiến lược 1: Phân rã theo quy tắc nghiệp vụ / Dòng giá trị (By Business Rule / Value Stream)

Chiến lược này tập trung vào việc phân tách Epic dựa trên các quy tắc nghiệp vụ và các giai đoạn khác nhau của luồng hủy chuyến, mỗi phần mang lại một giá trị nhất định cho người dùng hoặc hệ thống.

**Các Feature tạo ra:**
*   **Feature 1: Hủy chuyến không phát sinh phí**
    *   Cho phép khách hàng hủy chuyến khi tài xế chưa nhận chuyến, không áp dụng phí. 
*   **Feature 2: Hủy chuyến có phát sinh phí**
    *   Cho phép khách hàng hủy chuyến khi tài xế đã nhận chuyến, áp dụng phí hủy 10.000đ. 
*   **Feature 3: Thông báo và cập nhật giá cho hành khách còn lại**
    *   Hệ thống tự động tính toán lại giá chuyến đi cho các khách hàng còn lại và gửi thông báo kịp thời. 
*   **Feature 4: Ghi nhận và quản lý phí hủy**
    *   Hệ thống ghi nhận và xử lý các khoản phí hủy phát sinh. 

### Chiến lược 2: Phân rã theo các thành phần hệ thống / Lớp kỹ thuật (By System Components / Technical Layers)

Chiến lược này tập trung vào việc phân tách Epic dựa trên các thành phần hoặc lớp kỹ thuật cấu tạo nên tính năng, thường liên quan đến kiến trúc hệ thống.

**Các Feature tạo ra:**
*   **Feature 1: Giao diện người dùng cho việc hủy chuyến**
    *   Phát triển các màn hình và nút bấm để khách hàng có thể yêu cầu hủy chuyến. 
*   **Feature 2: Module tính toán và áp dụng phí hủy**
    *   Xây dựng logic để xác định có áp dụng phí hủy hay không và tính toán mức phí. 
*   **Feature 3: Module thông báo và cập nhật dữ liệu chuyến đi**
    *   Phát triển cơ chế để gửi thông báo cho các bên liên quan (khách còn lại, tài xế) và cập nhật trạng thái, giá cước chuyến đi trong cơ sở dữ liệu. 
*   **Feature 4: Module quản lý dữ liệu hủy chuyến**
    *   Thiết kế và triển khai cơ sở dữ liệu để lưu trữ thông tin liên quan đến các yêu cầu và trạng thái hủy chuyến. 

## Phần 2 - So sánh 2 chiến lược

| Tiêu chí INVEST | Chiến lược 1: Theo quy tắc nghiệp vụ / Dòng giá trị | Chiến lược 2: Theo thành phần hệ thống / Lớp kỹ thuật |
| :-------------- | :------------------------------------------------ | :---------------------------------------------------- |
| **Independent** | **(+)** Các feature tương đối độc lập (ví dụ: hủy miễn phí có thể triển khai trước hủy có phí). | **(–)** Các feature phụ thuộc chặt chẽ vào nhau (UI cần logic, logic cần DB, thông báo cần dữ liệu). Rất khó triển khai độc lập. |
| **Small**       | **(+)** Mỗi feature có phạm vi rõ ràng, có thể hoàn thành trong 1-2 Sprint và bàn giao giá trị.             | **(–)** Dù từng module có vẻ nhỏ về mặt kỹ thuật, nhưng không thể mang lại giá trị hoàn chỉnh cho người dùng nếu thiếu các module khác. |
| **Valuable**    | **(+)** Mỗi feature mang lại giá trị nghiệp vụ trực tiếp cho người dùng hoặc tổ chức (ví dụ: khách hủy miễn phí ngay lập tức có giá trị cho khách). | **(–)** Bản thân mỗi feature không trực tiếp mang lại giá trị cho người dùng cuối. Khách hàng không thể 
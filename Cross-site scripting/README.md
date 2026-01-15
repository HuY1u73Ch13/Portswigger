## Cross-site Scripting (XSS)
### Định nghĩa
Cross-site Scripting (XSS) là lỗ hổng bảo mật cho phép attacker chèn các đoạn mã độc (thường là JavaScript) vào giao diện của ứng dụng web mà người dùng khác sẽ truy cập. Khi nạn nhân tải trang, trình duyệt sẽ coi đoạn mã độc này là một phần hợp lệ của website và thực thi nó. Điều này dẫn đến việc attacker có thể đánh cắp cookie, session token, điều hướng người dùng hoặc thực hiện các hành động thay mặt nạn nhân.

### Những chỗ thường dính
- Các ô input cho phép nhập liệu văn bản (Thanh tìm kiếm, Form bình luận, Contact form).
- Tham số trên URL (Query Parameters) được hiển thị lại trên trang (Reflected XSS).
- Thông tin profile người dùng (Tên hiển thị, Bio, Avatar URL) được lưu vào database (Stored XSS).
- Các đoạn mã JavaScript xử lý dữ liệu từ URL (location.hash, location.search) để ghi vào DOM (DOM-based XSS).
- Error Message hiển thị lại nội dung input sai của người dùng mà không mã hóa (encode).
- File upload (tên file độc hại hoặc file SVG chứa script).

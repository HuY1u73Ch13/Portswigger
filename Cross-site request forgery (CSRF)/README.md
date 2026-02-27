## Cross-Site Request Forgery (CSRF)
### Định nghĩa
CSRF (Giao thức giả mạo yêu cầu chéo trang) là một lỗ hổng bảo mật cho phép attacker đánh lừa trình duyệt của nạn nhân thực hiện các hành động không mong muốn trên một ứng dụng web mà họ đã đăng nhập.
Về bản chất, attacker lợi dụng sự tin tưởng của ứng dụng đối với trình duyệt của người dùng. Khi nạn nhân truy cập vào một trang web độc hại, trang web đó sẽ gửi một request ngầm đến ứng dụng mục tiêu. Vì trình duyệt tự động đính kèm Cookie/Session, ứng dụng sẽ xử lý request đó như một yêu cầu hợp lệ từ chính chủ.

### Những chỗ thường dính
- Các chức năng thay đổi trạng thái: Đổi mật khẩu, cập nhật email, chuyển tiền, hoặc xóa dữ liệu mà không yêu cầu xác nhận lại.
- Sử dụng Cookie để quản lý phiên (Session): Ứng dụng chỉ dựa vào Cookie tự động để xác thực người dùng mà không có cơ chế bảo vệ bổ sung.
- Thiếu Anti-CSRF Token: Các form hoặc API không đi kèm mã token ngẫu nhiên, duy nhất cho mỗi phiên làm việc.
- Cấu hình CORS quá lỏng lẻo: Cho phép mọi domain (Access-Control-Allow-Origin: *) gửi request có kèm credentials.
- Sử dụng phương thức GET cho các tác vụ nhạy cảm: Dễ dàng bị khai thác thông qua thẻ <img> hoặc link ẩn.

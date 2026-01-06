## Access Control

### Định nghĩa
Access Control Vulnerability xảy ra khi hệ thống **không kiểm soát đúng quyền truy cập**, cho phép người dùng thực hiện hành động hoặc truy cập tài nguyên **ngoài phạm vi được cấp phép**.  
Đây là một trong những lỗ hổng **nghiêm trọng và phổ biến nhất**.

### Những chỗ thường dính
- Thay đổi `id`, `userId`, `orderId` trên URL hoặc request (IDOR)
- Truy cập URL admin bằng tài khoản thường
- API không kiểm tra quyền theo từng object
- Chức năng ẩn trên UI nhưng backend không chặn

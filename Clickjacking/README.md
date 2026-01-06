## Clickjacking

### Định nghĩa
Clickjacking là kỹ thuật lừa người dùng **click vào một nội dung bị che bởi iframe**, từ đó thực hiện hành động ngoài ý muốn (đổi mật khẩu, xác nhận giao dịch…).

### Những chỗ thường dính
- Trang admin
- Trang đổi mật khẩu
- Trang xác nhận giao dịch
- Website không cấu hình `X-Frame-Options` hoặc `CSP frame-ancestors`

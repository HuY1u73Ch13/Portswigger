## Server-Side Request Forgery (SSRF)

### Định nghĩa
SSRF xảy ra khi attacker ép server **gửi request thay mình** đến các tài nguyên nội bộ hoặc bên ngoài, dẫn đến lộ hệ thống nội bộ hoặc metadata cloud.

### Những chỗ thường dính
- Fetch URL
- Import data từ URL
- Webhook
- PDF/Image generator
- API đọc URL

# Web Application Vulnerabilities – Definitions & Common Attack Surfaces

Tài liệu này tổng hợp các lỗ hổng web phổ biến, bao gồm **định nghĩa chi tiết** và **những vị trí thường xuất hiện khi pentest**.

---

## API Testing

### Định nghĩa
API Testing trong bảo mật là quá trình kiểm tra các API backend nhằm phát hiện các lỗ hổng liên quan đến **xác thực, phân quyền, kiểm soát dữ liệu đầu vào và logic xử lý**.  
API thường được thiết kế để phục vụ frontend (web/mobile), nhưng nếu thiếu kiểm soát, attacker có thể gọi trực tiếp API để thao túng dữ liệu hoặc truy cập trái phép.

### Những chỗ thường dính
- API cho mobile app hoặc SPA (React, Angular, Vue)
- Endpoint `/api/*`
- API nội bộ bị expose ra internet
- API chỉ kiểm tra token nhưng không kiểm tra role
- API tin tưởng dữ liệu gửi từ client (price, role, status)

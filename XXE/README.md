## XML External Entity (XXE)

### Định nghĩa
XXE (XML External Entity) là lỗ hổng xảy ra khi ứng dụng **xử lý dữ liệu XML mà không tắt hoặc kiểm soát External Entity**, cho phép attacker khai báo entity trỏ tới tài nguyên bên ngoài.  
Thông qua XXE, attacker có thể **đọc file hệ thống, thực hiện SSRF, dò mạng nội bộ hoặc gây từ chối dịch vụ (DoS)**.

Lỗ hổng này thường xuất hiện trong các hệ thống:
- Sử dụng XML làm định dạng dữ liệu
- Dùng parser XML mặc định, cấu hình không an toàn
- Tin tưởng dữ liệu XML từ client

### Những chỗ thường dính
- SOAP API
- API nhận XML payload
- Upload file XML, SVG
- SAML authentication
- Web service cũ (legacy system)
- Chức năng import/export XML

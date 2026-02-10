## CORS Vulnerabilities

### Định nghĩa
CORS Vulnerabilities là các lỗ hổng xảy ra khi máy chủ web cấu hình header Access-Control-Allow-Origin thiếu chặt chẽ, phá vỡ cơ chế bảo vệ Same-Origin Policy (SOP) của trình duyệt. Mặc định, trình duyệt chặn các trang web lạ đọc dữ liệu của bạn. Tuy nhiên, nếu server "tin tưởng" sai đối tượng (ví dụ: phản hồi lại bất kỳ Origin nào gửi đến), attacker có thể lừa trình duyệt của nạn nhân gửi request và đọc trộm dữ liệu nhạy cảm trả về từ server đó.

### Những chỗ thường dính
- Các API chứa dữ liệu nhạy cảm (thông tin cá nhân, lịch sử giao dịch, token) yêu cầu xác thực bằng Cookie/Session.
- Server phản hồi header Access-Control-Allow-Origin dựa trên giá trị của header Origin trong request gửi lên (Reflected Origin).
- Cấu hình cho phép Origin: null (thường gặp khi test local hoặc trong các iframe sandbox).
- Các Regex kiểm tra domain bị lỗi (ví dụ: định cho phép bank.com nhưng lại cho phép cả bank.com.evil.site).
- Môi trường Development hoặc Staging (thường được mở toang * để tiện debug).

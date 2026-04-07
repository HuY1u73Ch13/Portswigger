## Web LLM Attacks
### Định nghĩa
Web LLM Attacks là kỹ thuật tấn công nhắm vào các ứng dụng tích hợp Mô hình ngôn ngữ lớn (LLM). Thay vì tấn công trực tiếp vào lõi AI, attacker thao túng đầu vào (prompt) để lừa LLM thực thi các hành động ngoài ý muốn như: truy xuất dữ liệu nhạy cảm, gọi API trái phép hoặc thực thi mã độc thông qua các quyền hạn mà ứng dụng đã cấp cho AI.
### Những chỗ thường dính
- Chatbot hỗ trợ khách hàng: Có quyền truy cập vào thông tin tài khoản hoặc đơn hàng.
- Tính năng tóm tắt (Summarization): LLM đọc nội dung từ URL hoặc file do người dùng cung cấp (dễ dính Indirect Prompt Injection).
- LLM có tích hợp Plugin/Function Calling: AI được quyền gọi các hàm gửi email, truy vấn database, hoặc đọc hệ thống file.
- Hệ thống AI nội bộ: Tin tưởng tuyệt đối vào kết quả trả về từ LLM mà không qua bước kiểm tra (sanitization).
- Giao diện hiển thị kết quả AI: Hiển thị trực tiếp phản hồi của LLM lên trình duyệt (dễ dính Stored XSS).
### Các kỹ thuật tấn công chính
- Prompt Injection: Tiêm lệnh độc hại để ghi đè chỉ thị hệ thống.
- Insecure Output Handling: LLM sinh ra mã độc (XSS/SQLi) và ứng dụng thực thi mã đó.
- Sensitive Data Leaking: Lừa LLM tiết lộ bí mật kinh doanh hoặc dữ liệu cá nhân trong tập huấn luyện/System prompt.
- LLM-driven SSRF: Thao túng LLM để nó gửi request đến các dịch vụ nội bộ không được expose.

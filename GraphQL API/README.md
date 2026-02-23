## GraphQL API Testing

### Định nghĩa
GraphQL là một ngôn ngữ truy vấn (query language) cho API, cho phép client yêu cầu chính xác những dữ liệu mình cần và không hơn.
Trong bảo mật, kiểm thử GraphQL tập trung vào việc khai thác cách server xử lý các truy vấn phức tạp. Khác với REST có nhiều endpoint (/getUsers, /deleteItem), GraphQL thường chỉ có duy nhất một endpoint (thường là /graphql). Attacker có thể lợi dụng cấu trúc này để "hỏi" server những thông tin nhạy cảm hoặc làm sập hệ thống bằng các truy vấn lồng nhau vô tận.
### Những chỗ thường dính (Vulnerabilities)
- Introspection Queries: Tính năng tự giới thiệu của GraphQL. Nếu không tắt, attacker có thể lấy toàn bộ schema (cấu trúc database, các hàm, các trường dữ liệu) của hệ thống.
- BOLA/IDOR (Broken Object Level Authorization): Truy vấn trực tiếp ID của người dùng khác trong câu query (ví dụ: user(id: "admin") { password_hash }) do server chỉ check login mà không check quyền sở hữu dữ liệu.
- GraphQL Injection: Tương tự SQL Injection, nhưng xảy ra khi dữ liệu đầu vào trong các arguments của query không được filter kỹ, dẫn đến việc can thiệp vào logic xử lý phía sau.
- Circular Queries (DoS): Gửi các truy vấn lồng nhau liên tục (A gọi B, B gọi lại A) khiến server tốn tài nguyên xử lý dẫn đến treo máy (Denial of Service).
- Field Suggestions: Ngay cả khi tắt Introspection, nếu attacker gõ sai tên trường, server có thể gợi ý: "Ý bạn có phải là 'admin_password' không?". Điều này làm lộ tên các trường nhạy cảm.

Cách phòng thủ cơ bản
Disable Introspection ở môi trường Production.

Query Depth Limiting: Giới hạn độ sâu của các truy vấn lồng nhau để tránh DoS.

Whitelisting: Chỉ cho phép thực thi các câu query đã được định nghĩa sẵn (Persisted Queries).

Strict Authorization: Kiểm tra quyền hạn ở mức Field-level (từng trường dữ liệu) thay vì chỉ kiểm tra ở mức Endpoint.

## NoSQL Injection

### Định nghĩa
NoSQL Injection xảy ra khi dữ liệu đầu vào của người dùng được sử dụng trực tiếp trong truy vấn NoSQL (MongoDB, Firebase, CouchDB…) mà **không được validate**, cho phép bypass logic hoặc truy xuất dữ liệu trái phép.

### Những chỗ thường dính
- Login API
- Search / filter
- API nhận JSON object
- Query động dựa trên input

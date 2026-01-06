## File Upload

### Định nghĩa
File Upload Vulnerability xảy ra khi ứng dụng cho phép upload file nhưng **không kiểm soát chặt loại file, nội dung hoặc vị trí lưu trữ**, có thể dẫn đến RCE, XSS hoặc lộ dữ liệu.

### Những chỗ thường dính
- Upload avatar
- Upload tài liệu
- Import dữ liệu
- Upload qua API
- Hệ thống CMS

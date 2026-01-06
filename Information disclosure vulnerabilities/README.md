## Information Disclosure Vulnerabilities

### Định nghĩa
Information Disclosure là lỗ hổng khiến hệ thống **vô tình tiết lộ thông tin nhạy cảm**, hỗ trợ attacker trong các cuộc tấn công tiếp theo.

### Những chỗ thường dính
- Error message chi tiết (stack trace)
- Response API dư thừa dữ liệu
- File `.env`, `.git`, backup
- Log file
- Header HTTP

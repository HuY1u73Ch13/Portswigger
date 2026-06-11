## HTTP Request Smuggling
### Định nghĩa
HTTP Request Smuggling trong bảo mật là một lỗ hổng phát sinh từ sự bất đồng bộ trong cách phân tích cú pháp (parsing) yêu cầu HTTP giữa các máy chủ tiền sảnh (Front-end/Load Balancer/Proxy) và máy chủ hậu sảnh (Back-end).
Khi hai máy chủ không thống nhất về cách xác định điểm kết thúc của một request (thường là sự xung đột giữa header Content-Length và Transfer-Encoding), attacker có thể tạo ra một request mập mờ để "buôn lậu" một phần payload độc hại vào bộ đệm của Back-end. Payload mắc kẹt này sau đó sẽ tự động bị nối vào request của một người dùng bất kỳ tiếp theo, cho phép attacker vượt qua cơ chế bảo mật, đánh cắp phiên người dùng hoặc đầu độc bộ nhớ cache.

### Những chỗ thường dính
- Hệ thống có kiến trúc nhiều tầng, nơi Front-end chuyển tiếp nhiều request đến Back-end qua cùng một kết nối TCP (keep-alive connection).
- Môi trường web có sử dụng Load Balancer, Reverse Proxy (như Nginx, HAProxy), CDN hoặc WAF nhưng sử dụng thư viện/cấu hình phân tích HTTP khác với máy chủ ứng dụng.
- Môi trường sử dụng HTTP/1.1 có hỗ trợ nhận dữ liệu dạng khối (header Transfer-Encoding: chunked).
- Các hệ thống thực hiện hạ cấp giao thức (downgrade) từ HTTP/2 ở mặt Front-end xuống HTTP/1.1 ở mặt Back-end nhưng không làm sạch (sanitize) kỹ các header.
- Các cụm server có sự chênh lệch trong việc ưu tiên xử lý header: Front-end tin vào Content-Length còn Back-end tin vào Transfer-Encoding (lỗi CL.TE), hoặc ngược lại (lỗi TE.CL).

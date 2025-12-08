## Phát hiện tiêm NoSQL
* <img width="904" height="453" alt="image" src="https://github.com/user-attachments/assets/720a346f-7780-408c-88ec-a28dac43511a" />
* Khi tôi thêm dấu ` đằng sau category=Corporate+gifts thì theo như thông tin trả về thông tin là
* `server 127.0.0.1:27017`. Cổng `27017` là cổng mặc định của MongoDB.
* Điều này xác nhận ứng dụng đang sử dụng một cơ sở dữ liệu NoSQL (cụ thể là MongoDB).
* Nguyên nhân gây lỗi là `SyntaxError: unterminated string literal` (Lỗi cú pháp: chuỗi ký tự chưa được kết thúc).
* <img width="878" height="396" alt="image" src="https://github.com/user-attachments/assets/95fc4563-068a-4a7e-b5e8-bd6126eaa5f3" />
* Khi gửi " lại không lỗi có thể suy luận được là ứng dụng backend đang xây dựng truy vấn MongoDB bằng cascg bao bọc tham số `category` trong dấu nháy "
* Khi gửi payload `Corporate gifts'` backend đang cố xây dựng `db.products.find({ "category": "Corporate gifts'" })` nó đã phá vỡ cú pháp và dẫn đến lỗi `SyntaxError: unterminated string literal`
* Thử payload này `' && '1' == '1`
* <img width="1057" height="353" alt="image" src="https://github.com/user-attachments/assets/e4fabaab-d88d-496a-bf21-64848b2c7dde" />
* Nó đã trả về 200 chứng tỏ backend đã hiểu và đã thực được query này.
* Để tối ưu query này nên đôi payload là `' || '1' == '1`
* Và thế là giải quyết được bài này.

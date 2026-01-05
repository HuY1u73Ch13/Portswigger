## Khai thác ánh xạ đường dẫn để đánh lừa bộ nhớ cache web 
* <img width="1316" height="612" alt="image" src="https://github.com/user-attachments/assets/a1ed817f-72fe-47dc-9bc6-903b854b9d60" />
* <img width="1297" height="569" alt="image" src="https://github.com/user-attachments/assets/059dc96d-ea24-4b52-af3f-82ca227edee7" />
* Gửi cả 2 request /my-account/abc.js và /my-account/abc nó vẫn trả về trang cá nhân của wiener chứng tỏ nó có cơ chế bỏ qua phần /abc.js mà thực tế web không có.
* <img width="1312" height="470" alt="image" src="https://github.com/user-attachments/assets/56ab4c80-9456-4a9d-98a4-b5890ae41aa6" />
* Ta có thể thấy được là được có dòng X-Cache: miss ở đây chứng tỏ là cache của request này chưa được lưu.
* Sau 1 khoảng thời gian tôi gửi lại request nhưng vẫn ko được nhưng sau 1 hồi tìm hiểu cái thì tôi biết được là `Cache-Control: max-age=30`
* Dòng này có nghĩa là cache chỉ được lưu trữ trong 30s nếu muốn hit cache thì phải gửi cả 2 gói liên tiếp dưới 30s.
* <img width="956" height="152" alt="image" src="https://github.com/user-attachments/assets/a3ae355c-399f-45c7-943e-8e6e0d551161" />
* Trong máy chủ khai khác gửi payload này cho nạn nhân và truy cập đến thư mục đó.
* <img width="944" height="202" alt="image" src="https://github.com/user-attachments/assets/1cb6dd69-a7f9-4928-800e-b1555c2f5ae2" />
* Và thế là ta đã có key api của carlos
* Giải thích về payload và payload bạn đặt trong máy đó là `<script>document.location="https://0ac5004003cea65a85f4196e00d70017.web-security-academy.net/my-account/wcd.js"</script>`
* `<script>...</script>` : Đây là thẻ HTML dùng để thực thi mã JavaScript ngay khi trình duyệt của nạn nhân tải trang web từ Exploit Server.
* `document.location="..."`: Đây là lệnh điều hướng. Nó bắt trình duyệt của người dùng phải rời khỏi trang hiện tại và truy cập ngay lập tức vào URL được chỉ định.
* URL mục tiêu (/my-account/wcd.js):
* `/my-account`: Là điểm cuối chứa thông tin nhạy cảm (API Key) của người dùng.
* `/wcd.js` : Đây là phần quan trọng nhất. Bạn đang "lừa" hệ thống bằng cách thêm một phần mở rộng file tĩnh giả vào sau đường dẫn thật.

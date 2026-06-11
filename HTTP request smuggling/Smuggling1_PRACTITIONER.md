## Tấn công giả mạo yêu cầu HTTP, xác nhận lỗ hổng CL.TE thông qua phản hồi khác biệt.
* Đầu tiên tôi cần giải thích lỗ hổng CL.TE là gì. CL tức là (Content-Length) Khai báo bằng 1 con số tĩnh, chỉ định chính xác tổng số byte (ký tự) của phần thân request.
* Ví dụ: Content-Length: 35 nghĩa là phần body dài chính xác 35 byte.
* TE (Transfer-Encoding: chunked): Khai báo rằng dữ liệu sẽ không được gửi cục bộ 1 lần mà được chia thành nhiều từng "khối" (chunk) nhỏ để gửi đi. Mỗi khối sẽ có độ dài riêng. Khối cuối cùng để báo hiệu "tôi đã gửi xong" luôn có kích thước bằng 0.
* ### Sự xung đột gây ra lỗi CL.TE
* Lỗ hổng xảy ra trong các hệ thống web có 2 lớp máy chủ xử lý nối tiếp nhau (ví dụ: Load Balancer đứng trước, Application Server đứng sau) và chúng không thống nhất với nhau về việc ưu tiên đọc header nào.
* ### Trong biến thể CL.TE
* **Máy chủ Front-end** (tiền sảnh) được cấu hình để tin tưởng vào tiêu đề Content-Length (CL)
* **Máy chủ Front-end** (hậu sảnh) được cấu hình để tin tưởng vào tiêu đề Transfer-Encoding (TE)
* Đối với lỗi này thì thì đầu tiên tôi lấy 1 req GET / HTTP/1.1
* <img width="1389" height="357" alt="image" src="https://github.com/user-attachments/assets/8683f85a-617e-45e7-ad0e-9ddfd628c2ad" />
* Tôi đổi method từ GET sang POST với mục đích là để gửi được dữ liệu lên server và phải đổi xuống HTTP/1.1 nữa là vì bản chất của giao thức này là nó giao tiếp bằng văn bản thuần túy. Nó phân tách các thành phần bằng cách đếm ký tự hoặc dựa vào các dòng trống.
* <img width="2025" height="765" alt="image" src="https://github.com/user-attachments/assets/cf6db434-66ba-4777-b3cc-4565e4a298b3" />
* Sau đó đưa payload này vào và gửi 2 lần lần đầu tiên nó trả về 200 và lần sau nó trả về 404
* <img width="1266" height="344" alt="image" src="https://github.com/user-attachments/assets/bca238d2-eff2-486e-b448-8e86198f4d8e" />
* Chứng tỏ nó đã dính.

## SSRF với bộ lọc đầu vào dựa trên danh sách đen 
* <img width="852" height="228" alt="image" src="https://github.com/user-attachments/assets/8570c67e-0297-4fdb-99b8-69929fb70686" />
* <img width="565" height="181" alt="image" src="https://github.com/user-attachments/assets/ab21a8e4-6dd8-41a3-9d49-0b5e5c472995" />
* Thử các ip `http://127.0.0.1/` `http://127.1/` `http://127.1/admin` đã thử encode các ip này nhưng đều bị chặn.
* Tôi thử encode chữ a thành `http%3A%2F%2F127.1%2F%2561dmin` và tôi đã làm đươc

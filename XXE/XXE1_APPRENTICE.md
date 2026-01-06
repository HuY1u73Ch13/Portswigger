## Exploiting XXE using external entities to retrieve files
* Ở lab này nó bảo tôi phải tấn công XXE qua chức năng kiểm tra hàng tồn kho
* <img width="554" height="534" alt="image" src="https://github.com/user-attachments/assets/666802a8-2c7e-449d-a417-272e6f13b272" />
* Vì thế tôi thử thêm paylaod ở đây.
* <img width="631" height="703" alt="image" src="https://github.com/user-attachments/assets/9108780c-940b-433d-817a-2db727df74ac" />
* Đã giải được lab này với payload như ảnh
* Giải thích về payload này là :
* `<!DOCTYPE ...>` là bước khai báo biến.
* Dòng này được gọi là DTD (Document Type Definition). Nó định nghĩa cấu trúc và các thực thể (Entities) mà tài liệu XML sẽ sử dụng.
* `<!ENTITY xxe ...>` đặt tên cho 1 biến tên là XXE.
* `SYSTEM` đây là từ khóa quan trọng. Nó ra lệnh cho trình phân tích XML là giá trị của biến này nằm ở SYSTEM và hãy vào SYSTEM để lấy nó ở đường dẫn `"file:/etc/passwd"`
* Và đoạn `&xxe;` được coi là bước sử dụng biến. Tức là tôi đang gọi đến productID là `xxe` chứ không phải là 3

## Brute-force một cookie ở lại đăng nhập 
* <img width="846" height="387" alt="image" src="https://github.com/user-attachments/assets/fac052ad-c77c-475b-99f8-c2276dc89b0f" />
* Bài này cho tôi tài khoản của tôi và tên tài khoản của carlos 
* <img width="897" height="422" alt="image" src="https://github.com/user-attachments/assets/b614c992-7406-4da1-a769-265c846fc893" />
* Lần này tôi thử đăng nhập nhiều lần và nó đã chặn 1 phút.
* <img width="977" height="590" alt="image" src="https://github.com/user-attachments/assets/0f4cbbac-e45e-41c0-99af-df5d1ad96b50" />
* Thử scan bằng cách thay đổi `X-Forwarded-For:` nhưng có vẻ cũng không được.
* <img width="1065" height="475" alt="image" src="https://github.com/user-attachments/assets/6c32286b-3f26-43af-ba1d-5f3c771525e5" />
* <img width="1383" height="589" alt="image" src="https://github.com/user-attachments/assets/02dd00aa-c04b-4a9d-8d75-5c3507b06477" />
* <img width="1068" height="474" alt="image" src="https://github.com/user-attachments/assets/28740874-71a5-419a-b4d6-7bac0da32c5f" />
* <img width="1071" height="588" alt="image" src="https://github.com/user-attachments/assets/1d23b658-297c-4d6f-8b7e-453cd3a25929" />
* Quan sát 4 hình ảnh trên ta thấy khi ta tích vào ô duy trì sự đăng nhập ta có thể thấy có sự xuất hiện thêm của trường `stay-logged-in` đây là trường duy trì sự đăng nhập mà không cần đăng nhập lại.
* <img width="1166" height="455" alt="image" src="https://github.com/user-attachments/assets/220291f8-085f-4438-975e-f3b5b68b492e" />
* Giải mã code này từ Base64 ta có thể xem được là trường `stay-logged-in` này được mã hóa từ tên tài khoản và mật khẩu như vậy mỗi tài khoản với mỗi mật khẩu sẽ có 1 chuỗi cố định.
* <img width="1149" height="355" alt="image" src="https://github.com/user-attachments/assets/3cd46570-25b2-472a-9689-3b8e8bd553c0" />


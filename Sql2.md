## Lỗ hổng SQL injection cho phép bỏ qua đăng nhập
* Dựa theo lỗ hổng này ta có thể biết được là hổng này là lỗ hổng sql nằm ở form input tài khoản mật khẩu đăng nhập
* <img width="1656" height="905" alt="image" src="https://github.com/user-attachments/assets/dc6724bf-93f2-4e3d-bf7b-52329183eee1" />
* Với tư duy như bài SQL1 tôi đã đăng nhập với tên người dùng là administrator và mật khẩu là ' OR 1=1--
* <img width="1629" height="941" alt="image" src="https://github.com/user-attachments/assets/794a9c3d-da99-4d26-bfe0-d2f170d8534c" />
* Và đã đăng nhập thành công.
* <img width="1619" height="778" alt="image" src="https://github.com/user-attachments/assets/c5c5bd36-fce8-4364-a7d1-8d1e2a845919" />
* Và nó đã trả về ở gói `1082` mã là `302` thì mã `302` này chứng tỏ là url này đã phản hồi và đã được chuyển hướng đến 1 url khác 
* Và ở gói `1083` nó đã được tạo 1 yêu cầu GET mới đến /my-account và trả về 200 chứng tỏ tôi đã đăng nhập thành công.

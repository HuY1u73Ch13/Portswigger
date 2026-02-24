## Thực hiện khai thác CSRF qua GraphQL 
* Ở bài trước mình bỏ qua giới hạn tốc độ (Rate Limit) gom nhiều query vào 1 request
* Còn ở lab này chúng ta phải vượt qua cơ chế samesite và content-type
* Attacker lừa nạn nhân nhấn vào link để gửi resquest nhạy cảm.
* Đầu tiên đăng nhập vào bằng tài khoản và mật khẩu của lab cho

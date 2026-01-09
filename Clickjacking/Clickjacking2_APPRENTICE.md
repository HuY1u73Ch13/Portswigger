## Clickjacking với dữ liệu đầu vào biểu mẫu được điền sẵn từ tham số URL 
* Ở lần trước là chúng ta chỉ cần nạn nhân nhấn vào nút "DELETE ACCOUNT" nhưng ở bài này mục tiêu là thay đổi email của họ.
* Trước tiên tôi thấy trang web này có cơ chế thay đổi email.
* Và lab này có nói là thay đổi email của người dùng bằng cách điền trước mẫu bằng tham số URL và lôi kéo người dùng vô tình nhấp vào nút "Cập nhật email".
* Thì sau khi tôi thử thay đổi email thì tôi thấy field email trên gói request
* <img width="268" height="43" alt="image" src="https://github.com/user-attachments/assets/ccd4445e-725b-433a-870f-5dc2ade17d71" />
* <img width="663" height="79" alt="image" src="https://github.com/user-attachments/assets/3ed1ca2e-7364-4fe1-a2d3-67363f6b0f31" />
* Sau khi tôi điền field lên url thì tôi thấy nó tự động điền vào ô nhập liệu của nạn nhân.
* <img width="943" height="282" alt="image" src="https://github.com/user-attachments/assets/bb71b9ac-6c39-41d9-921c-45ed9640bad4" />
* Sau khi gửi cái này thì tôi đã solve được

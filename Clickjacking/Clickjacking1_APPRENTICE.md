## Basic clickjacking with CSRF token protection
* Tại sao trong lab Clickjacking này lại nhắc đến từ khóa `CSRF`. Thì thông thường nút "Xóa Tài Khoản" được bảo về bằng CSRF token để ngăn chặn việc bị tấn công qua các request ngầm.
* Tuy nhiên Clickjacking vượt qua được CSRF vì chính người dùng thật là người trực tiếp nhấp chuột vào nút đó trên trình duyệt của họ.
* Ý tưởng để giải quyết lab này là nhúng frame vào tải khoản của người dùng (nạn nhân) vào 1 cái khung `<iframe>` làm trong suốt khung đó.
* Đặt tên là "Bấm vào để nhận thường" khi người dùng bấm vào thì người dùng đang xóa tài khoản.
* <img width="973" height="280" alt="image" src="https://github.com/user-attachments/assets/10012760-90b4-4b93-bf9c-8c6a19ccd1dd" />
* Điều chỉnh độ cao cho chuẩn và gửi thì tôi đã solve được.

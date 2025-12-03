## Liệt kê tên người dùng thông qua thời gian phản hồi 
* <img width="879" height="418" alt="image" src="https://github.com/user-attachments/assets/0a92a234-205c-46a5-841f-5497ee908a2e" />
* Bài này cũng cho tôi tên tài khoản và mật khảu tài khoản để đăng nhập và bảo tôi burpforce cái này.
* <img width="1043" height="223" alt="image" src="https://github.com/user-attachments/assets/1ec66b63-a70a-4bcf-9ca4-cf4626a0cbfc" />
* Tôi thử đăng nhập sai 3 lần và lần thứ 4 đã bị chặn
* <img width="1027" height="551" alt="image" src="https://github.com/user-attachments/assets/706f9583-afbf-4da2-8707-5c6ca0673fd2" />
* Tôi thử gửi 1 gói đúng tên đăng nhập nhưng sai mật khảu để xem nó có in ra các phản hổi khác nhau để khai thác từ đấy không nhưng khi tài khoản đúng nó vẫn hiển thị là `Invalid username or password.`
* Nhưng tôi đổi địa chỉ `X-Forwarded-For:` thì gói tin nó vẫn đi được ko bị giới hạn bỏi giới hạn lúc trước khi đăng nhập sai.
* <img width="1433" height="130" alt="image" src="https://github.com/user-attachments/assets/60db520f-0af5-4e9a-8585-f88e4057f3e3" />
* <img width="1439" height="141" alt="image" src="https://github.com/user-attachments/assets/ad9d81b9-da9f-4c77-bef7-d93f23b9e971" />
* <img width="1406" height="144" alt="image" src="https://github.com/user-attachments/assets/17264177-d004-40e1-bcd6-8cdc809e8a11" />
* Ta có thể thấy nó có thời gian phải hồi khác nhau thông qua các mật khẩu nên tôi nghĩ có thể tấn công brute-force bằng cách quan sát thời gian phản hồi.
* <img width="1091" height="457" alt="image" src="https://github.com/user-attachments/assets/30dbc320-45aa-4264-8d42-e93e2ff432db" />
* Sau khi tấn công thì tôi thấy payload này có thời gian phản hồi lâu nhất nên thôi thử dùng username này.
* <img width="1688" height="147" alt="image" src="https://github.com/user-attachments/assets/a175b270-a725-47ee-8597-4b1f486057aa" />
* Brute-force tiếp mật khẩu thì tôi được mật khẩu như này.

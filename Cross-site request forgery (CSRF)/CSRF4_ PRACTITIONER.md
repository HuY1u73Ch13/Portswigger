## CSRF trong đó token được liên kết với cookie không phiên 
* Trong bài này server chỉ kiểm tra xem "TokenA có đi kèm với Cookie A không", chứ không kiểm tra xem "Cookie A có thuộc về người dùng đang đăng nhập hay không?".
* **Bình thường** -> khi server khởi tạo dữ liệu, server sẽ cấp cho bạn 1 `session_id` ( để biết bạn là ai )
* Đồng thời, server tạo ra 1 `csrf_token` gắn chặt vào `session_id` đó vào trong cơ sở dữ liệu.
* Khi bạn đổi email: Server kiểm tra cái `csrf_token` này có đúng là của `session_id` này không.
* Nếu kẻ địch lấy token của họ thay cho bạn, server sẽ từ chối ngay vì không khớp chủ sở hữu.
* **Còn ở bài này** -> Server có sẵn 1 list csrfKey lưu trên trình duyệt và khi gói request được gửi đến thì server chỉ check xem là csrf(token được gửi đến) nó có trùng với list csrfKey đã được lưu sẵn trên trình duyệt hay không mà quên kiểm tra csrfkey đấy thuộc về người nào.
* <img width="536" height="525" alt="image" src="https://github.com/user-attachments/assets/d28344b0-63a3-4391-9fff-41d00ffaa255" />
* Dùng chức năng /change-email và rồi copy lại `csrdKey` và `csrf`
* Sau khi lấy được 2 cái đấy dùng chức năng tìm kiếm để tiêm csrfKey của tôi vào.
* <img width="1071" height="558" alt="image" src="https://github.com/user-attachments/assets/50dd906f-81fd-4dc7-aff1-fffec33b3b04" />

## Blind XXE với tương tác ngoài băng tần
* Thông thường với các lab **XXE** chúng ta thường muốn nó trả về nội dung file `/etc/passwd` nhưng ở đây bài lab này là dạng BlindXXE nên nó không trả ra kết quả màn hình để ta có thể đọc được.
* Bài này gợi ý phải dùng Burp Collaborator. Giải thích qua về chức năng Burp Collaborator này thì hãy coi đây là 1 trạm thu phát tín hiệu trung gian do burpsuite cung cấp.
* Chức năng này sẽ tạo ra 1 tên miền nằm trên internet và nó sẽ lắng nghe xem là có ai truy cập vào tên miền đó không nếu có nó sẽ báo ngay cho bạn.
* <img width="863" height="628" alt="image" src="https://github.com/user-attachments/assets/f013e0b0-7837-407b-9412-7e598649ad0f" />
* Dùng chức năng đấy để kiểm tra thử và tôi đã solve được chứng rỏ là cấu hình XML ở đây đang không an toàn. Server tự động gửi dữ liệu đến site bên ngoài chứng tỏ server có chức năng truy cập đến các site nhạy cảm bên ngoài cũng như bên trong 

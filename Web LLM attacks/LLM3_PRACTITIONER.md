## Indirect prompt injection
* <img width="1274" height="173" alt="image" src="https://github.com/user-attachments/assets/856d8a72-e2c4-4334-832b-3e2b4d2274d1" />
* Tôi thêm review mới và nó đã slove được bài này
* Tại sao lại dùng cái đống bùi nhùi `""" ] }` kia?
* Nếu hệ thống đang bọc review của bạn trong dấu ngoặc kép `"` hoặc định dạng JSON `}`, các ký tự này sẽ đóng cái ngoặc đó lại (đánh lừa hệ thống rằng review đã hết).
* Dòng `--- END OF REVIEW ---` và `SYSTEM INSTRUCTION:` giúp thiết lập lại vai trò, ép AI phải đổi từ trạng thái "đọc review" sang trạng thái "nghe lệnh admin".

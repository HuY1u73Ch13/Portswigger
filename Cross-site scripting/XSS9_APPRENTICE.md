## XSS được phản ánh thành một chuỗi JavaScript với dấu ngoặc nhọn được mã hóa HTML 
- Đề bài yêu cầu thực hiện một cuộc tấn công XSS thoát khỏi chuỗi JavaScript và gọi hàm alert.
- Nhập chuỗi ngẫu nhiên để tìm kiếm giá trị nhập vào được gán vào đâu : 
- <img width="1545" height="784" alt="image" src="https://github.com/user-attachments/assets/17ec78a1-0d31-42dc-8bcc-7f226d0ef1b6" />
- Ta thấy giá trị nhập vào được gán vào **searchTerm**
- Ta sử dụng : **'-alert(1)-'** để tấn công vào đoạn script
- <img width="1543" height="792" alt="image" src="https://github.com/user-attachments/assets/966a52d5-90ce-4f54-a32d-eeb44f535d10" />
- Trang web đã hiện thông báo :
- <img width="879" height="377" alt="image" src="https://github.com/user-attachments/assets/e33be863-cfe0-4ded-8797-5d632227495c" />
- Chuỗi '-alert(1)-' là một payload XSS dùng trong ngữ cảnh JavaScript string. Payload đóng chuỗi hiện tại bằng dấu ', chèn biểu thức JavaScript alert(1) thông qua toán tử -, sau đó mở lại chuỗi để tránh lỗi cú pháp, dẫn đến thực thi mã JavaScript mà ta mong muốn.

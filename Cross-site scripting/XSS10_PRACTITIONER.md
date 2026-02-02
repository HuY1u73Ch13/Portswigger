## Stored DOM XSS
- Comment bất kì lấy gói POST để kiểm tra :
- <img width="1543" height="604" alt="image" src="https://github.com/user-attachments/assets/eb1e086d-4d79-4635-baf2-01e9a5cee4fc" />
- Ta thử tấn công vào body bằng lệnh : <img width="202" height="33" alt="image" src="https://github.com/user-attachments/assets/253f48aa-9978-4efe-bb78-4fe0eebccae0" />
- Trang web hiện :
- <img width="278" height="91" alt="image" src="https://github.com/user-attachments/assets/78cadefb-f005-41cc-a718-b8bde1b3f4ef" />
- Ta có thể thấy rằng trang web đã được lọc bằng hàm **replace()**. Ta sử dụng : <img width="261" height="28" alt="image" src="https://github.com/user-attachments/assets/c1aaa41c-7a56-4142-b2db-40f90850537f" />
- Trang web hiện :
<img width="863" height="473" alt="image" src="https://github.com/user-attachments/assets/9a8fe918-5c58-4ca1-a5ba-114d39ee213f" />
- Trang web đã sử dụng hàm **replace() của** JavaScript để mã hóa dấu ngoặc nhọn nhưng khi thêm một cặp dấu ngoặc nhọn vào đầu phần bình luận các dấu ngoặc nhọn này sẽ được mã hóa, còn dấu ngoặc nhọn tiếp theo sẽ không bị ảnh hưởng, cho phép ta vượt qua bộ lọc và chèn HTML một cách hiệu quả.

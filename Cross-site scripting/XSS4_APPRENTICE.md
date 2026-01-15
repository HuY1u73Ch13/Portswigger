## DOM XSS in `innerHTML` sink using source `location.search`
* **Đề bài :**
* <img width="908" height="156" alt="image" src="https://github.com/user-attachments/assets/1930da9c-6b34-43f4-930b-e6c4e938576e" />
* Truy cập và kiểm tra phần tìm kiếm của trang web:
* <img width="554" height="600" alt="image" src="https://github.com/user-attachments/assets/4cb46528-bf5c-4c0b-9e02-6177a3c5f442" />
* Ta có thể thấy là dữ liệu người dùng nhập vào được xử lý ở hàm **doSearchQuery(query)** ta thử tấn công XSS bằng lệnh <img width="227" height="26" alt="image" src="https://github.com/user-attachments/assets/702c6484-39e8-4d48-b5c8-62adffc4a110" />
* <img width="1916" height="951" alt="image" src="https://github.com/user-attachments/assets/29a24e50-94f7-47d6-8e57-f907189042b1" />

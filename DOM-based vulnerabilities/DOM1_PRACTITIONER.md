## DOM XSS sử dụng tin nhắn web 
* <img width="724" height="333" alt="image" src="https://github.com/user-attachments/assets/0fb341be-5fc3-4b59-8c44-91e9880817ab" />
* Bấm `ctrl+u` ta thấy được đoạn code xử lý sự kiện `message` trông như trên ảnh
* Code này cực kì nguy hiểm vì nó nhận dữ liệu thô (e.data) từ bất kì ai gửi đến và nhét thẳng vào HTML của trang web mà không hề lọc rửa.
* <img width="1189" height="388" alt="image" src="https://github.com/user-attachments/assets/f25b81ca-8f2d-404c-aebe-ef46b52593c0" />
* Gửi payload này vào trang web ta có thể thấy là ta đã solve được bài này.
* Đoạn payload này được thiết kế để thực hiện tấn công **DOM XSS** thông qua cơ chế `postMessage`

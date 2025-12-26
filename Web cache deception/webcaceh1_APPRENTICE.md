## Khai thác ánh xạ đường dẫn để đánh lừa bộ nhớ cache web 
* <img width="1316" height="612" alt="image" src="https://github.com/user-attachments/assets/a1ed817f-72fe-47dc-9bc6-903b854b9d60" />
* <img width="1297" height="569" alt="image" src="https://github.com/user-attachments/assets/059dc96d-ea24-4b52-af3f-82ca227edee7" />
* Gửi cả 2 request /my-account/abc.js và /my-account/abc nó vẫn trả về trang cá nhân của wiener chứng tỏ nó có cơ chế bỏ qua phần /abc.js mà thực tế web không có.
* <img width="1312" height="470" alt="image" src="https://github.com/user-attachments/assets/56ab4c80-9456-4a9d-98a4-b5890ae41aa6" />
* Ta có thể thấy được là được có dòng X-Cache: miss ở đây chứng tỏ là cache của request này chưa được lưu.
* Sau 1 khoảng thời gian tôi gửi lại request nhưng vẫn ko được nhưng sau 1 hồi tìm hiểu cái thì tôi biết được là `Cache-Control: max-age=30`
* Dòng này có nghĩa là cache chỉ được lưu trữ trong 30s nếu muốn hit cache thì phải gửi cả 2 gói liên tiếp dưới 30s.

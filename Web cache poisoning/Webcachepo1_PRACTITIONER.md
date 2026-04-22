## Tấn công bộ nhớ cache web bằng tiêu đề không có khóa
* <img width="1379" height="467" alt="image" src="https://github.com/user-attachments/assets/a9dae3f1-887f-4bf3-832c-25297fc0d242" />
* Đầu tiên tôi dùng Param Miner để Guess Header và tôi xem log thì nó đoán được là có có param : x-forwarded-host
* Sau khi có param đấy thì tôi thử cho nó vào request để xem nó có trả về phản hồi gì không thì nó có trả như bên dưới
* <img width="990" height="1017" alt="image" src="https://github.com/user-attachments/assets/3e5c2602-f6b8-4412-a75e-201e6d249c98" />
* Tôi thử điền anh.com vào để xem nó có trả về anh.com trong response hay không thì tôi đã được kết quả như hình
* <img width="996" height="1355" alt="image" src="https://github.com/user-attachments/assets/d3d92a4f-d239-48b7-bb5d-c7a81ec2b7c9" />
* <img width="991" height="1298" alt="image" src="https://github.com/user-attachments/assets/00409408-d59a-4bf8-981f-905f94196ae6" />
* Sau đó tôi thêm 1 cái `/?cd=abs` path chưa bao giờ có mục đích là để nó lưu cache mới của trang này
* <img width="1015" height="1206" alt="image" src="https://github.com/user-attachments/assets/536095f0-cc83-4a42-acf1-83b47ca15104" />
* <img width="1015" height="1206" alt="image" src="https://github.com/user-attachments/assets/50fcf22d-bfea-4209-b1b9-827cfecccb9b" />
* Sau đó gửi đi đầu tiên là miss sau đó là hit và nó đã dính

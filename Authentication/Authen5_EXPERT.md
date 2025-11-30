## Bảo vệ brute-force bị hỏng, nhiều thông tin đăng nhập cho mỗi yêu cầu 
* <img width="1616" height="647" alt="image" src="https://github.com/user-attachments/assets/20bebb07-c298-4313-bb38-b8c9e91abb91" />
* Lần này đã được cho username là `carlos` nhưng có vẻ nó đã bị giới hạn sau 2 lần đăng nhập.
* <img width="529" height="325" alt="image" src="https://github.com/user-attachments/assets/5980dbf8-db3b-4a78-b6ca-0adf4ad0e024" />
* Sau khi ngồi nghiên cứu và quan sát lại thì tôi quan sát thấy username và passwd được gửi thông qua gói json
* Thì gói JSON là 1 gói văn bản rất nhẹ, dễ đọc và dễ hiểu cho cả con người và máy móc
* Nó được sử dụng để biểu diễn cấu trúc dữ liệu (cặp khóa-giá trị, mảng, vv ..)
* <img width="1093" height="476" alt="image" src="https://github.com/user-attachments/assets/cb4625d3-5406-4ab2-bd7b-b1c47c0cb4f5" />
* Với suy nghĩ đó tôi đã add list mật khẩu vào trong mảng của `password` và nó trả về 302 chứng tỏ nó đã được chuyển hướng đến trang khác.
* <img width="1254" height="731" alt="image" src="https://github.com/user-attachments/assets/1001c358-ed5e-4d97-abd7-b37c4154a118" />
* Copy resq với tùy chọn `Show response in browser` và paste nó lên trình duyệt và tôi đã giải được nó



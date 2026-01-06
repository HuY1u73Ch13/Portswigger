## Exploiting XXE to perform SSRF attacks
* Ở lab này là bước nâng cao hơn so với việc đọc file `/etc/passwd`. Thay vì đjojc file trên ổ cứng tôi sẽ phải dùng lỗ hổng XXE để ép server thực hiện 1 request đến 1 địa chỉ nội bộ mà bình thường không thể truy cập từ bên ngoài 
* Đây chính là sự kết hợp của **XXE** VÀ **SSRF (Server-Side Request Forgery)**
* <img width="536" height="282" alt="image" src="https://github.com/user-attachments/assets/0eb5c61a-5f68-4d93-8dea-f0b56312be8f" />
* Theo như yêu cầu của đề bài thì tôi cũng chưa hiểu từ khóa **EC2** là sao. Thì trong môi trường điện toán đám mây của `AWS (Amazon Web Services)` các máy ảo được gọi là `EC2`
* Luôn có 1 dịch vụ đặc biệt chạy ở 1 địa chỉ IP tĩnh ko đổi là `169.254.169.254`
* Mục đích là để các máy chủ lấy các thông tin về chính nó như (ID máy chủ, địa chỉ các máy nội bộ, cấu hình mạng, ...)
* Và địa chỉ này không thể truy cập từ tên ngoài và lưu nhiều dữ liệu nhạy cảm.
* <img width="704" height="603" alt="image" src="https://github.com/user-attachments/assets/6f7381e5-b668-4048-838f-744742a74b6a" />
* Nó trả ra như này và thấy được là nó trả về các thư mục con có sẵn `http://169.254.169.254/latest/` vì thế tôi tiếp tục
* <img width="709" height="616" alt="image" src="https://github.com/user-attachments/assets/51e4f269-588c-4979-89a6-3ef777b087be" />
* Và tôi dã solve được lab này.

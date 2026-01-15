## Lưu trữ XSS vào ngữ cảnh HTML mà không có gì được mã hóa 
* <img width="789" height="128" alt="image" src="https://github.com/user-attachments/assets/c01feb5f-477f-4ef0-b44f-e5772425e398" />
* Truy cập vào phần **Comment** trong trang web và thử câu lệnh chèn mã JavaScript : **<script>alert(1)</script>**
* <img width="683" height="328" alt="image" src="https://github.com/user-attachments/assets/1219f2a1-82a4-42e8-b0b3-88b7938dc081" />
* Sau khi up comment lên thì trang web hiện thông báo (1) và đã hoàn thành bài lab
* <img width="452" height="168" alt="image" src="https://github.com/user-attachments/assets/9f34530e-92f0-4a99-8c80-3d5a546b3970" />
* Lí do : Server đưa dữ liệu do người dùng kiểm soát vào HTML mà không mã hóa, khiến trình duyệt hiểu đó là mã JavaScript hợp lệ và thực thi.

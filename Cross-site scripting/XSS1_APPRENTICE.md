## Phản ánh XSS vào ngữ cảnh HTML mà không có gì được mã hóa 
* <img width="816" height="103" alt="image" src="https://github.com/user-attachments/assets/1133492f-ed3c-44a4-9dc5-6056fcac88af" />
* Đề bài yêu cầu tấn công bằng **alert** trực tiếp vào HTML
* Ta sẽ khai thác chức năng search ở trong trang web. Điền **<script>alert(1)</script>** để mã JavaScript thực thi thẳng trên HTML
* <img width="1878" height="769" alt="image" src="https://github.com/user-attachments/assets/91d4626e-d379-47dd-b88d-7051cfbd0efd" />
* Ta có thể thấy web hiện thông báo **1**
* <img width="440" height="164" alt="image" src="https://github.com/user-attachments/assets/5193fac0-f9ef-431c-9ad7-827633992bdc" />
* Lí do vì ứng dụng xử lý dữ liệu đầu vào (input) không an toàn, dẫn đến trình duyệt hiểu dữ liệu đó là mã lệnh thay vì văn bản

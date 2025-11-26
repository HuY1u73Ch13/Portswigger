## Tiêm SQL với bỏ qua bộ lọc thông qua mã hóa XML
* XML (eXtensible Markup Language) là một ngôn ngữ đánh dấu được thiết kế để mô tả, vận chuyển và lưu trữ dữ liệu một cách có cấu trúc, dễ đọc và dễ hiểu cho cả người và máy tính.
* Khác với HTML (có thẻ cố định), XML cho phép bạn tự tạo các thẻ (tags) của riêng mình để mô tả chính xác dữ liệu (ví dụ: <ten_khach_hang>, <dia_chi>).
* <img width="1269" height="447" alt="image" src="https://github.com/user-attachments/assets/157c0e9d-078c-4936-b3a1-74d1170f77ae" />
* Ở thử thách này tấn công qua form login như lúc này thì tôi đã bị phát hiện.
* <img width="1486" height="537" alt="image" src="https://github.com/user-attachments/assets/05e61a3a-fdff-4b90-9f4c-d5bb23989ca0" />
* Nhìn ở gói tin này thì ta có thể biết được là khi 1 trang web kiểm tra tồn kho sử dụng XML qua phương thức POST thì nó kiểm tra hàng tồn của sản phẩm có id là 6 ở của hàng có id là 1.
* Và nó trả về là 343 sản phẩm trong kho này
* <img width="1541" height="555" alt="image" src="https://github.com/user-attachments/assets/a58b13d0-3e5f-4365-a6be-31f4480042f6" />
* Tôi thử câu lệnh SQL injection ở productID và có vẻ như nó bị filter ở đây rồi.
* Mục tiêu của cái này là lấy ra cả cột `username` và `password` ra cùng 1 lúc trong 1 kết quả duy nhất
* Thì chúng ta phải nên sử dụng phương pháp nối chuỗi 

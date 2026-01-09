## Khai thác XXE thông qua tải lên tệp hình ảnh 
* Tiếp theo là bài khai thác XXE thông qua tải tệp lên hình ảnh. Đây là 1 kỹ thuật rất phổ biến và thú vị vì nó lợi dụng định dạng hình ảnh SVG (Scalable Vector Graphics).
* Bản chất của file SVG thực chất là 1 tài liệu XML, vì vậy nếu server sử dụng các thư viện như APACHE BATIK để xử lý hình ảnh này mà không cấu hình bảo mật nó sẽ dính lỗi XXE.
* <img width="919" height="551" alt="image" src="https://github.com/user-attachments/assets/27a24b71-50d3-423d-bee0-63e8936ca52f" />
* Tôi đã up thành công file và payload bằng file `exploit.svg` bản chất file SVG là ảnh nhưng là code. SVG thực chất là 1 tài liệu XML. Nó dùng các thẻ `<circle>`, `<rect>`, `<text>` để vẽ hình.
* Vì nó là thẻ XML, nên có thể chứa cách thành phần đặc trưng của XML, bao gồm cả DTD và Entities.
* Khi tải avatar ;ên máy chủ ko chỉ lưu file đó lại. Để hiển thị hoặc kiểm tra tính hợp lệ, máy sử dụng một thư viện(trong bài này là `Apache Batik`) để "đọc" và xử lý file SVG đó.
* Quá trình này gọi là `Parsing`
* Nếu thư viện này không được cấu hình để chặn các thực thể bên ngoài nó sẽ thực thi các lệnh XML mà bạn lén chèn vào trong file ảnh.
* Phân tích payload này thì.
* Dòng `!ENTITY xxe ...`. Bạn ra lệnh cho trình phân tích XML là tạo ra biến &xxe và giá trị của nó là nội dung file `/etc/hostname` trên máy chủ.
* Dòng `<text ...>&xxe;</text>`. Đây là thẻ vẽ chữ của SVG. Thay vì gõ chữ "Hello" bạn điền `&xxe;`.
* Kết quả sẽ thay thế bằng nội dung file hostname. Và khi nó vẽ ảnh ra cho bạn xem thì nó vô tình vẽ luôn tên máy chủ đó.
* Còn dòng `xmlns=http://www.w3.org/2000/svg` giống như một lời khai báo: "Tôi đang viết bằng ngôn ngữ SVG chuẩn năm nào".

## SSRF cơ bản chống lại máy chủ cục bộ.
* <img width="1060" height="441" alt="image" src="https://github.com/user-attachments/assets/42ca1a86-d148-4d35-b66d-11eeec528b1a" />
* Nhìn vào gói request này ta thấy được là có trường stockApi và nó đang được mã hóa (encode) từ URL.
* Sau khi giải mã ta được `http://stock.weliketoshop.net:8080/product/stock/check?productId=1&storeId=1`
* Cách thức hoạt động của cái này là khi trình duyệt bạn gửi yêu cầu đến `Web Server` kèm theo tham số `stockApi`
* Web server nhận được tham số này, sau đó nó sẽ tự đóng vai trò là 1 "khách hàng" để thực hiện 1 yêu cầu http khác tới địa chỉ nằm trong `stockApi` (địa chỉ backend).
* Sau khi lấy được dữ liệu tồn kho tử backend , web server sẽ trả lại kết quả cho trình duyệt của bạn.
* <img width="1068" height="562" alt="image" src="https://github.com/user-attachments/assets/c59335ce-5ef0-4216-aed6-49eabec1c709" />
* Sau khi điều chỉnh tham số `stockApi=http://localhost/admin` và gửi đến webserver thì nó trả ra `/admin/delete?username=carlos` như này.
* Lấy địa chỉ này và thay vào địa chỉ `stockApi`.
* <img width="956" height="165" alt="image" src="https://github.com/user-attachments/assets/7a02a040-ec55-4e25-b928-1f6f4ed49d53" />
* Và đã giải được
* Trong trường hợp này mục tiêu chính là lỗ hổng `SSRF (Server-Side Request Forgery)`
* Vấn đề: Nếu không kiểm tra kỹ, kẻ tấn công có thể thay đổi giá trị của `stockApi` thành 1 địa chỉ khác.
* Ví dụ: thay vì trỏ đến dịch vụ kho hàng, kè tấn công có thể đổi thành `http://localhost/admin` hoặc `http://192.168.0.1` để truy cập vào các dịch vụ nội bộ mà thông thường bên ngoài internet không thể tiếp cận được.
* 

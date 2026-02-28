## CSRF trong đó xác thực token phụ thuộc vào phương thức yêu cầu 
* Ở lab trước (No defenses), hệ thống hoàn toàn không có lớp bảo vệ nào. Nhưng ở các bài tiêp theo, sẽ có vài cơ chế bảo mật mà lập trình viên hay dùng, và nhiệm vụ của chúng ta là tìm cách **BYBASS** qua chúng.
* Đầu tiên tôi thử đăng nhập bằng tài khoản và mật khẩu wiener:peter.
* Khi vào tôi thấy trang web có ô có chức năng đổi email. Tôi bật intercept lên và thử thay đổi email xem như nào.
* Dùng chức năng **Change request method**.
* Thì lúc này gói request đã tự động nhảy từ phương thức POST sang phương thức GET, và tham số trên URL cũng đã nhảy thành như này.
* `/my-account/change-email?email=test%40me.com&csrf=JBD28eOqH4jyIfNdobsHsoVIx2va39Me`
* Tôi thử xóa bỏ phần `csrf=JBD28eOqH4jyIfNdobsHsoVIx2va39Me` là gửi đi.
* Và thế là tôi đã đổi được email và slove thành công bài này.
  

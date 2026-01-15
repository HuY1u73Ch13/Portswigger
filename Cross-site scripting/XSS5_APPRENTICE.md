## DOM XSS trong neo jQuery `href` Thuộc tính chìm bằng cách sử dụng `location.search` nguồn 
* Truy cập và thử sửa tham số truy vấn ngẫu nhiên:
* <img width="696" height="548" alt="image" src="https://github.com/user-attachments/assets/0e2a7f8d-ac53-46d7-a925-e1e7b6e6fe67" />
* Kiểm tra web để tìm nội dung ngẫu nhiên mới truyền vào :
* <img width="553" height="606" alt="image" src="https://github.com/user-attachments/assets/0414e6fe-90eb-4a5f-8b32-785416aa86cb" />
* Ta thử sửa tham số truy vấn thành **javascript:alert(document.cookie)** để chèn vào **backLink**
* <img width="557" height="631" alt="image" src="https://github.com/user-attachments/assets/7dbbbe86-4282-49bd-8cdd-9bc72f746113" />
* <img width="1914" height="954" alt="image" src="https://github.com/user-attachments/assets/44d479c3-6b47-4f85-b574-7ff2a0f1882d" />
* Ta đã hoàn thành bài lab nhờ cách chèn tham số độc hại vào **backLink**

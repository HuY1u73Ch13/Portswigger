## Lỗ hổng DOM XSS trong bộ chọn jQuery sử dụng sự kiện hashchange
- Đề bài yêu cầu tìm kiếm lỗ hổng ở hàm tìm kiếm của trang web:
- <img width="865" height="96" alt="image" src="https://github.com/user-attachments/assets/11049ff4-e78a-41f0-9e2b-e7dee5ffc08e" />
- Hàm trên cho phép ta di chuyển đến phần mà chúng ta cần tìm ở trên trang web
- Ta nhập <img width="419" height="30" alt="image" src="https://github.com/user-attachments/assets/f157628a-40a7-4ebe-af88-e006c54d4f07" /> vào hàm tìm kiếm
- <img width="1912" height="994" alt="image" src="https://github.com/user-attachments/assets/89cfc59a-4d83-4455-bf26-a66a5938d11c" />
- Trang web đã hiện lên 1 bức ảnh điều này cho thấy trang web không chặn **<script>** vậy nên ta dễ dàng bypass qua
- Payload lợi dụng việc ứng dụng sử dụng dữ liệu từ location.hash mà không xử lí, cho phép attacker chèn event handler HTML (onload, onerror)
  dẫn đến DOM-based Cross-Site Scripting, cho phép thực thi JavaScript tùy ý trong trình duyệt nạn nhân.

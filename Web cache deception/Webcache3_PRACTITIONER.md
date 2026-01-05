## Khai thác chuẩn hóa máy chủ gốc để đánh lừa bộ nhớ cache web 
* Thử chèn payload vào `/my-account§§abc` và gửi từ intruder thì tôi được như hình ảnh bên dưới
* <img width="1388" height="478" alt="image" src="https://github.com/user-attachments/assets/2fdc6481-6934-4d51-adcf-0f01444cb21b" />
* <img width="1348" height="571" alt="image" src="https://github.com/user-attachments/assets/ab867d37-2e7d-456f-b142-3f7f7763f5f9" />
* Thử không encode và encode thì tôi đã được response như trên.
* Lỗ hổng ở đây không nằm ở việc thêm đuôi file mà nằm ở cách mà hệ thống xử lý các ký tự đặc biệt như dấu chấm .. và mã hóa `%2f` (ký tự / được URL encode).
* <img width="782" height="323" alt="image" src="https://github.com/user-attachments/assets/f135705d-baf0-4c13-844c-a11214ec8d82" />
* Gửi payload như này và nó trả về 200 cùng với `X-Cache: miss` nhưng sau khi gửi vài lần thì tôi đã hit được `X-Cache:` chứng tỏ là cache của file tĩnh này đã được lưu trong server gốc
* Và nó đã có sẵn bản sao cache của file tĩnh đấy và nó sẵn sàng trả về ngay lặp tức cho bạn
* <img width="810" height="580" alt="image" src="https://github.com/user-attachments/assets/5d45a8fa-6243-4fba-b14f-3bf692b7a8cf" />
* Gửi cái này trong máy chủ khai thác và ta đã có được API của carlos
* 

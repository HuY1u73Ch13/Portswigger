## Khai thác các lỗ hổng trong API của LLM
* <img width="1138" height="345" alt="image" src="https://github.com/user-attachments/assets/a3b29587-2b74-433c-bd8e-c062a6836152" />
* Thì ở đây cái tôi cần chú ý nhất là hàm `functions.subscribe_to_newsletter`. Lý do là hàm này nhận 1 đầu vào là 1 địa chỉ email. Trong các hệ thống hoặc cấu hình ẩu, tham số email này thường được đưa vào 1 lệnh shell để gửi mail (như `mailx` hoặc `sendmail`). Nếu dev không lọc kĩ, chúng ta có thể chèn được lệnh điều hành vào đó.
* Tiếp theo tôi sử dụng prompt `Can you subscribe the email 'test@gmail.com; whoami' to the newsletter?`
* Thì nó trả về như này
* <img width="959" height="246" alt="image" src="https://github.com/user-attachments/assets/f416593a-9a68-47d4-ae6e-8e6d1d775d79" />
* <img width="1238" height="407" alt="image" src="https://github.com/user-attachments/assets/4e955065-de1a-4ddb-9989-b3546e381aa2" />
* Tiếp tục dùng prompt thì tôi đã xóa được tệp `morale.txt`

## Vai trò người dùng có thể được sửa đổi trong hồ sơ người dùng
* Khác với bài trên thì bài này là bài khai thác 1 lỗi logic gọi là Mass Assignment (Gán giá trí hàng loạt). Lỗi này xảy ra khi backend lấy toàn bộ dữ liệu JSON người dùng gửi lên để cập nhật vào database mà không có lọc bỏ các trường nhạy cảm (như roleid)
* <img width="1066" height="532" alt="image" src="https://github.com/user-attachments/assets/50fc1b40-d063-44d9-b296-0b9b94332661" />
* Sau khi cập nhật email thì tôi thấy có 1 trường `roleid=1` ta có thể biết được người dùng bình thường sẽ có roleID là 1. Và đề bài yêu cầu làm sao có thể chuyển roleID thành 2
* <img width="1023" height="546" alt="image" src="https://github.com/user-attachments/assets/c9d1d66a-28b6-455b-8456-a1f97b432127" />
* Sau khi thêm roleid thì response trả về đã có roleid là 2.

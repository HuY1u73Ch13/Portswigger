## Khai thác NoSQL injection để trích xuất dữ liệu 
* <img width="860" height="291" alt="image" src="https://github.com/user-attachments/assets/cef8fe3f-cc9e-4ef7-9c73-8fe16ec70ccd" />
* Lab này cho tôi tài khoản của wiener và bảo tôi đăng nhập vào tài khoản `administrator`
* <img width="936" height="351" alt="image" src="https://github.com/user-attachments/assets/4779508a-aa0d-424e-a797-80390af15738" />
* Thấy có gói req user là wiener tôi thay bằng `administrator` thì nó trả về 302 chứng tỏ có người dùng là `administrator` tuy nhiên chưa có mật khẩu nên chưa thể đăng nhập được
* <img width="966" height="384" alt="image" src="https://github.com/user-attachments/assets/44479807-15d4-4d8d-8e2c-1cabea9d5791" />
* Thử thêm câu lệnh truy vấn này thì tôi thấy truy vấn được thì có thể là đang có lỗi sql ở đây.
* Thử đổi `username` thành `password` để xem sao
* <img width="959" height="379" alt="image" src="https://github.com/user-attachments/assets/f4121e47-7a2d-4e4f-99f5-d1c92a40c6c2" />
* Nó cũng trả về 200 nên là tôi biết được kí tự đầu tiên của password là khác 'a'
* <img width="779" height="823" alt="image" src="https://github.com/user-attachments/assets/4d6b7d0b-19c4-4d56-ad19-10d224166125" />
* Sau khi bruteforce mật khẩu thì tôi biết được là mật khẩu này có độ dài là 8 và tiếp tục burpforce từng chữ cái trong mật khẩu.
* <img width="877" height="854" alt="image" src="https://github.com/user-attachments/assets/de821ae4-500e-4714-85fc-67e305a397b8" />
* Sau khi bruteforce mật khẩu tôi dược mật khẩu là 'nnfkejay`

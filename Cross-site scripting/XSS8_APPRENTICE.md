# Lưu trữ XSS vào neo hrefcó dấu ngoặc kép được mã hóa HTML 
* <img width="860" height="70" alt="image" src="https://github.com/user-attachments/assets/86337373-283b-459e-a411-e45730bd3023" />
- Đề bài yêu cầu gọi hàm alert khi người dùng nhấp vào tên tác giả bình luận
- Gửi 1 comment bất kì lên để kiểm tra
- <img width="1542" height="785" alt="image" src="https://github.com/user-attachments/assets/6b553df0-23a7-4e2d-8f6e-59dd88bf6f79" />
- Nội dung ta nhập ở Website được gán vào href ta sử dụng : **javascript:alert(1)**
- <img width="1323" height="525" alt="image" src="https://github.com/user-attachments/assets/7fd8afb3-53d5-4b0d-b309-6c615cb3f923" />
- Ta ấn vào tên người dùng thì lệnh javascript:alert(1) sẽ được thực thi và hiện lên thông báo :
- <img width="953" height="1026" alt="image" src="https://github.com/user-attachments/assets/08a100aa-5bdc-4bf9-b928-03ba33c41a07" />
- Khi giá trị javascript:alert(1) được gắn vào thuộc tính href, trình duyệt sẽ thực thi JavaScript khi người dùng click vào liên kết.
- Nếu ứng dụng cho phép người dùng kiểm soát giá trị href mà không validate hoặc whitelist scheme, điều này dẫn đến lỗ hổng XSS thông qua JavaScript URI.

## Khai thác lỗ hổng clickjacking để kích hoạt XSS dựa trên DOM 
* Ở lab trước chúng ta thực hiện 1 hành động có sẵn là đổi email. Chỉ là Clickjacking thuần túy nhưng ở lab này là Clickjacking + XSS. Dùng Clickjacking để kích hoạt ngòi nổ cho XSS.
* Thì đầu tiên tôi cần tìm điểm yếu của XSS nó nằm ở đâu.
* `https://0ac9003a0360fa4d832fe27300c5008a.web-security-academy.net/feedback?name=%3Cimg%20src=1%20onerror=print()%3E&email=hacker@evil.com&subject=test&message=test` 
* Dùng payload này gửi lên url và tôi thấy trang web nhảy ra trang in chứng tỏ có lỗ hổng XSS ở đây.
* 

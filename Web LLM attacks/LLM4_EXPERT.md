## Khai thác lỗ hổng xử lý đầu ra không an toàn trong LLMs
* Ở bài trước, chúng ta đã nhắm vào việc LLM tự động gọi các API. Nhưng nếu hệ thống bảo mật tốt, họ không cấp cho LLM quyền gọi API nhạy cảm thì sao?
* Lúc này ta nhắm vào cách trang web hiển thị câu hỏi của AI
* Nếu trang web tin tưởng những gì AI nói và in thẳng ra màn hình chat mà không thèm lọc các thẻ HTML/JAVAScript (Sanitization), lỗ hổng XSS sẽ xảy ra. AI lúc này sẽ trở thành một kẻ vận chuyển mã độc.
* Đầu tiên tôi vào trang /my-account/ và tôi intercept và bấm nút delete acount 
* <img width="1872" height="839" alt="image" src="https://github.com/user-attachments/assets/b96b4f17-5387-406a-b737-a0e888be3248" />
* Nhìn vào request này ta thấy được là nó có 1 tham số cực kì quan trọng là `csrf=GtlaMz...`
* Vấn đề ở đây là chúng ta ko thể dùng token của `tôi(hoang)` để xóa tài khoản của thằng `carlos`. Nếu mã JS độc hại của tôi chỉ gửi bừa 1 lệnh POST, server sẽ báo lỗi CSRF. Vì vậy chúng ta cần tạo ra đoạn mã XSS (JavaScript) của chúng ta cần chạy 2 bước (Two-step exploit).
* Bước 1: Trình duyệt của nạn nhân sẽ tự động tải trang `GET /my-account` (trang cá nhân của Carlos), âm thầm trích xuất lấy cái mã CSRF Token của Carlos.
* Bước 2: Lấy token đó nhét vào một request `POST /my-account/delete` rồi gửi đi.
* 

## DOM-based Vulnerabilities

### Định nghĩa
DOM-based vulnerabilities (phổ biến nhất là DOM XSS) là lỗ hổng bảo mật xảy ra hoàn toàn ở phía client (trình duyệt), khi mã JavaScript của ứng dụng lấy dữ liệu từ một nguồn không an toàn (Source) và đưa nó vào một hàm xử lý nguy hiểm (Sink) mà không qua kiểm tra hoặc mã hóa. Khác với các lỗ hổng XSS truyền thống, payload tấn công có thể không bao giờ được gửi đến server, khiến các bộ lọc phía server (WAF) không thể phát hiện được.

### Những chỗ thường dính
* Source (Nguồn dữ liệu độc hại):
  * Các tham số trên URL: location.search, location.hash, document.URL.
  * Dữ liệu từ trang trước: document.referrer.
  * Giao tiếp giữa các cửa sổ/iframe: window.name, sự kiện postMessage (như bài lab bạn vừa làm).
* Sink (Điểm thực thi mã độc):
  * Ghi trực tiếp vào HTML: element.innerHTML, document.write().
  * Thực thi mã script: eval(), setTimeout(), setInterval().
  * Điều hướng trang: location.href, window.open().
* Môi trường:
  * Các ứng dụng Single Page Application (SPA) dùng React, Vue, Angular đời cũ hoặc dùng v-html / dangerouslySetInnerHTML sai cách.
  * Các thư viện jQuery cũ (ví dụ bộ chọn $('#...') với đầu vào từ URL).

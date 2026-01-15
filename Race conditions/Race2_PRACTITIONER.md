## Vượt qua giới hạn tốc độ thông qua các điều kiện cuộc đua 
* Ở bài lab trước ta tận dụng lỗ hổng áp dụng mã giảm giá server kiểm tra "Mã đã dùng chưa" Chậm cập nhật trạng thái "đã dùng". Ta chèn nhiều req để dùng tiếp.
* Còn ở bài lab này ta tận dụng lỗ hổng Server kiểm tra "Đã sai quá 3 lần chưa?" -> chậm cập nhật bộ đếm "số lần sai" -> Ta chèn nhiều lần trước khi bị khóa IP. Gửi nhiều request khác nhau (mỗi request là 1 mật khẩu khác trong danh sách) cùng 1 lúc.
* Bài này phải dùng chức năng Turbo Intruder nó sẽ xếp toàn bộ dữ liệu ví dụ 30 request vào 1 đường ống, rồi gửi đi toàn bộ dữ liệu nhưng chỉ dữ lại bit cuối cùng.
* Thì thuật ngữ chỉ dữ lại bit cuối cùng là như nào
* Ví dụ : Mật khẩu là master thì trong request là password=master
* **Giai đoạn 1** Turbo Intrudẻ gửi 30 kết nối để server và bắt đầu gửi dữ liệu, nhưng nó cố tình cắt bỏ chữ cái cuối cùng.
* **Request 1:** Gửi password=maste... (Dừng lại, không gửi chữ r).
* **Request 2:** Gửi password=maste... (Dừng lại, không gửi chữ r).
* ...
* **Request 3:** Gửi password=maste... (Dừng lại, không gửi chữ r).
* **Lúc này Server đang làm gì?** Server nhận được các gói tin này, nhưng nó thấy chưa đủ dữ liệu (theo quy định HTTP, nó biết độ dài gói tin, nhưng nó chưa nhận được ký tự cuối). -> Server buộc phải đưa các request này vào trạng thái "TREO" (Pending/Waiting). Nó giữ 30 request này trong bộ nhớ RAM, chưa xử lý, chưa kiểm tra pass, chưa tăng bộ đếm lỗi.
* **Giai đoạn 2:** Chốt hạ (Open Gate) Khi lệnh engine.openGate() được kích hoạt. Turbo Intruder gom 30 chữ r còn thiếu của 30 request kia, đóng gói vào một gói tin TCP duy nhất (hoặc gửi cực nhanh).
* BÙM! Server nhận được 30 chữ r cùng một lúc.
* **Giai đoạn 3:** Xử lý đồng thời Ngay lập tức, 30 request đang bị "treo" trong RAM chuyển sang trạng thái "Hoàn thành" tại cùng một tích tắc. -> Server bắt đầu xử lý logic cho cả 30 cái:
* Luồng 1: Kiểm tra bộ đếm (đang là 0) -> OK -> Check pass.
* Luồng 2: Kiểm tra bộ đếm (vẫn đang là 0, vì Luồng 1 chưa kịp cộng) -> OK -> Check pass.
* ...
* Luồng 30: Kiểm tra bộ đếm (vẫn là 0) -> OK -> Check pass.
* <img width="1274" height="785" alt="image" src="https://github.com/user-attachments/assets/9dd9e609-2e54-4adb-a8aa-a5be028c634d" />
* Giải thích payload này là
* <pre> def queueRequests(target, wordlists):
    # DÒNG 1: Khởi động động cơ (Engine)
    engine = RequestEngine(endpoint=target.endpoint,
                           concurrentConnections=1, 
                           engine=Engine.BURP2
                           ) </pre>
* `concurrentConnections=1` Đây là chỗ khó hiểu nhất. Tại sao muốn nhanh mà lại chỉ dùng 1 kết nối?
  * Hãy tưởng tượng nó là 1 đường ống nước to. Để gửi đồng loạt, ta nhét tất cả 30 gói tin vào chung 1 đường ống này (nhờ giao thức HTTP/2). Nếu mở nhiều kết nối, các gói tin sẽ chạy lộn xộn, không đến cùng lúc được.
* `engine=Engine.BURP2` Bảo tool sử dụng giao thức HTTP/2 (cần thiết cho kỹ thuật gom gói tin này).
* <pre> # DÒNG 2: Chuẩn bị đạn (Danh sách mật khẩu)
    passwords = ["123456", "password", "master", ...] </pre>
    * Đây chỉ đơn giản là danh sách các mật khẩu tôi muốn thử.
* <pre> # DÒNG 3: Nạp đạn vào nòng (Xếp hàng - Queue)
    for password in passwords:
        engine.queue(target.req, password, gate='1') </pre>
* `target.req` Là cái request mẫu bạn gửi từ Burp qua (có chứa `%s`).
* `password` Nó sẽ lấy mật khẩu lắp vào chỗ %s
* `gate='1'` Đây là mấu chốt. Lệnh này bảo Turbo Intruder: "Xếp cái request này vào hàng đợi số 1, NHƯNG ĐỪNG GỬI NGAY, cứ giữ nó ở vạch xuất phát cho tao".
* <pre>#DÒNG 4: Khai hỏa!
  engine.openGate('1')</pre>
* `openGate('1')` Sau khi vòng lặp ở trên đã xếp đủ 30 "vận động viên" vào vạch xuất phát. Lệnh này giống như tiếng súng hiệu lệnh. BÙM! Tất cả 30 request lao đi cùng một lúc qua cái kết nối duy nhất đã tạo ở Dòng 1.

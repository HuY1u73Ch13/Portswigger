## Điều kiện cuộc đua đa điểm cuối 
* Bài này là race **Đa điểm (Single-endpoint).**
* Lab này buộc tôi phải phối hợp nhịp nhàng giữa 2 chức năng khác nhau:
* `POST /cart:` Thêm hàng vào giỏ.
* `POST /cart/checkout:` Thanh toán.
* **Hành động:** Tôi không gửi các yêu cầu giống nhau. Bạn phải gửi 1 cặp lệnh "Thanh Toán" và "Thêm hàng" chạy song song để lừa hệ thống.
* **Bình Thường:** Hệ thống kiểm tra: "Giỏ hàng có gì?" -> "Có thẻ quà tặng 10$" -> "Tài khoản đủ tiền không?" -> "Đủ" -> "Trừ 10$ và giao hàng"
* **Lỗ Hổng:** Lỗ hổng ở đây chính là có 1 khoảng hở thời gian giữa lúc hệ thống **kiểm tra tiền** (Validate) và lúc hệ thống **chốt đơn** (confirm).
* Tôi đã solve được lab này bằng cách đầu tiên thêm món hàng gitf card vào giỏ hàng gửi request kiểm tra giỏ hàng thì nó nghĩ tôi có 100$ mua gift card 10$ hợp lý và duyệt
* Nhưng ngay sau khi duyệt thì trước khi kịp chốt đơn request thêm áo khoác của tôi `POST /cart` lại chen ngang vào. Thì server lại thực hiện việc thêm áo vào
* Request checkout tiếp tục chạy theo luồng để hoàn thành quy trình chốt đơn.
* **Lỗi Logic** : lỗi ở đây là server lại không kiểm tra lại số dư nữa (vì nó đá kiểm tra ở bước 1 rồi). Và nó cứ lấy tất cả như thế để tạo đơn và hoàn thành việc thanh toán
* Thứ tự các request để solve bài lab này là
* <img width="1058" height="633" alt="image" src="https://github.com/user-attachments/assets/6d2a9e03-3171-465b-875b-0fd685e60864" />
* <img width="900" height="643" alt="image" src="https://github.com/user-attachments/assets/84531dd0-f6e8-42a5-ba50-95ed657494dc" />
* ![Uploading image.png…]()

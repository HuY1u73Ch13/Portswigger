## Thao túng tin nhắn WebSocket để khai thác lỗ hổng
* Đầu tiên websocket là 1 giao thức truyền thông mạng (network protocol) cho phép thiết lập một kênh giao tiếp 2 chiều (full duplex) và liên tục (persistent) giữa máy khách (Client - thường là trình duyệt) và máy chủ (server) thông qua 1 kết nối TCP duy nhất.
* Nói 1 cách đơn giản là cả 2 máy chủ và server và client đều có thể chủ động gửi tin nhắn cho nhau bất cứ lúc nào mà không cần phải hỏi và không cần chờ người kia hỏi trước.
* So sánh về cốt lõi: HTTP vs WebSocket
* HTTP (Cổ điển)
  * Hoạt động theo cơ chế Yêu cầu - Phản hồi
  * Client phải "hỏi" (gửi request), Server mới "trả lời" (gửi response).
  * Sau khi trả lời xong, kết nối bị đóng lại. Nếu client muốn gửi dữ liệu mới nó phải gửi yêu cầu mới.
  * VD: Bạn F5 trang báo để xem tin tức mới.
* WebSocket
  * Hoạt động theo cơ chế thời gian thực (realtime)
  * Kết nối được giữ mở liên tục
  * Server có thể chủ đồn đẩy dữ liệu xuống Client ngay khi có tin nhắn mới mà không cần Client phải yêu cầu.
* <img width="570" height="168" alt="image" src="https://github.com/user-attachments/assets/cb5c0daf-5472-429d-a353-ac2c21f78dd8" />
* Ở đây khi chặ gói ta thấy được đoạn payload trên đã được mã hóa vì thế tôi thử thay đôi payload thành thẳng bên dưới để gửi 
* <img width="527" height="209" alt="image" src="https://github.com/user-attachments/assets/779b018e-f6ca-42e0-a9cc-2d3d79848143" />
* Và thế là đã solve được câu này

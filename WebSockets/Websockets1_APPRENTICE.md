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
* 

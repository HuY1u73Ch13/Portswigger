## WebSocket Testing
### Định nghĩa
WebSocket Testing là quá trình kiểm thử giao thức giao tiếp hai chiều (full-duplex) và liên tục giữa client và server. Khác với HTTP (yêu cầu - phản hồi), WebSocket duy trì một kết nối TCP mở, cho phép server chủ động đẩy dữ liệu. Trong bảo mật, việc kiểm thử tập trung vào quá trình bắt tay (handshake), cơ chế xác thực phiên, và dữ liệu được truyền tải (frames) để đảm bảo attacker không thể chiếm quyền điều khiển hoặc tiêm mã độc.

### Những chỗ thường dính
- Lỗ hổng CSWSH (Cross-Site WebSocket Hijacking) - tương tự như CSRF.
- Giao thức không được mã hóa (ws:// thay vì wss://).
- Dữ liệu trong tin nhắn (message frames) không được validate (dẫn đến SQLi, XSS).
- Thiếu xác thực (Authorization) sau bước Handshake ban đầu.
- Endpoint thực hiện hành động nhạy cảm mà không kiểm tra lại token/session.

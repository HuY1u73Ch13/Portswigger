## Race Condition 

### Định nghĩa
Race Condition (Điều kiện tranh đua) là lỗ hổng xảy ra khi ứng dụng xử lý các yêu cầu đồng thời (concurrent) mà không có cơ chế đồng bộ hóa hoặc khóa (locking) an toàn. Vấn đề cốt lõi thường nằm ở lỗi TOCTOU (Time-of-Check to Time-of-Use): kẻ tấn công khai thác "khoảng trống" thời gian cực ngắn giữa lúc hệ thống kiểm tra điều kiện (ví dụ: còn tiền không?) và lúc thực hiện hành động (ví dụ: trừ tiền) để thực hiện thao tác vượt quyền hoặc gian lận.

### Những chỗ thường dính
- Chức năng áp dụng mã giảm giá (Coupon/Voucher) giới hạn số lần sử dụng
- Giao dịch tài chính (rút tiền, chuyển khoản) để thực hiện Double Spending
- Các tính năng tích điểm, đổi quà, hoặc bình chọn (Voting)
- Kiểm tra hàng tồn kho trong thương mại điện tử (mua vượt quá số lượng có sẵn)
- Quy trình Upload file (gọi file thực thi trước khi hệ thống kịp quét hoặc xóa file)
- Các ứng dụng đa luồng (multi-threaded) thao tác trên cùng một Database record

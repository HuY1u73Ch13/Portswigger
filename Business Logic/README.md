## Business Logic

### Định nghĩa
Business Logic Vulnerability xảy ra khi ứng dụng **hoạt động đúng về mặt kỹ thuật nhưng sai về mặt nghiệp vụ**.  
Lỗ hổng này không nằm ở code injection mà ở **cách hệ thống xử lý quy trình**.

### Những chỗ thường dính
- Thanh toán, hoàn tiền
- Mua hàng, áp mã giảm giá
- Đặt vé, đặt lịch
- Workflow nhiều bước nhưng không kiểm tra trạng thái
- Thao tác đảo ngược quy trình (skip step)

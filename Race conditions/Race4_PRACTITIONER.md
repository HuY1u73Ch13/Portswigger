## Điều kiện cuộc đua một điểm cuối 
* Vấn đề cốt lõi ở cơ chế này là thay đổi email có thể bị lừa nếu bạn gửi yêu cầu thay đổi quá nhanh. Hệ thống có thể gửi các mã xác nhận cho email A (của bạn) nhưng lại lưu email B (của nạn nhân) vào cơ sở dữ liệu trước khi quá trình xác thực hoàn tất. Khi bạn bấm vào link xác nhận của A, hệ thống vô tình xác nhận luôn cho email B.
* <img width="2128" height="679" alt="image" src="https://github.com/user-attachments/assets/7062fa2a-61f8-4682-b5b2-71a19d6d3f59" />
* Đầu tiên tôi bấm vào cập nhật email và thấy được gói `POST /my-account/change-email` cùng với trường email.
* Bây giờ tôi cần đổi địa chỉ email của req1 và req2 thành như hình ảnh bên dưới.
* <img width="534" height="644" alt="image" src="https://github.com/user-attachments/assets/705ee25a-7d5a-4ed6-83e6-7b6389000f97" />
* <img width="523" height="571" alt="image" src="https://github.com/user-attachments/assets/a3aee4dc-a4a9-4cd8-9ccc-c63a9695914b" />
* <img width="296" height="151" alt="image" src="https://github.com/user-attachments/assets/f0accb10-20c1-4b51-8b34-be80e128a8c3" />
* Gửi với `Send group (parallel)` 

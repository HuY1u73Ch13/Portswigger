<img width="897" height="623" alt="image" src="https://github.com/user-attachments/assets/8aab2652-7bc1-413e-bbad-45106308b40d" />## XXE mù với tương tác ngoài băng tần thông qua các thực thể tham số XML 
* Mục tiêu của lab này vẫn giống lab trước. Là chứng minh lab này bị lỗi `Blind XXE` bằng cách ép nó gủi 1 yêu cầu (DNS/HTTP) tới Burp Collaborator của tôi.
* Nhưng bài này đã nâng cao hơn 1 tí và hệ thống phòng thủ đã được nâng cấp.
* Server nó vẫn đọc XML nhưng nó đã được cấu hình để ngăn chặn các thực thể bên ngoài thông thường nhu là &
* <img width="897" height="623" alt="image" src="https://github.com/user-attachments/assets/10e06b34-70f1-4950-aadb-713462b22ea5" />
* Và tôi đã solve được lab này.
* Thay % thành # hoặc các cái khác sẽ không được vì `&` dùng để gọi các thực thể chung trong phần nội dung của XML ( giữa các thẻ)
* Và `%` để gọi các thực thể tham số như cái trên luôn nhưng chỉ hoạt động trong DTD (<!DOCTYPE [...] >)

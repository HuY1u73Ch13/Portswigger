## Tìm điểm cuối GraphQL ẩn
* Ở lab trước là ta khai thác thông tin nhạy cảm bị lộ
* Còn ở lab này là tìm ra Endpoint GraphQL đang trốn. Nó bị ẩn đi hoặc sử dụng các đường đẫn không phổ biến
* <img width="1549" height="515" alt="image" src="https://github.com/user-attachments/assets/dee185c7-94e2-4f09-8ee5-590930bd0466" />
* Thử /api sau đường dẫn ta được kết quả như này. Điều này chứng tỏ ta có thể query ngay tại đây.
* <img width="1365" height="519" alt="image" src="https://github.com/user-attachments/assets/c141d584-18f9-42b1-9403-a4b12f83dd39" />
* Thử query thêm ta được như này
* Vì server này đã được cấu hình để chặn từ khóa `__schema {` nên ta chỉ cần mã hóa đoạn sau là bybass được.
* <img width="580" height="264" alt="image" src="https://github.com/user-attachments/assets/27b5de2c-079b-4df9-816a-fc9782338146" />
* <img width="585" height="270" alt="image" src="https://github.com/user-attachments/assets/edd9a267-bba4-407d-a016-d58d78789a28" />
* <img width="420" height="235" alt="image" src="https://github.com/user-attachments/assets/a8b1e369-7c74-41dc-9504-bdf57bc04b89" />
* Gửi cái này ta biết được user carlos là 3
* <img width="587" height="272" alt="image" src="https://github.com/user-attachments/assets/6b4232e9-3c8f-4522-9173-db37bc5ae7ff" />
* Gửi query xóa và ta đã xóa được carlos

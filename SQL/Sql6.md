## SQL injection UNION attack, determining the number of columns returned by the query
- Ta sử dụng câu lênh **ORDER BY** để sắp xếp và tìm các số lượng cột
<img width="1543" height="277" alt="image" src="https://github.com/user-attachments/assets/4101bcec-eaed-4a74-8ba9-4e3e2868e9e1" />
<img width="1420" height="153" alt="image" src="https://github.com/user-attachments/assets/710f528d-5360-4a4f-825d-770e2bbdba4b" />
<img width="1398" height="127" alt="image" src="https://github.com/user-attachments/assets/50995fb1-80b3-49ba-be0f-e53c59d19b3f" />
<img width="1409" height="136" alt="image" src="https://github.com/user-attachments/assets/bbbceef1-6a63-45ab-8a97-1d2f32ad76f0" />
- Xác định được bảng có 4 cột ta sử dụng **UNION SELECT** để liệt kê ra các cột
<img width="1411" height="138" alt="image" src="https://github.com/user-attachments/assets/ac612039-f25a-4965-8503-3557eeabb84a" />
- Ta đã hoàn thành bài LAB nhờ cách trả về các hàng bổ xung bằng NULL

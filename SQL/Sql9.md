## Tấn công SQL injection UNION, truy xuất nhiều giá trị trong một cột 
- Tìm số lượng cột trong bảng từ **Order by**
<img width="1352" height="156" alt="image" src="https://github.com/user-attachments/assets/bbd2093e-0d8c-4f20-abe8-9cafb24108f8" />
<img width="1425" height="154" alt="image" src="https://github.com/user-attachments/assets/69e140d2-d903-42dd-b4a9-b445bb902790" />

- Xác định kiểu dữ liệu trả về của các cột
<img width="1295" height="154" alt="image" src="https://github.com/user-attachments/assets/1326f11b-5030-4508-be89-091eadc76eec" />

- Vì cột đầu tiên không phù hợp để sử dụng để trả về chuỗi kí tự nên ta phải kết hợp dữ liệu vào cột thứ 2
  bằng cách ||'-'|| để có cả dữ liệu **username** và **password**
<img width="1392" height="161" alt="image" src="https://github.com/user-attachments/assets/7496f148-2d83-4270-879d-dc89aeff601e" />

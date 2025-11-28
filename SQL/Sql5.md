## Tấn công tiêm SQL, truy vấn loại cơ sở dữ liệu và phiên bản trên MySQL và Microsoft
* <img width="1177" height="456" alt="image" src="https://github.com/user-attachments/assets/31290b36-4ff8-4de5-b1ee-0bd71864691d" />
* Đầu tiên tôi đọc truy vấn này không được và sau khi đọc hint
* <img width="546" height="86" alt="image" src="https://github.com/user-attachments/assets/4347b9fe-fff0-4662-894f-31c78d1cbece" />
* Tôi biết được sau dấu `--` ta có 1 khoảng trắng nên là tôi đã thêm %20 tương đương kí tự khoảng trắng sau `--` và nó đã trà về 200 như hình bên dưới
* <img width="1169" height="450" alt="image" src="https://github.com/user-attachments/assets/6a191b67-37ef-46d4-9aea-6a143e0baca9" />
* Nên có thể đoán được là có lỗi sql injec ở đây
* <img width="1146" height="471" alt="image" src="https://github.com/user-attachments/assets/53699508-d599-4189-a010-b292c6979cb5" />
* <img width="1222" height="606" alt="image" src="https://github.com/user-attachments/assets/48f54586-9eda-4016-ae3f-655e5479aff4" />
* Tiếp tục dùng lệnh ORDER BY để xem `Tech gifts` có bao nhiêu cột trong tập hợp kết quả truy vấn gốc
* Đến `ORDER BY 3` tức là khi đang cố gắng xắp sếp cột T3 trong bảng nhưng trả về lỗi suy ra bảng này chỉ có 2 cột
* <img width="1161" height="565" alt="image" src="https://github.com/user-attachments/assets/7de92ab0-23ae-410b-bfb4-7f18bf01e5c1" />
* Theo như xác định tiếp thì 2 bảng này đều có kiểu dữ liệu là String
* <img width="2015" height="697" alt="image" src="https://github.com/user-attachments/assets/02af9ca6-d827-4019-bdc3-4aa240891e89" />
* Và thử payload tiếp theo thì ta đã giải được bài này.







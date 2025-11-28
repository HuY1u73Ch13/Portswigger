## Tấn công SQL injection, truy vấn loại và phiên bản cơ sở dữ liệu trên Oracle
* Đề này bảo tôi phát hiện chỗ lỗi SQL và viết payload để truy vấn ra loại và phiên bản cơ sở dữ liệu trên Oracle.
* <img width="1595" height="591" alt="image" src="https://github.com/user-attachments/assets/96b665a0-48e2-442a-b4e4-9b478f35a6a5" />
* Thì tôi đã test và biết lỗi SQL ở trên trường category này.
* <img width="1376" height="405" alt="image" src="https://github.com/user-attachments/assets/bb558c76-ec79-4ab8-bbbf-1312f6edbefa" />
* <img width="1325" height="448" alt="image" src="https://github.com/user-attachments/assets/0df30d45-c565-476c-be17-f5332b1b92ce" />
* <img width="1506" height="458" alt="image" src="https://github.com/user-attachments/assets/7e42af01-9642-4894-b799-443ff6f90d66" />
* Tiếp theo tôi dùng lệnh `ORDER BY` để kiểm tra xem bảng có bao nhiêu cột
* Kỹ thuật này dựa trên việc sắp xếp kết quả theo số thứ tự của cột. Nếu bạn cố gắng sắp xếp theo một cột không tồn tại, cơ sở dữ liệu sẽ trả về lỗi cú pháp hoặc lỗi server.
* Thì theo như xác định bảng này có 2 cột
* <img width="2200" height="597" alt="image" src="https://github.com/user-attachments/assets/44a8b41d-7c80-42cb-bb53-81bd1677561d" />
* Tôi đã cố thử `/filter?category=Tech+gifts' UNION SELECT 'b', 'a'--` `/filter?category=Tech+gifts' UNION SELECT '1', 'a'--` thử xem các cột này thuộc kiểu dữ liệu nhưng không tìm được.
* <img width="826" height="124" alt="image" src="https://github.com/user-attachments/assets/b90f7b95-2e79-4d1f-8e4d-73e2c4de9348" />
* Theo như tôi tìm hiểu thì khi dùng `UNION SELECT` bắt buộc phải có `FROM` nên tôi đã thử payload khác
* <img width="2436" height="589" alt="image" src="https://github.com/user-attachments/assets/ede57959-b99b-4ec8-86de-63f33086d460" />
* Để giải thích về payload này thì
* Chọn ra 2 cột ở cột 1 không trả về gì cả còn ở cột 2 thì `BANNER` thì nó là cột bí mật trong database chứa thông tin phiên bản của oracle `FROM v$version` là chỉ ra hãy lấy thư mục bí mật đó có tên là `v$version` 







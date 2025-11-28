## Lỗ hổng SQL injection trong mệnh đề WHERE cho phép truy xuất dữ liệu ẩn
* `https://0afd00bc03ed5c78832b1e0f00ba0017.web-security-academy.net/product?productId=14` với 1 đường dẫn như này thì khi từ web gửi vào server nó sẽ hiểu với câu truy vấn sql là `SELECT * FROM products WHERE id = '14';`
* Vậy khi chúng ta chèn thêm ` OR 1=1 thì server nó sẽ hiểu là trả về tất cả các cột nếu id = '14' đúng hoặc '1=1' đúng nhưng ở đây 1=1 luôn đúng nên nó sẽ luôn trả về các giá trị.
* <img width="940" height="415" alt="image" src="https://github.com/user-attachments/assets/7c6abc24-63a8-4cf5-a31a-6a4ca15ceaa0" />
* <img width="1050" height="440" alt="image" src="https://github.com/user-attachments/assets/9a300f85-8e85-40db-8dd8-6a694b927b52" />
* Theo suy nghĩ ở trên thì tôi đã thử sql ở 2 trường id và trường category thì trường id trả về invalid trong khi trường category trả về kết quả 200 chứng tỏ nó đang có lỗ hổng ở đây

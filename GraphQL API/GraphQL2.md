## Vô tình tiếp xúc với các trường GraphQL riêng tư 
* Ở lab trước tìm và đọc 1 **Object** bị ẩn (bài blog ID số 3)
* **BOLA** tôi truy cập vào dữ liệu mà lẽ ra tôi không được phép thấy.
* Còn bài này tìm và đọc các **Fields** nhạy cảm trong 1 Object công khai.
* Sau khi dùng chức năng **set introspection query** tôi đã lấy được danh sách các Types trả về, có 1 Object cực kì quan trọng và **User**
* Trong này có các fields là `id`, `username`, và đặc biệt là `password`.
* Và có 1 hàm có tên là `getUser(id: Int!)` cho phép tôi lấy thông tin của user dựa trên thông tin của ID của họ.
* <img width="355" height="165" alt="image" src="https://github.com/user-attachments/assets/484ad2a1-9e15-47b6-b5d8-31974b0ff4c9" />
* <img width="567" height="222" alt="image" src="https://github.com/user-attachments/assets/d5fc2ff8-658d-470c-8054-287d5cbb83e5" />
* Điều chỉnh phần `GraphQL` và tôi đã có được tk mà mk.

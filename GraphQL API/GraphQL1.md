## Accessing private GraphQL posts
* <img width="743" height="313" alt="image" src="https://github.com/user-attachments/assets/74268177-d908-473e-94be-61b6630a9fa2" />
* Tôi thấy có gói này là khác lạ so với các gói khác
* <img width="569" height="118" alt="image" src="https://github.com/user-attachments/assets/56a99505-f64b-41f8-97fa-76e79f5f9b73" />
* Tôi thấy có 1 câu lệnh query trong gói trên như thế này.
* <img width="591" height="269" alt="image" src="https://github.com/user-attachments/assets/2ae3dbc7-2ea6-4fcc-a3d6-c79a2d10f893" />
* Thử câu lệnh này thì tôi nhận được web code 200
* <img width="589" height="241" alt="image" src="https://github.com/user-attachments/assets/725f223c-4ffd-460f-a341-c42c8bbfe10b" />
* Ta thấy trường **postPassword** đây là tính năng cho phép người dùng đặt mật khẩu cho riêng từng bài blog (private posts).
* Lập trình viên định nghĩa trường postPassword trong GraphQL Type để dùng cho các hàm quản trị (admin), nhưng lại vô tình để nó hiển thị công khai trong Schema mà không phân quyền (Authorization) ở mức trường dữ liệu (Field-level).
* <img width="587" height="277" alt="image" src="https://github.com/user-attachments/assets/47aaa4b0-b101-4f75-961c-70c193708092" />
* <img width="584" height="249" alt="image" src="https://github.com/user-attachments/assets/a97bc40a-604e-48f4-a1c0-d38b8c36a7aa" />
* Gửi cái này và cái ta nhận được là 2 trường `getBlogPost` và `getAllBlogPosts`
* Và sau đó tại khung `Query(GraphQL)` ta thêm
* <pre>query getBlogPost($id: Int!) {
    getBlogPost(id: $id) {
        id
        title
        postPassword
    }
  }
</pre>.
* Tại khung `Variables(JSON)`
* <pre>{
    "id": 3
  }
</pre>.
* <img width="582" height="271" alt="image" src="https://github.com/user-attachments/assets/c10a49e3-452d-405f-9d28-d96d4f7161e9" />
* Ta được mật khẩu như này

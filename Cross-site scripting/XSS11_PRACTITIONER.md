## DOM XSS trong biểu thức AngularJS với dấu ngoặc đơn góc và dấu ngoặc kép được mã hóa HTML 
* <img width="1217" height="478" alt="image" src="https://github.com/user-attachments/assets/697eb865-d5d9-4c6a-a1bd-bd6a8e18a536" />
* Với payload này tôi đã slove được bài này.
* Bài lab này muốn tôi tìm hiểu về cơ chế Template ở phía trình duyệt, cụ thể là với framework AngularJS.
* **Bối cảnh** : Ứng dụng cho web sử dụng AngularJS để quản lý giao diện. Nó có 1 vùng HTML được đánh dấu là `ng-app` (nơi mà AngularJS hoạt động).
* **Lỗi bảo mật** : Ứng dụng cho phép người dùng nhập dữ liệu và phản hồi lại dữ liệu đó vào trong vùng `ng-app` mà không lọc bỏ các kí tự đặc biệt của AngularJS (như dấu ngoặc nhọn {{ }}).
* **Hậu quả** : Khi Angular JS khời chạy hoặc quét lại trang, nó nhìn thấy các kí tự {{...}} do bạn nhập vào, nó sẽ tưởng đó là code của lập trình viên và thực thi nó. Điều này cho phép bạn chạy mã JavaScript độc hại (XSS) mà không cần thẻ `<script>` hay các thẻ HTML khác.
* Phân tích payload này.
* `{{ ... }}`: Đây là cú pháp nội suy (interpolation) của AngularJS. Bất cứ thứ gì nằm trong cặp ngoặc này sẽ được Angular tính toán và thực thi.
* `$on`: Đây là một hàm/đối tượng có sẵn trong Scope của AngularJS (thường dùng để lắng nghe sự kiện). Thực tế, attacker có thể dùng bất kỳ đối tượng nào có sẵn, miễn là nó có thuộc tính `constructor`
* `.constructor`: Đây là mấu chốt. Trong JavaScript, `constructor` của một hàm (như $on) chính là `Function` constructor (Hàm tạo hàm).
  *  Việc gọi `.constructor` giúp chúng ta "thoát" khỏi phạm vi biến cục bộ của Angular và chạm tới đối tượng `Function` gốc của JavaScript.
* `('alert(1)')`: Đây là tham số truyền vào cho `Function` constructor. Nó tương đương với việc bạn khai báo: `new Function('alert(1)')`. Kết quả trả về là một hàm vô danh có nội dung là `alert(1)`.
* `()`: Cặp ngoặc cuối cùng dùng để thực thi ngay lập tức hàm vừa được tạo ra ở bước trên.

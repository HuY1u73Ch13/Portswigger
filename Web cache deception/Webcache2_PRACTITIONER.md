## Khai thác dấu phân cách đường dẫn để đánh lừa bộ nhớ cache web
* Đây là 1 bài lab đánh lừa bộ nhớ đệm của web cSủa PortSwigger. Để giải quyết lab này tôi cần hiểu được cơ chế mà máy chủ gốc (Origin Server) hoặc là bộ nhớ đệm của máy chủ (Cache Server) xử lý URL khác nhau như nào khi gặp các ký tự phân cách.
* <img width="986" height="598" alt="image" src="https://github.com/user-attachments/assets/83dd06c8-ab63-4538-a9ae-c6a81acee075" />
* Theo như payload này thì khi gửi `GET /my-account;adad` nó trả về 200 chứng tỏ là Server đã nhìn thấy dấu ; và quyết đinh cắt bỏ và phớt lờ phần phía sau (adad), và chỉ xử lý phần phía trước (/my-account)
* <img width="1069" height="425" alt="image" src="https://github.com/user-attachments/assets/64c2b59f-4ba9-4242-89ab-9e5347a3becd" />
* Đổi request thành file tĩnh `;x.js` và sau khi gửi vài lần thì `X-Cache: hit`
* Khi mà `X-Cache: hit` nó chứng tỏ 3 vấn đề sau đây : khi `X-Cache: miss` thì nó phải hỏi máy chủ gốc và sau đó lưu lại và trả cho bạn
* Khi mà `X-Cache: hit` tức là Cache Server đã lưu dữ liệu này từ trước. Khi mà bạn hỏi lần nữa thì nó sẽ trả về ngay lập tức bản sao mà không liên lạc với `Origin Server` nữa.
* <img width="1074" height="318" alt="image" src="https://github.com/user-attachments/assets/d4f11b50-6e1d-4e6c-9fea-4bcabbb6a81f" />
* Gửi vài lần thì thấy  `X-Cache: hit` và `Cache-Control: max-age=30` trong vòng 30s nên là tôi đã gửi exploit này vào máy của nạn nhân 
* <img width="1147" height="171" alt="image" src="https://github.com/user-attachments/assets/c6c478d5-f3e7-46c3-bfc3-9b56d9b7e82c" />
* Và truy cập lại luôn ních này trong 30s thì tôi đã có API của carlos 

## Thực thi mã từ xa thông qua tải lên web shell 
* <img width="843" height="424" alt="image" src="https://github.com/user-attachments/assets/1ca35add-44cb-448f-b140-313609f41872" />
* Lab này cho tôi 1 tài khoản sẵn và yêu cầu của nó là hãy trích xuất nội dung tệp `/home/carlos/secret`
* <img width="1128" height="823" alt="image" src="https://github.com/user-attachments/assets/ae223c90-c87f-4e5b-8fca-e383baeb655e" />
* Tôi thử upfile php lên thì bài này vẫn cho phép upfile php
* <img width="1070" height="652" alt="image" src="https://github.com/user-attachments/assets/8c2aba6e-6c7b-478d-8dae-66e534f05fb7" />
* Tôi thử up hình ảnh lên và tôi đã thấy hình ảnh
* Và với ý tưởng này tôi thử up file php với lệnh echo `/home/carlos/secret` để coi mình có thể xem được không.
* <img width="1142" height="847" alt="image" src="https://github.com/user-attachments/assets/9edf2501-9167-4784-bf77-ecb6c257438a" />
* Tối bắt 1 gói upload và up nó lên thử sau khi bắt được thì tôi chỉnh sửa tên tệp và chỉnh `Content-Type: application/x-php`
* <img width="945" height="471" alt="image" src="https://github.com/user-attachments/assets/3fe978c8-3feb-4709-b210-8dd3d64eccfa" />
* Quay lại gói này và xem gói nhận về tôi vừa gửi thì được kết quả như trên




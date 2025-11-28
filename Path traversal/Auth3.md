## Duyệt đường dẫn tệp, trình tự duyệt bị loại bỏ không đệ quy 
* <img width="1063" height="508" alt="image" src="https://github.com/user-attachments/assets/16179aba-f9f3-4c9a-891d-9e45c94c3676" />
* <img width="1080" height="511" alt="image" src="https://github.com/user-attachments/assets/b1ee5ff9-d803-4a3f-aade-81362b06675f" />
* Ở đây tôi đã gửi thử 2 payload nhưng kết quả trả ra như nhau nên có vẻ ở đây nó đã bị lọc hoặc loại bỏ đi `../../` khi xử lý server
* <img width="1077" height="519" alt="image" src="https://github.com/user-attachments/assets/2b6b5b78-8da1-498a-bc04-ffab09544d5c" />
* <img width="1060" height="501" alt="image" src="https://github.com/user-attachments/assets/e95f0c81-8228-4cef-9a5d-dc2c2a1c0258" />
* Thử encode url và gửi nhưng có vẻ vẫn không được
* <img width="1073" height="506" alt="image" src="https://github.com/user-attachments/assets/ce2cde0a-1693-4a9b-b620-f000de70c96c" />
* <img width="1088" height="510" alt="image" src="https://github.com/user-attachments/assets/cd91bd1f-6238-4849-aa1a-ebb2f140a774" />
* <img width="1071" height="527" alt="image" src="https://github.com/user-attachments/assets/a80cd9f1-4a25-45c5-9ea3-71806e30509f" />
* Khi thử payload này thì được chứng tỏ server xử lý đằng sau bằng cách nếu phát hiện `../` thì xóa đi 1 lần và xử lý String còn lại vì thế ta vào được tệp `/etc/passwd`





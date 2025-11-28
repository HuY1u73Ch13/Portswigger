## Chèn lệnh hệ điều hành mù với độ trễ thời gian 
* <img width="1157" height="454" alt="image" src="https://github.com/user-attachments/assets/577d179f-4660-42f2-8bf3-3083299e8049" />
* Thử lỗi sql injection ở đây nó trả về 200 nên đoán được là nó đang ko filter kĩ ở đây
* Vì ở đây khi chèn OS vào nó chỉ STORE chứ không hiển thị nên dùng `whomi` ở đây không có ý nghĩa vì thế ta thử dùng lệnh khác như là lệnh sleep.
* <img width="1162" height="479" alt="image" src="https://github.com/user-attachments/assets/53717904-bbed-4445-95af-48cf46d499d1" />
* Tôi thử lệnh sleep ở đây và thấy nó mấy 10s mới trả về response nên chúng ta có thể biết được ở đây là lỗi oscommand

## Hạn chế điều kiện chạy quá mức 
* Race conditions mục tiêu của bài này là lợi dụng việc xử lý không đồng bộ để áp dụng mã giảm giá nhiều lần liên tiếp cho 1 đơn hàng, khiến giá của 1 chiếc áo khoác xuống mức giá rất rẻ.
* <img width="1215" height="152" alt="image" src="https://github.com/user-attachments/assets/0bdb61a6-8830-4acb-a5ec-5c06b2d23355" />
* Ta thấy có mã giảm giá 20% thì ta thử copy mã này rồi để thử giảm giá nhiều lần.
* <img width="2311" height="763" alt="image" src="https://github.com/user-attachments/assets/0e884d9d-6b38-4840-92e1-1cdb06af3695" />
* Gửi 21 lần với chế độ `send group (parallel)` thì ta đã giải được bài lab này.

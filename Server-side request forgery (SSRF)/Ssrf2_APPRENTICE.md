## SSRF cơ bản so với một hệ thống back-end khác 
* <img width="1105" height="590" alt="image" src="https://github.com/user-attachments/assets/013d6673-15ec-44c0-87b5-67c5577a689a" />
* Ta thấy có 1 gói /product/stock và parameter `stockApi=`
* <img width="618" height="136" alt="image" src="https://github.com/user-attachments/assets/f1b76944-127d-46d6-a5db-3c6c5da3a93f" />
* Decode chuỗi trên ta được 1 địa chỉ local. Gói này đang thực hiện gọi đến địa chỉ này để check số lượng hàng tồn kho
* Nhưng mục tiêu của ta là xóa được người dùng carlos thông qua api này.
* <img width="1072" height="497" alt="image" src="https://github.com/user-attachments/assets/025b85e1-f228-4bb6-907a-bf810d40c4b8" />
* <img width="793" height="691" alt="image" src="https://github.com/user-attachments/assets/f6743a5c-7ec6-413d-9100-573913d6eb9e" />
* Thử chèn payload vào địa chỉ cuối cùng của ip ta quêt được ip `192.168.0.18`
* <img width="528" height="162" alt="image" src="https://github.com/user-attachments/assets/4487fc97-c0ca-4284-91a1-74b41a7c8102" />
* Nó trả về cái này. Thử encode nó là gửi đi xem nó có xóa được người dùng carlos không.
* <img width="2269" height="549" alt="image" src="https://github.com/user-attachments/assets/8a1c7616-6c2e-4dd1-a21b-63e69196c8ea" />

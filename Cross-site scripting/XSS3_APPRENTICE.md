## DOM XSS in `document.write` sink using source `location.search`
* <img width="937" height="184" alt="image" src="https://github.com/user-attachments/assets/29f7f538-fab5-4c45-8d67-8658b653b4cf" />
* Truy cập và tìm kiếm bất kì để kiểm tra :
* <img width="766" height="337" alt="image" src="https://github.com/user-attachments/assets/74872643-e1a6-46f2-856d-071dc820c6c9" />
* Kiểm tra xem đoạn code được tìm kiếm như thế nào
* <img width="549" height="578" alt="image" src="https://github.com/user-attachments/assets/b934b63a-9edc-497f-9376-e360c2ed9aa9" />
* Ta có thể thấy đoạn **/img** được lưu trong 1 đoạn code ta sử dụng <img width="193" height="35" alt="image" src="https://github.com/user-attachments/assets/896183de-0c7d-44d0-b97b-741b96f75925" /> để bypass và in ra cảnh báo
* <img width="1917" height="953" alt="image" src="https://github.com/user-attachments/assets/7a95fe47-17e0-41b6-bc8d-873fa1b74ec6" />
* Ta hoàn thành bài lab nhờ cách bypass qua đoạn code khi trang web không lọc hoặc không kiểm soát dữ liệu đầu vào

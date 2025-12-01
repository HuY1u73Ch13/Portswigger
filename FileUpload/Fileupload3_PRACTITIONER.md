<img width="1156" height="887" alt="image" src="https://github.com/user-attachments/assets/895568c4-3c1f-4eac-b767-748484f089e0" />## Tải lên web shell thông qua duyệt đường dẫn 
* Bài này cũng cho tôi tài khoản sẵn và
* <img width="1114" height="892" alt="image" src="https://github.com/user-attachments/assets/fece2c57-5d34-4b6d-a6ec-4b0a13ce4284" />
* Lần này tôi vẫn up được lên nhưng có vẻ là tệp này nó đang không được xử lý đúng các mà chỉ in ra nội dung của file.
* Tôi đoán là do thư mục chứa file php này không được phép thực thi file php 
* Nên tôi đã thử upload file php này sang 1 thư mục khác.
* <img width="654" height="169" alt="image" src="https://github.com/user-attachments/assets/c3a74900-2e46-4075-93fc-c5fd71c6d928" />
* <img width="572" height="108" alt="image" src="https://github.com/user-attachments/assets/883c06e8-df37-4d69-a441-75ae7a396c02" />
* Tôi thử 2 cách này nhưng vẫn không được
* <img width="1156" height="887" alt="image" src="https://github.com/user-attachments/assets/929a2998-92cd-48bc-a51b-1bed3c682dc3" />
* Tôi thử upfile php với hàm system
* <img width="544" height="258" alt="image" src="https://github.com/user-attachments/assets/30ba4f2e-0f75-411b-b496-f9d5d7998c48" />
* Tiếp theo lùi file với `https://0ad2000c040b925582a4d869006e0023.web-security-academy.net/files/2.php?cmd=ls` command ls
* <img width="886" height="193" alt="image" src="https://github.com/user-attachments/assets/6af15295-eec2-4d41-8f6d-4759fd58435e" />
* Và nó đã đọc được file và
* `https://0ad2000c040b925582a4d869006e0023.web-security-academy.net/files/2.php?cmd=cat+/home/carlos/secret`
* Thay url bằng command trên và ta sẽ đọc được file
* <img width="1050" height="218" alt="image" src="https://github.com/user-attachments/assets/5aae9b02-cf7e-44f5-ada2-4e7afb6eff06" />


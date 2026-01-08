## Khai thác XXE mù để truy xuất dữ liệu thông qua thông báo lỗi 
* Lab này bảo phải khai thác qua thông báo trả về lỗi trên response
* <img width="1551" height="648" alt="image" src="https://github.com/user-attachments/assets/bc2b1d2c-5794-4049-b90b-8dd828b69765" />
* Tôi đã solve được bài này.
* Giải thích về payload này thì là đầu tiên khi gửi đi nó sẽ thực thi `<!ENTITY % file SYSTEM "file:///etc/passwd">` cái này trước và đọc file /etc/passwd và nó sẽ lưu vào bộ nhớ với cái tền là `% file`
* khi thực thể `% eval` được thực thi thì máy chủ sẽ lấy nội dung từ `% file` đã lưu trước. Và khi nó thực thi cái exfil kia thì nó lại không thấy đường dẫn ma kia và nó trả về `XML parser exited with error: java.io.FileNotFoundException:`
* Kèm với thực thể `% file` luôn.

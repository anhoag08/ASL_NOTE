#Design_Pattern 

Viết tắt của Command and Query Responsibility Segregation, một pattern tách rời việc độc và ghi cho một cơ sở dữ liệu. 

# Bài toán
- Trong một kiến trúc truyền thống, một cơ sở dữ liệu được dùng cho cả việc đọc và ghi. Kiến trúc cơ bản này hoạt động tốt cho các hoạt động CRUD (Create, Read, Update, Delete) cơ bản. Tuy nhiên trong các ứng dụng phức tạp hơn, cách tiếp cận này có thể trở nên bất khả thi. Ví dụ, Trong phần đọc, ứng dụng có thể sử dụng các truy vấn khác nhau cùng lúc, trả về các data transfer object (DTO) với các dạng khác nhau. Ánh xạ các đối tượng trên có thể trở nên phức tạp. Trong phần ghi, model có thể ứng dụng các luật và xác thực phức tạp. Vì vậy, bạn có thể nhận được một model quá phức tạp và làm quá nhiều thứ.
- Việc độc và ghi thường tạo ra khối lượng công việc khác nhau với các yêu cầu về hiệu năng và scale rất khác biệt.
![[Pasted image 20231028104757.png|500]]

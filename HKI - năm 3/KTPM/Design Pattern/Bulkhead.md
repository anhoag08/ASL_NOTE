#Design_Pattern

# Link Azure:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead

# Định nghĩa:
- Là một dạng thiết kế ứng dụng giúp chống chịu sự cố. Trong kiến trúc Bulkhead, các thành phần của một ứng dụng được cách ly thành các nhóm để nếu một phần gặp sự cố, các thành phần khác vẫn tiếp tục hoạt động.

# Bài toán:
- Một ứng dụng cloud có thể bao gồm nhiều dịch vụ, với mỗi dịch vụ có một hoặc nhiều người dùng. Khối lượng công việc quá lớn hoặc sự cố trong dịch vụ sẽ ảnh hưởng tất cả các người dùng của dịch vụ này.
- Và một người dùng có thể gửi yêu cầu tới nhiều dịch vụ cùng lúc, sử dụng tài nguyên cho mỗi yêu cầu. Nếu người dùng gửi yêu cầu tới dịch vụ và có lỗi, các tài nguyên sử dụng bởi người dùng có thể không được giải phóng đúng lúc và nếu dịch vụ tiếp tục chạy thì các tài nguyên này có thể không tiếp cận lại được và sẽ ảnh hưởng đến các dịch vụ khác cùng sử dụng tài nguyên này.

# Cách hoạt động
- Phân chia các dịch vụ thành các nhóm khác nhau, dựa vào khối lượng sử dụng và yêu cầu sẵn sàng hoặc chia một dịch vụ thành nhiều dịch vụ con của nó. Thiết kế này giúp cô lập sự cố và cho phép bạn duy trì tính năng của dịch vụ cho một số người dùng, kể cả khi gặp sự cố.
- Một người dùng cũng có thể phân chia tài nguyên để đảm bảo các tài nguyên được sử dụng để gọi tới một dịch vụ không ảnh hưởng đến các tài nguyên gọi đến các dịch vụ khác. Khi đó nếu một dịch vụ bị lỗi thì chỉ tài nguyên gọi đến dịch vụ đó bị ảnh hưởng thay vì ảnh hưởng tới tất cả các tài nguyên khác, cho phép người dùng tiếp tục sử dụng các dịch vụ không bị lỗi.

# Ưu điểm
- Cô lập người dùng và dịch vụ khỏi sự cố dây chuyền. Một sự cố ảnh hưởng tới một người dùng hoặc một dịch vụ có thể được cô lập, ngăn ngừa toàn bộ dự án ngừng hoạt động
- Cho phép bạn giữ lại một vài tính năng trong trường hợp một dịch vụ gặp sự cố. Các dịch vụ và tính năng khác vẫn sẽ tiếp tục hoạt động.
- Cho phép bạn triển khai các dịch vụ cung cấp các chất lượng dịch vụ khác nhau cho ứng dụng sử dụng chúng, những người sử dụng có mức ưu tiên cao sẽ được sử dụng các dịch vụ cao cấp hơn.

![[Pasted image 20231007113823.png]]
- Ảnh trên cho thấy do dịch vụ A được cô lập nên khi A lỗi thì B và C vẫn hoạt động.


![[Pasted image 20231007113834.png]]
- Ảnh trên cho thấy nhiều người dùng sử dụng một dịch vụ, các người dùng được chia cho các instance khác nhau nên nếu một instance gặp sự cố thì các instance khác vẫn tiếp tục hoạt động


# Hạn chế
- Khó khăn trong việc phân chia các nghiệp vụ và yêu cầu kỹ thuật thành các vùng khác nhau trong ứng dụng
- Có overhead do phải có thêm sự giao tiếp giữa các kết nối trung gian và ứng dụng chính.
- Tốn chi phí cho việc phân chia tài nguyên, độ cô lập càng cao chi phí càng tốn kém
- Khó khăn trong việc theo dõi hiệu năng của toàn hệ thống.

# Khi nào sử dụng pattern này
- Khi cần cô lập các tài nguyên dùng để vận hành các dịch vụ backend.
- Cô lập các loại người dùng khác nhau.
- Bảo vệ hệ thống khỏi sự cố dây chuyền.



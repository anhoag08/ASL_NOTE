#Design_Pattern 

# Link Azure:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/sidecar

# Định nghĩa
- Pattern này tập trung vào việc tách biệt các tính năng bổ sung và chức năng hỗ trợ  khỏi các ứng dụng chính và đặt chúng trong các tiến trình hoặc container riêng biệc (sidecar) và chạy song song với ứng dụng chính. Đồng thời cho phép ứng dụng chính được cấu tạo thành từ nhiều tiến trình, công nghệ riêng biệt và độc lập

# Cách hoạt động
- Sidecar không nhất thiết phải là một phần của ứng dụng chính nhưng nó được connect tới ứng dụng chính.
- Các task có liên quan mạnh đến nhau sẽ được đưa vào app chính còn các hoạt động cần thiết nhưng không liên quan đến nghiệp vụ của app chính sẽ được tách biệt thành các sidecar

# Ưu điểm:
- Sidecar có thể sử dụng ngôn ngữ, công nghệ riêng biệt với app chính vì nó độc lập với app chính trong môi trường chạy
- Sidecar có thể tiếp cận các tài nguyên chung với app chính và thực hiện các dịch vụ liên quan đến tài nguyên đó.
- Vì được liên kết gần gũi nên sẽ không tạo ra trễ khi tương tác giữa app chính và sidecar
- Kể cả nếu app chính của bạn không cung cấp khả năng mở rộng, sidecar có thể được dùng như một app phụ hoặc host cho các container khác.

# Nhược điểm
- Các khó khăn trong việc lựa chọn phương pháp đóng gói và deploy.
- Khi thiết kế sidecar, cần phải lựa chọn kỹ càng phương pháp giao tiếp giữa app chính và sidecar. Nên sử dụng các công nghệ phát triển cụ thể cho framework hoặc ngôn ngữ đó trừ khi gặp vấn đề hiệu năng.
- Cần quyết định xem sidecar có thể được phát triển thành một dịch vụ độc lập thay vì như một thực thể
- Cần xem xét sidecar có thể được triển khai dưới một dạng thư viện, thư viện tích hợp sâu cho app chính có thể giảm độ trễ mạng.
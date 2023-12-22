#Design_Pattern 

Khi bạn sử dụng một hoạt động tuần tự bao gồm một loạt các bước, mô hình CT có thể trở nên hữu dụng, đặc biệt khi một trong các bước gặp lỗi, CT sẽ rollback các công việc tại bước đó

# Bài toán
- Ứng dụng chạy trên cloud thường xuyên thay đổi dữ liệu. Các dữ liệu này thường trải dài qua các nguồn dữ liệu khác nhau tại các địa điểm khác nhau, để tránh cạnh tranh và tăng hiệu năng trong một môi trường phân tán, một ứng dụng không nên cung cấp sự 
#Design_Pattern 

# Azure Architecture Link : https://learn.microsoft.com/en-us/azure/architecture/patterns/throttling

# Bài toán
- Khối lượng công việc của ứng dụng đám mây thường sẽ biến thiên theo thời gian dựa trên số lượng người sử dụng đang hoạt động hoặc dựa và các hoạt động mà họ đang thực hiện. Ví dụ, nhiều người dùng thường hoạt động trong giờ hành chính, hoặc hệ thống sẽ phải thực hiện các tính toán đắt đỏ và cuối mỗi tháng. Có thể sẽ có các sự tăng đột biến về hoạt động trong hệ thống. Nếu yêu cầu xử lý của hệ thống vượt mức tài nguyên có thể đáp ứng, hệ thống sẽ hoạt động chậm và có thể gặp lỗi. Nếu hệ thống cần phải đáp ứng được một mức độ dịch vụ nào đó, cần phòng ngừa các lỗi đó.

# Giải pháp


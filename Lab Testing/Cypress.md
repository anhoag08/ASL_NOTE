#LabTesting
Điểm mạnh:

- Dễ dàng setup: Đa số công việc setup được làm nhờ setup tool của Cypress.
- Hỗ trợ các plug-in giúp hỗ trợ tester cũng như cho phép tester cài đặt môi trường làm việc tùy ý.
- Có UI cho review report và log của test mà không cần tải thêm thư viện
- Tự động chờ async await mà k cần dùng wait().
- Hiệu suất nhanh do xây dựng sử dụng kiến trúc riêng.
- Toàn bộ các chức năng cần có cho tester được đi kèm từ đầu mà không cần cài thêm thư viện.

Điểm yếu:
- Chỉ hỗ trợ Java Script/ Type Script.
- Không thể chạy test trên nhiều browser hoặc multi-tab cùng lúc.
- Lượng web browser hỗ trợ ít.
-  Như Selenium, không thể select được các items được sinh ra động.
- Thiếu khả năng cài đặt chi tiết môi trường lập trình và mỗi lần chạy kiểm thử cần tester tương tác với UI của Cypress để chạy test gây mất thời gian.

Đặc trưng:
- Là công cụ dễ set-up và sử dụng nhất cho UI Testing, với việc có tất cả các tính năng được phát triển nhằm hòa hợp với nhau giúp cho hiệu suất sử dụng cao. Tuy nhiên đổi lại là khả năng tùy chỉnh cũng như tự động hóa là thấp hơn so với các công cụ khác.

Ý kiến:
- Với việc dễ set-up và sử dụng, Cypress rất phù hợp cho người mới học kiểm thử UI, tuy nhiên việc thiếu khả năng tùy chỉnh và work-flow mang tính thủ công khiến Cypress không phù hợp với kiểm thử phức tạp.
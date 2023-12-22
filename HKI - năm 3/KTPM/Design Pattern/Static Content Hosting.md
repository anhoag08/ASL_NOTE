#Design_Pattern 

# Azure Architecture Link: 
*https://learn.microsoft.com/en-us/azure/architecture/patterns/static-content-hosting

# Định nghĩa
- Triển khai nội dung tĩnh lên các dịch vụ lưu trữ đám mây có thể chuyển nội dung trực tiếp tới người dùng. Điều này sẽ làm giảm nhu cầu tính toán đắt đỏ

# Bài toán
- Các ứng dụng web thường chứa một số thành phần là nội dung tĩnh. Các nội dung tĩnh này có thể bao gồm các trang HTML hoặc các tài nguyên khác như hình ảnh, chữ mà sẽ cho phép người dùng truy cập, bằng cách đóng 1 phần trong trang HTML (hình ảnh trong trang, style sheet, client-side JS) hoặc các nội dung cần tải xuống (nội dung PDF)
- Mặc dùng các web server đã và đang được tối ưu cho việc render động và caching đầu ra, các server này vẫn cần xử lý các yêu cầu để tải các nội dung tĩnh. Điều này sẽ tiêu tốn các tài nguyên xử lý

# Giải pháp
- Trong đa số các môi trường hosting đám mây, bạn có thể lưu một vài tài nguyên hoặc các trang tĩnh của ứng dụng trong các dịch vụ lưu trữ. Dịch vụ lưu trữ có thể xử lý các yêu cầu cho các tài nguyên này, giảm tải trọng cho các tài nguyên tính toán xử lý các yêu cầu khác của trang web. Giá thành cho dịch vụ lưu trữ đám mây thường rẻ hơn là máy ảo tính toán.
- Khi lưu trữ một số phần của một ứng dụng trong một dịch vụ lưu trữ, yêu cầu chính liên quan đến việc triển khai ứng dụng và đảm bảo bảo mật cho các dữ liệu không dành cho người dùng ẩn danh.

# Vấn đề
- Hệ thống lưu trữ cần cung cấp API để truy cập các tài nguyên, có thể khó khăn trong việc cần tìm các loại giao thức khác nhau (HTTP, HTTPS, ...)
- Để đáp ứng tối đa hiệu năng và tính sẵn sàng, cân nhắc sử dụng mạng lưới nội dung (CDN) để cache các nội dung của các dịch vụ lưu trữ ở các vị trí địa lỹ thuận lợi.
- Cân nhắc sử dụng các key hoặc token nhằm đảm bảo bảo mật cho tài nguyên.

# Khi nào dùng
- Tối ưu chi phí cho việc triển khai web, ứng dụng mà chứa các tài nguyên tĩnh
- Sử dụng một dịch vụ lưu trữ chung cho các ứng dụng được triển khai tại các môi trường khác nhau
- Lưu trữ tài nguyên tĩnh tại các vị trí địa lý khác nhau dùng một mạng lưới dữ liệu cache tại các vị trí khác nhau
- Tách rời chi phí, tài nguyên cho việc lưu trữ, giao tiếp các tài nguyên tĩnh khỏi hệ thống chính
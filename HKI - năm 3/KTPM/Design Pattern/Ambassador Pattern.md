#Design_Pattern 

**Định nghĩa**

- Mô hình thiết kế Ambassador (Ambassador Design Pattern) là một mô hình thiết kế phần mềm được sử dụng để quản lý và kiểm soát giao tiếp giữa các thành phần của hệ thống. Mô hình này tập trung vào việc tạo ra một lớp trung gian (được gọi là "Ambassador") để xử lý và kiểm soát giao tiếp giữa các thành phần khác nhau của ứng dụng.


Ưu điểm:
- Việc tách proxy giúp kiểm soát cácvấn đề đến routing, security và ngăn các vấn đề liên quan đến ràng buộc của host.
- Đồng thời proxy có thể kiểm soát các chỉ số performance như độ trễ, lượng tài nguyên sử dụng, và có thể kiểm soát các chỉ số này trong cùng môi trường với ứng dụng host

Hạn chế:
- Việc tạo lớp trung gian sẽ tăng độ trễ
- Proxy sẽ đơn giản hóa các quá trình liên lạc cho service nhưng điều này có thể tiềm ẩn rủi ro
- Hạn chế trong việc package và deploy proxy
- Hạn chế trong việc quyết định deploy một proxy cho tất cả client hay mỗi proxy cho một client

Khi nào sử dụng pattern này:
- Khi cần deploy một ứng dụng có nhiều client connect qua nhiều ngôn ngữ hoặc giao diện network khác nhau
- giảm load xử lý cho host hoặc tách biệt việc xử lý connectivity cho một bên thứ 3
- Cần hỗ trợ dịch vụ cloud hoặc các dạng cụm connect mà không thể update ứng dụng host
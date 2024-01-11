#Design_Pattern 

# Link Azure:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/federated-identity

Mô hình "Federated Identity" là một phương thức trong lĩnh vực an ninh thông tin, nơi người dùng có thể xác thực một lần và sau đó được xác thực bởi nhiều hệ thống khác nhau mà không cần phải nhập lại thông tin xác thực. Điều này thường được sử dụng trong môi trường có nhiều dịch vụ và ứng dụng khác nhau, giúp cải thiện trải nghiệm người dùng và quản lý an ninh.

**Cách Hoạt Động:**

1. **Xác Thực Ban Đầu:**
    
    - Người dùng thực hiện quá trình xác thực ban đầu tại một điểm cuối xác thực. Thông thường, điều này là một hệ thống xác thực chính (Identity Provider - IdP) có trách nhiệm xác nhận danh tính người dùng.
2. **Cấp Token Hoặc Voucher:**
    
    - Sau khi xác thực thành công, IdP cấp một token hoặc voucher chứa thông tin xác thực của người dùng. Token này thường chứa các thông tin như ID người dùng, quyền truy cập, và thời gian hiệu lực.
3. **Chuyển Đến Dịch Vụ Tiếp Theo:**
    
    - Người dùng sử dụng token hoặc voucher này để truy cập các dịch vụ khác nhau mà không cần phải xác thực lại. Đối với mỗi dịch vụ, token được chuyển đến để xác định danh tính và quyền truy cập của người dùng.
4. **Rõ Ràng và An Toàn:**
    
    - Mô hình này giữ cho người dùng rõ ràng và an toàn trong quá trình sử dụng nhiều ứng dụng và dịch vụ khác nhau. Họ không cần phải nhớ và nhập lại thông tin xác thực nhiều lần.
5. **Quản Lý Quyền Truy Cập:**
    
    - IdP có thể quản lý và cung cấp quyền truy cập cho người dùng tới từng dịch vụ cụ thể. Điều này giúp kiểm soát an ninh và quản lý quyền truy cập theo cách linh hoạt và hiệu quả.
6. **Tích Hợp Mút Xác Thực (Single Sign-On - SSO):**
    
    - Mô hình "Federated Identity" thường đi kèm với tính năng Single Sign-On, nơi một lần xác thực cho phép người dùng truy cập một loạt các dịch vụ mà không cần phải đăng nhập lại.
7. **Chuẩn Hóa Giao Thức:**
    
    - Để thực hiện mô hình này, các chuẩn giao thức như SAML (Security Assertion Markup Language), OAuth, hoặc OpenID Connect thường được sử dụng để quản lý quá trình xác thực và chia sẻ thông tin xác thực.

Mô hình "Federated Identity" giúp cải thiện tính linh hoạt, an toàn, và trải nghiệm người dùng trong các hệ thống phức tạp có nhiều dịch vụ và ứng dụng.
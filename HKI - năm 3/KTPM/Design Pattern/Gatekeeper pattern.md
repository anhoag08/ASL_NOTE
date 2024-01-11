#Design_Pattern 

# Link Azure: 
*https://learn.microsoft.com/en-us/azure/architecture/patterns/gatekeeper

Mô hình "Gatekeeper" là một biện pháp an ninh thiết kế để kiểm soát và giám sát quyền truy cập vào các tài nguyên hệ thống. Mô hình này thường được triển khai như một lớp trung gian giữa người dùng hoặc các thành phần bên ngoài và tài nguyên nội bộ của hệ thống. "Gatekeeper" giúp kiểm soát, giám sát và thậm chí có thể thay đổi các yêu cầu truy cập dựa trên các quy tắc và chính sách an ninh.

**Cách Hoạt Động:**

1. **Xác Thực (Authentication):**
    
    - "Gatekeeper" thường thực hiện quá trình xác thực để xác định danh tính của người dùng hoặc thành phần yêu cầu truy cập. Điều này có thể bao gồm việc sử dụng mật khẩu, mã thông báo, hoặc các phương thức xác thực khác.
2. **Ủy Quyền (Authorization):**
    
    - Sau khi xác thực, "Gatekeeper" kiểm tra quyền truy cập của người dùng hoặc thành phần dựa trên các quy tắc và chính sách an ninh. Nó quyết định liệu họ có quyền truy cập vào tài nguyên mong muốn hay không.
3. **Quản Lý Quyền Truy Cập:**
    
    - "Gatekeeper" duy trì và quản lý các quyền truy cập cho từng người dùng hoặc thành phần trong hệ thống. Nó có thể sử dụng các nguyên tắc như nguyên tắc tưởng đối (least privilege) để giảm rủi ro an ninh.
4. **Kiểm Soát Yêu Cầu (Request Control):**
    
    - "Gatekeeper" có khả năng kiểm soát các yêu cầu truy cập, đặt ra các điều kiện và hạn chế các loại hoạt động cụ thể. Điều này giúp bảo vệ tài nguyên hệ thống khỏi các mối đe dọa an ninh.
5. **Giám Sát (Monitoring):**
    
    - Mô hình này thường cung cấp chức năng giám sát để theo dõi các hoạt động truy cập. "Gatekeeper" ghi lại thông tin về người dùng, tài nguyên và các sự kiện an ninh liên quan để phục vụ mục đích kiểm tra và xác định xâm nhập.
6. **Thống Nhất (Consistency):**
    
    - "Gatekeeper" có thể giúp đảm bảo tính nhất quán trong việc thực hiện chính sách an ninh trên toàn hệ thống. Điều này giúp tránh những lỗ hổng an ninh do sự không nhất quán trong việc quản lý quyền truy cập.
7. **Bảo vệ Tài Nguyên Nội Bộ:**
    
    - "Gatekeeper" bảo vệ tài nguyên nội bộ của hệ thống khỏi sự truy cập trái phép hoặc không ủy quyền, giữ cho các tài nguyên quan trọng an toàn.
8. **Tích Hợp Với Cơ Sở Hạ Tầng Hiện Có:**
    
    - Mô hình "Gatekeeper" thường được tích hợp với cơ sở hạ tầng hiện có, như proxy, API gateway, hay các giải pháp bảo mật khác để đảm bảo tính tương thích và linh hoạt.

Mô hình "Gatekeeper" đóng vai trò quan trọng trong việc bảo vệ hệ thống và tài nguyên khỏi các mối đe dọa an ninh bằng cách kiểm soát và quản lý quyền truy cập một cách chặt chẽ.
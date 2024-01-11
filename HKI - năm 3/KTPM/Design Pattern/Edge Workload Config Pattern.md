#Design_Pattern 

# Link Azure:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/edge-workload-configuration


"Edge Workload Configuration pattern" là một mô hình thiết kế được sử dụng trong kiến trúc phần mềm để quản lý cấu hình của các công việc (workloads) chạy tại các đỉnh (edge) của mạng, thường là tại các thiết bị IoT hoặc các hệ thống xử lý đám mây gần đó. Mô hình này giúp tối ưu hóa việc triển khai và quản lý cấu hình tại các điểm đỉnh mạng.

**Cách hoạt động:**

1. **Xác Định Cấu Hình Workload:**
    
    - Xác định và đặt ra các yêu cầu cấu hình cho công việc cụ thể (workload). Điều này bao gồm các thông số như nguồn dữ liệu đầu vào, cấu hình hệ thống, an ninh, và các thông số khác quan trọng.
2. **Lưu Trữ Cấu Hình Tại Trung Tâm Quản Lý (Centralized Configuration Management):**
    
    - Lưu trữ cấu hình tại một trung tâm quản lý, thường là một hệ thống quản lý cấu hình tập trung. Điều này giúp quản lý và theo dõi cấu hình từ một vị trí duy nhất.
3. **Triển Khai Cấu Hình Đến Edge Devices:**
    
    - Các cấu hình được triển khai xuống các thiết bị đỉnh mạng từ trung tâm quản lý. Quá trình này có thể được thực hiện tự động và có thể được kích hoạt bởi sự thay đổi trong yêu cầu hoặc cập nhật.
4. **Cập Nhật Động Cấu Hình:**
    
    - Cung cấp khả năng cập nhật động cấu hình tại các đỉnh mạng mà không cần tới sự can thiệp trực tiếp từ người quản trị. Điều này giúp nhanh chóng thích ứng với thay đổi môi trường hoặc yêu cầu.
5. **Quản Lý Phiên Bản Cấu Hình:**
    
    - Quản lý phiên bản của cấu hình để có thể quay trở lại phiên bản trước đó nếu cần thiết. Điều này giúp giảm thiểu rủi ro khi triển khai các cập nhật cấu hình mới.
6. **Bảo Mật Cấu Hình:**
    
    - Bảo vệ cấu hình từ việc truy cập trái phép bằng cách sử dụng các biện pháp bảo mật như mã hóa và xác thực.
7. **Giám Sát và Báo Cáo:**
    
    - Cung cấp các cơ chế giám sát để theo dõi việc triển khai cấu hình và báo cáo về tình trạng hoạt động của edge workloads.

Mô hình này giúp giảm bớt khả năng lỗi và tối ưu hóa quá trình quản lý cấu hình cho các công việc chạy tại các điểm đỉnh mạng.
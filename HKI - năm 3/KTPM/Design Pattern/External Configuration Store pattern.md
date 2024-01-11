#Design_Pattern 

# Link Azure:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/external-configuration-store


Mô hình "External Configuration Store" là một biện pháp kiến trúc được sử dụng để quản lý và lưu trữ các cấu hình của ứng dụng mà không cần phải tích hợp chúng trực tiếp vào mã nguồn của ứng dụng. Thay vì lưu trữ cấu hình trong mã nguồn, chúng được giữ ở một nơi tách biệt gọi là "External Configuration Store."

**Cách Hoạt Động:**

1. **Lưu Trữ Cấu Hình Ở Nơi Tách Biệt:**
    
    - Các thông số cấu hình như các giá trị kết nối cơ sở dữ liệu, cài đặt hệ thống, đối với các môi trường khác nhau (phát triển, thử nghiệm, sản xuất), được lưu trữ ở nơi tách biệt từ mã nguồn của ứng dụng. Điều này có thể là một kho dữ liệu trực tuyến, tệp tin cấu hình, hoặc các dịch vụ quản lý cấu hình.
2. **Truy Cập Từ Ứng Dụng:**
    
    - Khi ứng dụng khởi chạy hoặc cần truy cập cấu hình, nó sẽ gọi tới External Configuration Store để lấy thông tin cấu hình. Các thông số này có thể được đọc khi ứng dụng khởi chạy hoặc được tải lại khi cần thiết.
3. **Khả Năng Cập Nhật Linh Hoạt:**
    
    - Do cấu hình được lưu trữ ngoại tuyến, các thay đổi cấu hình có thể được áp dụng mà không cần phải triển khai lại ứng dụng. Điều này mang lại linh hoạt cao trong việc cập nhật cấu hình mà không làm gián đoạn hoạt động của ứng dụng.
4. **Bảo Mật và Quản Lý Phiên Bản:**
    
    - External Configuration Store có thể cung cấp cơ chế bảo mật để kiểm soát quyền truy cập và quản lý phiên bản của cấu hình. Điều này giúp đảm bảo rằng chỉ những người được ủy quyền mới có thể truy cập và thay đổi cấu hình.
5. **Dễ Dàng Quản Lý:**
    
    - Quản lý cấu hình từ một vị trí tách biệt giúp tăng cường khả năng quản lý, giúp dễ dàng theo dõi và thay đổi cấu hình của ứng dụng.
6. **Hỗ Trợ Nhiều Môi Trường:**
    
    - External Configuration Store cho phép quản lý và duy trì cấu hình cho nhiều môi trường khác nhau mà không cần sửa đổi mã nguồn.

Mô hình này giúp tách biệt việc quản lý cấu hình và mã nguồn ứng dụng, giảm sự phụ thuộc và tăng tính linh hoạt trong quá trình triển khai và quản lý hệ thống.
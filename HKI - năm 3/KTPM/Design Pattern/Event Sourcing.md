#Design_Pattern 

# Link Azure:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/event-sourcing

  
Mô hình "Event Sourcing" là một kiểu thiết kế trong phần mềm nơi dữ liệu không chỉ được lưu trữ ở trạng thái hiện tại của hệ thống mà còn được lưu trữ dưới dạng sự kiện (event) đã xảy ra. Thay vì chỉ lưu trữ trạng thái hiện tại của đối tượng, hệ thống Event Sourcing theo dõi và lưu trữ tất cả các sự kiện đã xảy ra với đối tượng đó từ thời điểm ban đầu.

**Cách Hoạt Động:**

1. **Tạo và Lưu Trữ Sự Kiện:**
    
    - Mỗi khi có sự kiện xảy ra trong hệ thống (ví dụ: tạo mới, cập nhật, xóa), sự kiện đó được tạo ra và lưu trữ lại. Các sự kiện này thường chứa thông tin về thay đổi, như dữ liệu mới, giá trị cũ, thời gian xảy ra sự kiện, và các thông tin liên quan khác.
2. **Xây Dựng Trạng Thái Hiện Tại:**
    
    - Trạng thái hiện tại của đối tượng không được lưu trữ trực tiếp, mà được xây dựng bằng cách tái tạo từ tất cả các sự kiện đã xảy ra. Các sự kiện được áp dụng theo thứ tự để xây dựng trạng thái hiện tại của đối tượng.
3. **Tìm Kiếm và Truy Vấn:**
    
    - Khi cần truy vấn về trạng thái hiện tại của đối tượng hoặc theo dõi lịch sử thay đổi, hệ thống có thể sử dụng các sự kiện đã lưu trữ để xây dựng lại trạng thái hoặc theo dõi lịch sử.
4. **Bảo Toàn Lịch Sử:**
    
    - Mô hình Event Sourcing giúp bảo toàn toàn bộ lịch sử của đối tượng từ thời điểm bắt đầu, giúp theo dõi và kiểm soát mọi thay đổi.
5. **Khả Năng Đồng Bộ:**
    
    - Sự kiện Sourcing cung cấp khả năng đồng bộ hóa giữa các microservices hoặc các thành phần của hệ thống, bởi vì mỗi sự kiện có thể được phát sóng và xử lý độc lập.
6. **Bảo Mật và Theo Dõi:**
    
    - Bạn có thể theo dõi chi tiết mọi thay đổi xảy ra với dữ liệu và sử dụng thông tin này cho mục đích bảo mật và theo dõi.

Mô hình Event Sourcing có ưu điểm trong việc theo dõi và quản lý lịch sử thay đổi, nhưng cũng đặt ra một số thách thức, như việc quản lý cơ sở dữ liệu sự kiện và việc xử lý một lượng lớn sự kiện khi cần xây dựng lại trạng thái hiện tại.
#Design_Pattern 

# Link Azure:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/queue-based-load-leveling

Mô hình "Queue-Based Load Leveling" là một chiến lược thiết kế trong hệ thống phần mềm để giảm tải đột ngột lên các thành phần của hệ thống. Mục tiêu là làm cho tải đối với các thành phần đó trở nên ổn định hơn bằng cách sử dụng hàng đợi (queue) để làm trung gian giữa các thành phần sản xuất (producer) và tiêu thụ (consumer).

**Cách Hoạt Động:**

1. **Hàng Đợi (Queue):**
    
    - Mỗi khi một yêu cầu hoặc công việc được tạo ra (sản xuất), nó không được gửi trực tiếp đến thành phần tiêu thụ. Thay vào đó, nó được đặt vào hàng đợi.
2. **Xử Lý Từ Hàng Đợi:**
    
    - Thành phần tiêu thụ sẽ không đọc trực tiếp từ thành phần sản xuất mà sẽ đọc từ hàng đợi. Điều này giúp làm giảm tải đột ngột trên thành phần tiêu thụ.
3. **Xử Lý Dần Dần:**
    
    - Thành phần tiêu thụ có thể xử lý yêu cầu từ hàng đợi dần dần, dựa trên khả năng xử lý của nó và tình trạng hiện tại. Điều này giúp tránh tình trạng quá tải đột ngột.
4. **Ổn Định Tải:**
    
    - Dùng hàng đợi giúp giữ cho lưu lượng xử lý ổn định hơn, và nếu có đợt tăng đột ngột, yêu cầu sẽ được đặt vào hàng đợi và xử lý dần dần, giúp tránh tình trạng quá tải.
5. **Bảo toàn Dữ Liệu:**
    
    - Nếu cần thiết, các hệ thống có thể cài đặt các chiến lược để bảo toàn dữ liệu trong hàng đợi, giảm nguy cơ mất mát dữ liệu do quá tải.

**Lợi Ích và Ứng Dụng:**

- **Ổn Định Hệ Thống:** Giúp giảm tải đột ngột và làm cho hệ thống ổn định hơn.
- **Bảo toàn Tài Nguyên:** Ngăn chặn quá tải lên các thành phần của hệ thống và bảo toàn tài nguyên.
- **Quản Lý Lưu Lượng:** Hỗ trợ quản lý lưu lượng và giảm áp lực lên các thành phần quan trọng.

Mô hình Queue-Based Load Leveling thường được sử dụng trong các hệ thống xử lý dữ liệu lớn, hệ thống phân phối, và các hệ thống có đặc tính biến động về tải làm việc.
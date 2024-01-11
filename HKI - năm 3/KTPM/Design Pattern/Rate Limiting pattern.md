#Design_Pattern 

# Link Azure:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/rate-limiting-pattern

Mô hình Rate Limiting (giới hạn tốc độ) là một chiến lược được sử dụng để kiểm soát số lượng các yêu cầu hoặc sự kiện được thực hiện trong một khoảng thời gian cụ thể. Mục tiêu của mô hình này là giữ cho tỷ lệ các yêu cầu hoặc sự kiện ổn định và không vượt quá ngưỡng được xác định, nhằm đảm bảo tính ổn định và sẵn sàng của hệ thống. Các hệ thống web thường sử dụng mô hình Rate Limiting để ngăn chặn các loại tấn công như tấn công từ chối dịch vụ (DDoS) hoặc ngăn chặn việc sử dụng dịch vụ quá mức từ một nguồn đơn.

**Cách Hoạt Động:**

1. **Đặt Ngưỡng (Threshold):**
    
    - Xác định một ngưỡng hoặc một số lượng tối đa cho các yêu cầu hoặc sự kiện mà hệ thống có thể xử lý trong một khoảng thời gian nhất định.
2. **Đo Lường Tần Suất:**
    
    - Hệ thống đo lường tần suất của các yêu cầu hoặc sự kiện. Điều này có thể được thực hiện bằng cách theo dõi thời gian giữa các yêu cầu hoặc sự kiện.
3. **So Sánh với Ngưỡng:**
    
    - Khi một yêu cầu mới được nhận, hệ thống kiểm tra xem đã đạt đến ngưỡng chưa. Nếu đã vượt quá ngưỡng, yêu cầu mới có thể bị từ chối hoặc xử lý theo cách khác nhau tùy thuộc vào chiến lược cụ thể.
4. **Xử Lý Yêu Cầu:**
    
    - Nếu yêu cầu không vượt quá ngưỡng, hệ thống tiếp tục xử lý yêu cầu như bình thường. Nếu đã vượt quá, hệ thống có thể thực hiện các hành động như từ chối yêu cầu, trì hoãn xử lý, hoặc giảm độ ưu tiên.
5. **Đặt Lại Tần Suất:**
    
    - Một số hệ thống hỗ trợ việc đặt lại tần suất theo thời gian, đảm bảo rằng ngưỡng không được áp dụng vĩnh viễn và có thể thích ứng với biến động trong lưu lượng.

**Lợi Ích và Ứng Dụng:**

- **Bảo Vệ Tài Nguyên:** Giảm rủi ro từ các tấn công và bảo vệ tài nguyên của hệ thống.
- **Đảm Bảo Sẵn Sàng:** Ngăn chặn quá mức sử dụng tài nguyên và giữ cho hệ thống hoạt động mượt mà.
- **Chống DDoS:** Rate Limiting là một công cụ hiệu quả trong việc chống lại các cuộc tấn công DDoS.

Mô hình Rate Limiting đóng vai trò quan trọng trong việc quản lý và bảo vệ các hệ thống trực tuyến khỏi các rủi ro liên quan đến tải và an ninh.
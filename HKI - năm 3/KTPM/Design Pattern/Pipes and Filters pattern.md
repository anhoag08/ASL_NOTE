#Design_Pattern 

# Link Azure
*https://learn.microsoft.com/en-us/azure/architecture/patterns/pipes-and-filters

Mô hình "Pipes and Filters" là một mô hình kiến trúc phần mềm trong đó một hệ thống được chia thành một loạt các thành phần độc lập (filters) mà mỗi thành phần đảm nhận một công việc cụ thể. Các thành phần này kết hợp thông qua các ống (pipes), nơi dữ liệu được chuyển đến và từ các filters. Mô hình này giúp tạo ra một hệ thống linh hoạt và dễ mở rộng bằng cách chia nhỏ các chức năng thành các bước nhỏ, độc lập và dễ tái sử dụng.

**Cách Hoạt Động:**

1. **Filters (Bộ Lọc):**
    
    - Filters là các thành phần độc lập thực hiện các chức năng cụ thể. Mỗi filter nhận dữ liệu đầu vào, thực hiện một xử lý hoặc chức năng cụ thể, và sản xuất dữ liệu đầu ra. Filters không cần biết về sự tồn tại của nhau, điều này giúp tăng tính độc lập và tái sử dụng của chúng.
2. **Pipes (Ống):**
    
    - Pipes là các kênh thông tin giữa các filters. Chúng chịu trách nhiệm vận chuyển dữ liệu từ filter này đến filter khác. Pipes đảm bảo sự tương tác linh hoạt giữa các thành phần và cho phép chúng hoạt động cùng nhau mà không cần biết đến nhau.
3. **Luồng Dữ Liệu (Data Flow):**
    
    - Dữ liệu được truyền từ filter này đến filter khác thông qua các pipes. Mỗi filter thực hiện một bước cụ thể trong quá trình xử lý. Điều này tạo ra một luồng dữ liệu từng bước mà dữ liệu đi qua.
4. **Dễ Mở Rộng và Tái Sử Dụng:**
    
    - Do mỗi filter hoạt động độc lập và không phụ thuộc vào các thành phần khác, hệ thống có thể dễ dàng mở rộng bằng cách thêm hoặc thay thế filters mà không ảnh hưởng đến các phần còn lại. Filters có thể được sử dụng lại trong nhiều ngữ cảnh khác nhau.
5. **Khả Năng Kết Hợp:**
    
    - Filters có thể được kết hợp để tạo thành các quy trình xử lý phức tạp bằng cách sắp xếp chúng trong một chuỗi theo thứ tự mong muốn. Sự kết hợp linh hoạt này giúp tạo ra các ứng dụng phức tạp từ các thành phần nhỏ và tái sử dụng được.
6. **Quản Lý Lỗi Hiệu Quả:**
    
    - Mỗi filter có thể quản lý lỗi một cách độc lập. Điều này giúp hệ thống xử lý lỗi một cách hiệu quả, với khả năng cô lập và xử lý lỗi tại cấp độ filter cụ thể.
7. **Mô-đun và Rõ Ràng:**
    
    - Mô hình "Pipes and Filters" giúp tạo ra mô-đun và rõ ràng trong thiết kế phần mềm. Mỗi filter có thể được phát triển và kiểm thử một cách độc lập, và cấu trúc tổng thể của hệ thống trở nên dễ hiểu và bảo trì.

Mô hình "Pipes and Filters" thường được sử dụng trong các hệ thống xử lý dữ liệu, hệ thống xử lý tín hiệu, và các ứng dụng có yêu cầu về xử lý dữ liệu phức tạp mà có thể chia thành các bước đơn giản và độc lập.
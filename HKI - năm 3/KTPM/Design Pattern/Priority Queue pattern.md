#Design_Pattern 

# Link Azure:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/priority-queue

Mô hình Priority Queue là một mô hình trong lập trình và thiết kế phần mềm, nơi các yêu cầu hoặc công việc được xử lý theo độ ưu tiên của chúng. Điều này có nghĩa là các yêu cầu có độ ưu tiên cao sẽ được xử lý trước so với các yêu cầu có độ ưu tiên thấp hơn.

**Cách Hoạt Động:**

1. **Thêm Yêu Cầu:**
    
    - Các yêu cầu hoặc công việc được thêm vào hàng đợi theo độ ưu tiên của chúng. Yêu cầu có độ ưu tiên cao hơn sẽ được đặt trước trong hàng đợi.
2. **Xử Lý theo Độ Ưu Tiên:**
    
    - Khi hệ thống sẵn sàng để xử lý yêu cầu, nó sẽ lấy yêu cầu có độ ưu tiên cao nhất từ hàng đợi và bắt đầu xử lý nó.
3. **Ưu Tiên Cao Nhất Được Xử Lý Trước:**
    
    - Các yêu cầu có độ ưu tiên cao nhất sẽ luôn được xử lý trước so với những yêu cầu có độ ưu tiên thấp hơn. Điều này giúp đảm bảo rằng các công việc quan trọng hoặc cần được xử lý ngay lập tức sẽ được ưu tiên.
4. **Cập Nhật Độ Ưu Tiên:**
    
    - Trong một số trường hợp, độ ưu tiên của yêu cầu có thể thay đổi trong quá trình chờ đợi. Hệ thống có thể cập nhật độ ưu tiên của các yêu cầu để đảm bảo rằng nó vẫn tuân theo quy tắc ưu tiên mới.
5. **Áp Dụng Trong Nhiều Ngữ Cảnh:**
    
    - Mô hình Priority Queue có thể được áp dụng trong nhiều ngữ cảnh, từ hệ thống xử lý sự kiện trong lập trình đa luồng đến các tình huống quản lý tài nguyên và ưu tiên công việc trong hệ thống phân tán.
6. **Quản Lý Độ Ưu Tiên Động:**
    
    - Một số hệ thống có thể hỗ trợ quản lý độ ưu tiên động, trong đó độ ưu tiên của yêu cầu có thể thay đổi dựa trên các điều kiện thời gian thực, tình trạng hệ thống, hoặc yếu tố khác.

Mô hình Priority Queue giúp đảm bảo rằng các công việc được xử lý theo độ quan trọng của chúng, giúp tối ưu hóa hiệu suất hệ thống và đáp ứng nhanh chóng đối với các yêu cầu quan trọng.
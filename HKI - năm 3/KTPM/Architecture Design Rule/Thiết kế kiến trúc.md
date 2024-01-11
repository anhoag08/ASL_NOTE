#Design_Pattern 

- Phân rã
- Thiết kế để thỏa mãn các yêu cầu quan trọng (ASR)
- Thiết kế và kiểm tra (Generate and Test)

# ADD
- Attribute-Driven Design là một phương thức lặp dùng để thiết kế kiến trúc

![[Pasted image 20240111122534.png|500]]

Attribute-Driven Design (ADD) là một phương pháp thiết kế kiến trúc phần mềm tập trung vào việc xác định và quản lý các thuộc tính chất lượng của hệ thống. Phương pháp này được phát triển để đảm bảo rằng kiến trúc của hệ thống đáp ứng đúng các yêu cầu về chất lượng từ người dùng và bên ngoài hệ thống. Dưới đây là mô tả về cách Attribute-Driven Design hoạt động:

1. **Xác Định Yêu Cầu Chất Lượng:**
    
    - Bắt đầu với việc xác định và hiểu rõ các yêu cầu chất lượng của hệ thống. Các yêu cầu này có thể bao gồm hiệu suất, độ tin cậy, bảo mật, mở rộng, bảo trì, và các thuộc tính chất lượng khác.
2. **Phân Tích và Ưu Tiên Thuộc Tính Chất Lượng:**
    
    - Phân tích các yêu cầu chất lượng và xác định sự ưu tiên của chúng. Điều này có thể bao gồm việc xác định thuộc tính chất lượng quan trọng hơn và các mức độ ưu tiên giữa chúng.
3. **Xây Dựng Kiến Trúc Sơ Bộ:**
    
    - Dựa trên thông tin về yêu cầu chất lượng, xây dựng một kiến trúc sơ bộ cho hệ thống. Kiến trúc này có thể là một tập hợp các khối chức năng, giao tiếp giữa chúng, và các quyết định kiến trúc sơ bộ.
4. **Liên Kết Thuộc Tính Chất Lượng với Kiến Trúc:**
    
    - Gắn kết các yêu cầu chất lượng với các phần của kiến trúc sơ bộ. Điều này đồng nghĩa với việc quyết định làm thế nào mỗi thuộc tính chất lượng sẽ được đảm bảo và duy trì trong kiến trúc.
5. **Kiểm Soát và Tối Ưu Hóa:**
    
    - Kiểm soát và theo dõi việc triển khai kiến trúc để đảm bảo rằng các thuộc tính chất lượng được duy trì. Đồng thời, tiến hành tối ưu hóa kiến trúc khi cần thiết để đáp ứng yêu cầu và thay đổi mới.
6. **Lặp Lại Quá Trình:**
    
    - Các bước trên được lặp lại và điều chỉnh khi có thêm thông tin hoặc yêu cầu mới về chất lượng xuất hiện.

Attribute-Driven Design là một phương pháp linh hoạt, tập trung vào các yêu cầu chất lượng và định hình kiến trúc dựa trên chúng. Nó giúp đảm bảo rằng kiến trúc phản ánh đúng các ưu tiên và mong muốn của bên dùng đối với hệ thống.
# Phương pháp của Microsoft
- Application Architecture Guide
- ## Đầu vào
	- Các ca sử dụng
	- Yêu cầu phi chức năng
	- Các ràng buộc
- ## Các bước chính
	- B1: Tìm mục đích của kiến trúc
	- B2: Xác định các hoạt cảnh chính
	- B3: Xác định ứng dụng loại gì ?
	- B4: Xác định các vấn đề chính

•Identify Architecture Objectives. Đưa ra mục tiêu một cách chi tiết từ đầu giúp cho chúng ta tập trung vào kiến trúc và xử lý đúng vấn đề, và biết được lúc nào sẽ hoàn thành một pha để chuyển sang pha tiếp theo

•Key Scenarios. Sử dụng các hoạt cảnh chính sẽ giúp cho chúng ta tập trung thiết kế vào các vấn đề chính và đánh giá các ứng viên khi có các bản thiết kế

•Application Overview. Xác định loại ứng dụng, ràng buộc trong triển khai, kiểu kiến trúc, và các công nghệ giúp liên kết giữa kiến trúc được thiết kế với thế giới thực, nơi hệ thống sẽ hoạt động

•Key Issues. Các vấn đề chính được xác định thông qua thuộc tính chất lượng và các khía cạnh quan tâm.

•Candidate Solutions. Tạo ra bản mẫu của kiến trúc và đánh giá dựa trên các hoạt cảnh sử dụng chính, các vấn đề chính, các ràng buộc triển khai trước khi bước sang vòng lặp tiếp theo.
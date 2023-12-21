#Design_Pattern 
Định nghĩa:
- Tách một tin nhắn lớn thành một tham chiếu, key và lưu trữ payload ở một dịch vụ ngoài. Sau đó gửi tham chiếu và key tới dịch vụ nhắn tin. Pattern này cho phép các tin nhắn khối lượng lớn có thể được xử lý, trong khi đảm bảo tính bảo mật cho tin nhắn và giữ cho dịch vụ xử lý không bị quá tải hoặc làm chậm. Pattern này giảm chi phí, do việc lưu trữ được thực hiện ở bên ngoài dịch vụ nhắn tin.

Cách hoạt động:
- Gửi một tham chiếu và key tới dịch vụ nhắn tin và lưu trữ tin nhắn ở một dịch vụ lưu trữ, dịch vụ nhắn tin sẽ sử dụng tham chiếu để truy cập, xử lý tin nhắn và tải tin nhắn về, nếu cần thiết

![[Pasted image 20230930111429.png]]


Khi nào thì sử dụng pattern này:
- Sử dụng khi tin nhắn vượt quá khả năng hỗ trợ của dịch vụ nhắn tin.
- Sử dụng khi tin nhắn chỉ có thể được truy cập bởi một dịch vụ có sở hữu key đến tin nhắn đấy. Nhằm đảm bảo tính bảo mật cho tin nhắn
  
  
Ưu điểm:
- Tối ưu hóa hiệu suất truyền tải mạng: Do chỉ chuyển key claim-check chứ không chuyển cả tin nhắn
- Tiết kiệm tài nguyên: Không sử dụng tài nguyên của service để lưu trữ tin nhắn
- Tích hợp dễ dàng vào các hệ thống.

Nhược điểm
- chỉ dùng có hiệu quả với tin nhắn lớn vượt quá giới hạn dữ liệu của bus tin nhắn còn gây độ trễ đv tin ngắn Có thể cần xoá tin nhắn sau 1 t/g cho đỡ tốn bộ nhớ vì nhận toàn tin nhắn dài và tốn tiền mua lưu trữ->ko đồng bộ xoá đc tin nhắn
- Quá trình lưu trữ tin nhắn và xử lý sau khi nhận được key sẽ tăng độ trễ vào quá trình xử lý
- Yêu cầu truy cập bên thứ 3 để lưu trữ tin nhắn.
- Tăng tính phức tạp cho dịch vụ nhắn tin do phải xử lý tham chiếu


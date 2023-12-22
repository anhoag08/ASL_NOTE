#Design_Pattern 

# Azure Architecture Link:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/throttling

# Định nghĩa
- Kiểm soát lượng tài nguyên sử dụng của một người dùng, dịch vụ hoặc cả hệ thống nhằm cho phép ứng dụng không gặp lỗi và đáp ứng yêu cầu chức năng

# Bài toán
- Khối lượng công việc của ứng dụng đám mây thường sẽ biến thiên theo thời gian dựa trên số lượng người sử dụng đang hoạt động hoặc dựa và các hoạt động mà họ đang thực hiện. Ví dụ, nhiều người dùng thường hoạt động trong giờ hành chính, hoặc hệ thống sẽ phải thực hiện các tính toán đắt đỏ và cuối mỗi tháng. Có thể sẽ có các sự tăng đột biến về hoạt động trong hệ thống. Nếu yêu cầu xử lý của hệ thống vượt mức tài nguyên có thể đáp ứng, hệ thống sẽ hoạt động chậm và có thể gặp lỗi. Nếu hệ thống cần phải đáp ứng được một mức độ dịch vụ nào đó, cần phòng ngừa các lỗi đó.

# Giải pháp
- Một giải pháp thay thế cho autoscaling là cho phép các ứng dụng sử dụng tài nguyên đến một giới hạn, sau đó giới hạn (throttle) ứng dụng đó. Hệ thống sẽ theo dõi lượng tài nguyên ứng dụng sử dụng, để khi lượng sử dụng vượt quá giới hạn, hệ thống sẽ giới hạn (throttle) lượng yêu cầu từ một hoặc nhiều người dùng. Điều này cho phép hệ thống tiếp tục hoạt động và đáp ứng yêu cầu chức năng cho trước

- Hệ thống có thể áp dụng một vài chiến thuật giới hạn (throttle) như sau:
	- Từ chối yêu cầu từ người dùng đã truy cập API của hệ thống nhiều hơn n lần trong một khoảng thời gian. Cách này yêu cầu hệ thống phải ghi lại lượng tài nguyên sử dụng của mỗi người dùng của ứng dụng
	- Dừng hoặc làm giảm chất lượng chức năng của các dịch vụ không thiết yếu để các dịch vụ thiết yếu có thể chạy với lượng tài nguyên cần thiết. Ví dụ: Ứng dụng stream video, giảm độ phân giải của video
	- Sử dụng phương pháp cân bằng tải để làm mịn khối lượng hoạt động. Trong một môi trường đa người sử dụng, phương pháp này sẽ giảm hiệu suất cho mỗi người sử dụng.
	- Từ chối hoặc giới hạn các yêu cầu từ các ứng dụng hoặc người dùng có ưu tiên thấp.

- Hình dưới minh họa việc giới hạn lượng tài nguyên sử dụng cho 3 dịch vụ A, B, C![[Pasted image 20231222162627.png|500]]
- Ở đây, tại T1, lượng tài nguyên sử dụng của 3 ứng dụng vượt ngưỡng giới hạn, ứng dụng B có độ ưu tiên thấp nên bị dừng để dồn tài nguyên cho ứng dụng A, C. Ở T2, lượng tài nguyên quay lại đủ cho B được thực hiện lại

- Hình tiếp cho ta thấy việc dùng giới hạn kết hợp với autoscaling để cho ứng dụng linh động với lượng tài nguyên yêu cầu.![[Pasted image 20231222163116.png|500]]
- Ở đây ta thấy, tại T1, lượng tài nguyên vượt ngưỡng giới hạn, hệ thống kích hoạt autoscaling tăng lượng tài nguyên để phù hợp với yêu cầu. Trong lúc autoscaling được thực hiện, hệ thống được giới hạn để không vượt quá giới hạn và gặp lỗi. Ở T2, việc autoscaling được thực hiện xong, hệ thống dừng việc giới hạn và hoạt động bình thường trở lại.

# Vấn đề
- Thiết kế giới hạn hệ thống và các chiến thuật cần được thiết kế từ rất sớm trong khâu thiết kế ứng dụng.
- Việc giới hạn cần được thực hiện nhanh chóng, đồng thời hệ thống cần có thể chuyển về trạng thái bình thường nhanh chóng khi đã đủ tài nguyên

# Khi nào sử dụng pattern này
- Khi cần đảm bảo một hệ thống cần đáp ứng một mức độ chức năng nào đó
- Ngăn ngừa một dịch vụ độc chiếm toàn bộ tài nguyên của hệ thống
- Xử lý sự tăng bất ngờ trong sử dụng hệ thống
- Tối ưu giá thành cho hệ thống bằng cách giới hạn tài nguyên tối đa mà hệ thống có thể sử dụng
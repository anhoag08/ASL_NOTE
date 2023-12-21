# Các mức độ kiểm thử
- Unit
- Integration
- System
- Acceptance

# Vì sao cần kiểm thử tích hợp
- Một trong các lỗi phổ biến là interface error là cơ chế cho phép 2 module giao tiếp với nhau
- Các đơn vị chương trình thường phát triển bởi các dev khác nhau

# Hướng tiếp cận
- Big bang
- Incremental
- Sandwich

# Big-bang
- Đầu tiên các module được unit testing
- Sau đó được tích hợp và kiểm thử toàn hệ thống
- Trong một vài trường hợp Big-bang được áp dụng để tích hợp và kiểm thử hệ thống nhỏ
- Tuy nhiên chỉ phù hợp với hệ thống nhỏ do phải cần hết tất cả các module để kiểm thử.

# Incremental
- Kiểm thử tích hợp theo các chu kỳ tăng dần
- Chu kỳ sau bổ sung tích hợp các đơn vị mới vào kiểm thử cùng các đơn vị đã kiểm thử ở chu kỳ trước.

	## **Top down**
	- Sử dụng stubs
	- ![[Pasted image 20231026163001.png]]

	## **Bottom up**
	- Sử dụng driver
	- ![[Pasted image 20231026163033.png]]

# Sandwich
- Kết hợp cả Bottom up và Top down
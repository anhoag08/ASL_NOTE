

# Các dạng thay đổi phần mềm
- Điều chỉnh
- Thích ứng
- Tối ưu
- Bảo mật

# Kiểm thử hồi quy
- Sử dụng lại tests một cách hiệu quả khi kiểm tra các thay đổi
	- Kiểm thử chọn lọc: Chỉ thực thi các tests ảnh hưởng bởi sự thay đổi
	- Kiểm thử có tính ưu tiên: Sắp xếp các tests để nhanh chóng phát hiện lỗi
	- Giảm thiểu kiểm thử: Loại bỏ các test dư thừa

# Kiểm thử có chọn lọc (RTS)
- Nhằm mục đích tăng tốc độ kiểm thử hồi quy bằng cách chỉ chạy lại các kiểm thử bị ảnh hưởng bở thay đổi mã nguồn
- Kỹ thuật RTS là an toàn nếu chọn tất cả các tests có hành vì có thể bị ảnh hưởng bởi thay đổi mã nguồn

Cạnh nguy hiểm : Cạnh đi vào một dòng lệnh thay đổi

![[Pasted image 20231021132539.png]]
![[Pasted image 20231021132551.png]]

# Kiểm thử có tính ưu tiên
- Sắp xếp lại thứ tự ưu tiên của việc thực thi nhằm tối đa một số mục tiêu
	- Thường tối đa khả năng tìm lỗi của bộ test
Với m lỗi và n test, ta có tỉ lệ phát hiện được lỗi bằng:

![[Pasted image 20231021133402.png]]

TFi : Test đầu tiên phát hiện ra lỗi thứ i

- Phương pháp tổng: Chọn test phủ nhiều đơn vị nhất là test được thực thi kế tiếp
- Phương pháp bù: Chọn test phủ nhiều đơn vị chưa phủ nhất là test được thực thi kế tiếp
- 
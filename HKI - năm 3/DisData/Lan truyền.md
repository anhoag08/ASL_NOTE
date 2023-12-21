# Phân loại theo thời gian lan truyền cập nhật
- Tích cực
- Lười biếng

# Phân loại theo nơi phát sinh cập nhật
- Trung tâm hóa
	- Single master: Chỉ có một site cho mọi đối tượng dữ liệu
	- Primary copy: Có thể có các site master khác nhau cho mỗi đối tượng dữ liệu logic
	- Ưu điểm:
		- Dễ cập nhật
		- Luôn xác định ít nhất 1 site có dữ liệu up-to-date
	- Nhược điểm:
		- Single master: Quá tải
		- Primary copy: Khó cập nhật
- Phân tán
	- Phát sinh từ bất kỳ trạm nào
	- Ưu điểm:
		- Dễ dàng cập nhật
		- Giảm tải
	- Nhược điểm:
		- Tương tranh

# Giao thức

		

=> Tồn tại 4 chiến lược ( tổ hợp giữa thời gian và nơi phát sinh cập nhật )





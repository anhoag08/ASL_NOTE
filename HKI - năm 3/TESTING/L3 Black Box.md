
Các phương pháp:

- Kiểm thử vét cạn: Kiểm thử hết các TH (Dùng khi miền input giới hạn).

- Kiểm thử ngẫu nhiên - monkey testing: Sử dụng lý thuyết Xác suất sampling (nếu 1000 test fail với tỉ lệ 1% thì độ tự tin là 99%)
	- Tăng khả năng bao phủ của sinh test ngẫu nhiên bằng kỹ thuật kiểm thử ngẫu nhiên thích ứng.
		- Với 1 bộ test T và các ứng viên C
		- Khoảng cách từ C -> T là khoảng cách từ C đến test gần C nhất.
		- Lựa chọn C có khoảng cách đến T xa nhất.
Kiểm thử tổ hợp có trong bài thi.


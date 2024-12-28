#LabTesting
k dc dat ten bien la empty
u1 v1 & (u2 v2 | u3 v2)
cùng loc khác val
cùng val khác loc (tạo obj map)
Tạo key cho từng dòng expr trong template
xử lý lại bộ hoặc
sastisfy all bug

Research Resources
https://tkbb.uet.vnu.edu.vn/
http://lib.uet.vnu.edu.vn/


Tổng kết buổi họp
- Cần tạo UI trực quan cho người dùng:
	- Tạo mock web cho người dùng nhập Test Data
	- Tạo stand alone IDE cho thao tác nhập Test Script
	- Tạo button GUI cho các hoạt động của người dùng (Sinh resources, sinh test case)

- Liên kết và tự động hóa các workflow:
	- Tự động chuyển giao data giữa các phần tử (chuyển template từ MPS về Java).
	- Chuyển Data từ mock Web về chương trình.

- Hoàn thiện các chức năng cho chương trình (Invalid, các hành động khác ngoài SendText và Click)
	- Long Click
	- Double Click
	- Drag And Drop
	- Select All From List
	- Condition (If else)
	- Loop (For, While)

- Tạo test cho các trang web thực tế, kiểm thử qua nhiều chức năng của chương trình và kiểm tra performance của chương trình
	- Kiểm thử cho nhiều bước chuyển web
	- Kiểm thử cho nhiều chức năng

- Deadline hoàn thiện demo: 2 tháng

- Công việc cá nhân : Hoàn thiện phần Invalid cho workflow MPS

- Câu hỏi:
- Biểu đồ thành phần

Json object
json list thay data nhưng không thay locator
nếu toàn action tĩnh thì data index là -1\


Reviewer A:
- Viết quá trình sinh test dưới dạng thuật toán (psuedo code).
- Các hình ảnh mô tả quá trình sinh test nên sử dụng context thực tế i.e. Hình 5,6 (Thay đổi hình 2, 3).
- Cần thêm bối cảnh và các website khác cho phần đánh giá.
- Tìm cách so sánh thời gian sinh test hợp lý hơn giữa Katalon Studio và tool.
- Hình 9, 10 cần giải thích ý nghĩa màu sắc trong hình.

Reviewer B:
- Phân tích thêm điểm mạnh, điểm yếu về tính thực tiễn khi sử dụng UBL
- Phần thí nghiệm và đánh giá cần thêm thông tin để giải thích kết luận tốt hơn.
- Thêm phần tool support để giúp người đọc reproduce thí nghiệm.
- Định nghĩa giới hạn của UBL trong thí nghiệm.
- Kỹ thuật hỗ trợ cho tạo UBL và sinh test cần miêu tả chi tiết => Vấn đề trong việc hiểu quá trình kiểm tra tính đúng đắn của UBL (syntax).
- Thêm thí nghiệm và kết quả để tăng tính thuyết phục cho kết luận
- Format:
	- Phần intro thiếu giới thiệu cho section 5.
	- Terminology dùng trong bài còn inconsistent
- Xử lý lỗi trong UBL
	- syntax
	- sai hành động
	- sai phép toán logic
	- Constraint sử dụng trong tính toán số test case.
- Cụ thể hơn trong so sánh giữa Katalon và tool:
	- Khả năng ứng dụng thực tế (các hành động support, ...)
	- Formal definition cho UBL scope
	- Kết hơp so sánh thời gian tạo ra bộ script UBL cho tool với các phương pháp tạo test khác nhau của Katalon (Record and play, ...)

Mục tiêu chính:
- Viết formal algorithm cho quá trình sinh test.
- Consistence trong định nghĩa các hành động
- Cải thiện phần thực nghiệm và so sánh kết quả
- Miêu tả thêm các kịch bản thực tế.

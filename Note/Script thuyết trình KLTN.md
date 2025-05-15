# Slide 1
Xin kính chào các thầy cô trong hội đồng, em tên là Phạm Hoàng Ân, em xin trình bày về đề tài KLTN GIẢI PHÁP TĂNG ĐỘ PHỦ CHO BỘ KIỂM THỬ ĐƯỢC SINH TỰ ĐỘNG CHO KIỂM THỬ GIAO DIỆN WEB được thực hiện dưới sự hướng dẫn của thầy Lê Khánh Trình

# Slide 2
Nội dung bài trình bày của em gồm 4 phần: Giới thiệu, Giải pháp, Thực nghiệm, Kết luận

# Slide 3
Hiện nay, trong quá trình phát triển phần mềm, kiểm thử giao diện đóng một vai trò thiết yếu. Tuy nhiên còn công ty vẫn sử dụng kiểm thử thủ công, dẫn đến tốn kém về nhân công và chi phí, chất lượng các bộ kiểm thử phụ thuộc vào kiến thức của kiểm thử viên và dễ bỏ sót các trường hợp khó.

Đồng thời, các giải pháp hiện tại cho kiểm thử giao diện tự động còn nhiều hạn chế, Record & Play phụ thuộc vào kỹ năng của kiểm thử viên để viết được kịch bản kiểm thử hiệu quả và khó khăn với các ca kiểm thử dùng nhiều bộ dữ liệu khác nhau. Giải pháp kiểm thử dựa trên mô hình các trạng thái của giao diện thường dẫn đến sinh các ca kiểm thử thừa trong nỗ lực bao quát hết các trường hợp.

Từ đó dẫn đến nhu cầu cho một giải pháp giúp làm giảm yêu cầu kỹ thuật cho kiểm thử viên và giúp tự động hóa việc bao quát các trường hợp khi sinh kịch bản kiểm thử.

Giải pháp được đề tài đề xuất là phát triển một ngôn ngữ miền chuyên biệt cho kiểm thử giao diện để giảm rào cản kỹ thuật và sử dụng phương pháp kiểm thử bất thường và sinh ca kiểm thử tự động để tăng độ phủ cho bộ kiểm thử được sinh ra.

# Slide 4
Phương pháp đề xuất sử dụng một ngôn ngữ miền chuyên biệt đặt tên là User Behavior Language viết tắt là UBL được thiết kế để có tính trừu tượng cao.

Một kịch bản kiểm thử sẽ bao gồm một hoặc nhiều chuỗi lệnh. Một chuỗi lệnh sẽ bao gồm một hoặc nhiều lệnh. Một lệnh sẽ mô tả một hành động cụ thể của người dùng trên giao diện và bao gồm 2 thành phần là hành động và mô tả phần tử.

Một chuỗi lệnh còn có thể không có hoặc chứa nhiều ràng buộc. Các ràng buộc được biểu diễn dưới dạng phép toán logic AND hoặc OR và được sử dụng để liên kết các lệnh với nhau.

Hiện tại UBL hỗ trợ 6 hành động

# Slide 5
Về hệ thống sinh kịch bản kiểm thử bất thường, kiến trúc tổng quan của hệ thống như sau, hệ thống gồm 3 module chính là module tiền xử lý dữ liệu, module xử lý phép toán logic và module sinh ca kiểm thử bất thường.

Luồng hoạt động của hệ thống như sau, khi nhận được yêu cầu sinh ca kiểm thử từ chương trình chính, bộ điều khiển gửi yêu cầu tiền xử lý tới module tiền xử lý dữ liệu. Module tiền xử lý dữ liệu nhận đầu vào từ file script.json và tiến hành lưu dữ liệu của các lệnh và dữ liệu kiểm thử vào các HashMap. Khi module tiền xử lý dữ liệu nhận được các phép toán logic về ràng buộc lệnh thì sẽ tiến hành gửi yêu cầu xử lý logic tới module xử lý phép toán logic. Module xử lý logic tiến hành tính toán truth table về các trường hợp đúng sai của biểu thức logic và trả về để module tiền xử lý dữ liệu lưu lại.

Sau khi xử lý dữ liệu hoàn thành, bộ điều khiển gửi yêu cầu sinh ca kiểm thử đến module sinh ca kiểm thử bất thường. Module sinh ca kiểm thử bất thường tiến hành truy vấn dữ liệu về kịch bản và dữ liệu kiểm thử và sinh ca kiểm thử và viết ra file đầu ra.

# Slide 6
Module sinh ca kiểm thử bất thường sử dụng phương pháp kiểm thử bất thường. Phương pháp tiến hành cô lập một bộ phận của kịch bản, giả lập lỗi trong phần cô lập và kiểm tra phản hồi của giao diện. Ví dụ

# Slide 7
Ở thực nghiệm đầu tiên, 

# Slide 8
Em xin cảm ơn ban giám khảo các thầy cô và mọi người đã lắng nghe.
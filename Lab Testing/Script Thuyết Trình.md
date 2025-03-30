# Slide 1
Xin kính chào ban giám khảo và các thầy cô, em tên là Phạm Hoàng Ân, em xin đại diện cho nhóm trình bày về dự án AutUI - Công cụ hỗ trợ sinh kịch bản kiểm thử cho giao diện web.

# Slide 2
Nội dung chúng em gồm 4 phần: Giới thiệu, Giải pháp, Ưu điểm nhược điểm, Hướng đi tương lai

# Slide 3
Hiện nay, trong quá trình phát triển phần mềm, kiểm thử giao diện đóng một vai trò thiết yếu. Tuy nhiên còn công ty vẫn sử dụng kiểm thử thủ công, dẫn đến tốn kém về nhân công và chi phí, chất lượng các bộ kiểm thử phụ thuộc vào kiến thức của kiểm thử viên và dễ bỏ sót các trường hợp khó.

Đồng thời, các giải pháp hiện tại cho kiểm thử giao diện tự động còn nhiều hạn chế, Record & Play phụ thuộc vào kỹ năng của kiểm thử viên để viết được kịch bản kiểm thử hiệu quả và khó khăn với các ca kiểm thử dùng nhiều bộ dữ liệu khác nhau. Giải pháp kiểm thử dựa trên mô hình các trạng thái của giao diện thường dẫn đến sinh các ca kiểm thử thừa trong nỗ lực bao quát hết các trường hợp.

Từ đó dẫn đến nhu cầu cho một giải pháp giúp làm giảm yêu cầu kỹ thuật cho kiểm thử viên và giúp tự động hóa việc bao quát các trường hợp khi sinh kịch bản kiểm thử.

# Slide 4
Giải pháp chúng em đề xuất là AutUI - Công cụ hỗ trợ sinh kịch bản kiểm thử cho giao diện web. Các huóng giải quyết của nhóm em cho các nhu cầu đã nêu là:

Ngôn ngũ chuyên biệt gần với ngôn ngữ tự nhiên giúp kiểm thử viên dễ dàng mô tả kịch bản kiểm thử mà không phải học syntax.

Tự động sinh kịch bản kiểm thử từ ảnh giao diện và mô tả giúp gợi ý cho kiểm thử viên hướng tiếp cận kịch bản kiểm thử

Xác định phần tử web tự động giúp giảm yêu cầu kỹ thuật cho kiểm thử viên

Kiểm thử bất thường, kiểm thử phản hồi của hệ thống khi nhận các đầu vào bất thường giúp tăng chất lượng ca kiểm thử được sinh ra

# Slide 5
Luồng hoạt động của hệ thống như sau:

Bước đầu người dùng sẽ tạo kịch bản kiểm thử sử dụng DSL có tên User Behavior Language viết tắt là UBL. UBL sẽ có dạng gần ngôn ngữ tự nhiên giúp làm giảm yêu cầu kỹ thuật với người dùng

Sau đó, hệ thống sẽ hỗ trợ người dùng tạo kịch bản kiểm thử. Ở bước này, kịch bản kiểm thử sẽ được chuyển thành tập lệnh chi tiết chứa các thông tin về hành động và ràng buộc.

Ở bước thứ ba hệ thống sẽ xác định vị trí của các phần tử web sử dụng XPath một cách tự động

Sau đó hệ thống sẽ sinh các ca kiểm thử dựa trên kịch bản, dữ liệu người dùng và vị trí phần tử. Hệ thống sẽ sinh luồng hợp lệ để kiểm tra luồng cơ bản của kiểm thử viên định nghĩa và sinh luồng bất thường để kiểm tra phản hồi của hệ thống khi nhận các dữ liệu không hợp lệ.

Cuối cùng, hệ thống sẽ thực thi bộ kiểm thử và ghi lại kết quả và trả lại báo cáo cho người dùng.

# Slide 6
Hệ thống có khả năng giảm sự phụ thuộc của quá trình kiểm thử vào trình độ của kiểm thử viên
Sử dụng kiểm thử bất thường để tăng độ phủ cho ca kiểm thử
Giảm tác động của thay đổi source HTML tới bộ kiểm thử, tăng tính tái sử dụng

Tuy nhiên giải pháp còn tồn tại một vài hạn chế
Gặp khó khăn khi xử lý Single Page Apps
DSL chưa hỗ trợ các chức năng nâng cao lưu biến, lặp, điều kiện
Chưa tích hợp xử lý NLP để nhận diện các từ đồng nghĩa trong mô tả người dùng

# Slide 7
Trong tương lai, nhóm muốn cải tiến để hệ thống xử lý được các trang web single page apps
xử lý NLP
Fuzzing để tự động sinh dữ liệu kiểm thử

Đồng thời hợp tác với các doanh nghiệp để đưa giải pháp tới các dự án thực tế
Cải thiện khả năng chia sẻ bộ kiểm thử giữa các kiểm thử viên
Cải thiện báo cáo chạy script, capture bước chạy, capture lỗi

# Slide 8
Em xin cảm ơn ban giám khảo các thầy cô và mọi người đã lắng nghe.
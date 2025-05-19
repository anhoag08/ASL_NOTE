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
Tổng quan luồng hoạt động hệ thống như sau:
Đầu tiên người dùng sử dụng ngôn ngữ UBL để mô tả kịch bản kiểm thử mong muốn
Sau đó, kịch bản kiểm thử sẽ được hệ thống chuyển thành các tập lệnh chứa thông tin về hành động và ràng buộc
Ở bước 3, từ các mô tả phần tử, hệ thống tiến hành xác định vị trí phần tử tự động
Sau khi đã có vị trí phần tử và dữ liệu kiểm thử, hệ thống tiến hành sinh ca kiểm thử, bao gồm luồng hợp lệ và bất thường
Cuối cùng, hệ thống thực thi ca kiểm thử được sinh ra.

Em xin trình bày đóng góp của em trong hệ thống, bao gồm thiết kế ngôn ngữ miền chuyên biệt và hệ thống sinh ca kiểm thử bất thường.

# Slide 5
Phương pháp đề xuất sử dụng một ngôn ngữ miền chuyên biệt đặt tên là User Behavior Language viết tắt là UBL được thiết kế để có tính trừu tượng cao.

Một kịch bản kiểm thử sẽ bao gồm một hoặc nhiều chuỗi lệnh. Một chuỗi lệnh sẽ bao gồm một hoặc nhiều lệnh. Một lệnh sẽ mô tả một hành động cụ thể của người dùng trên giao diện và bao gồm 2 thành phần là hành động và mô tả phần tử.

Một chuỗi lệnh còn có thể không có hoặc chứa nhiều ràng buộc. Các ràng buộc được biểu diễn dưới dạng phép toán logic AND hoặc OR và được sử dụng để liên kết các lệnh với nhau.

Hiện tại UBL hỗ trợ 6 hành động

# Slide 6
Về hệ thống sinh kịch bản kiểm thử bất thường, kiến trúc tổng quan của hệ thống như sau, hệ thống gồm 3 module chính là module tiền xử lý dữ liệu, module xử lý phép toán logic và module sinh ca kiểm thử bất thường.

Tiền xử lý dữ liệu: Nhận dữ liệu đầu vào dạng .json và lưu vào các mảng.
Xử lý phép toán logic: Nhận các biểu thức logic, chuyển về dạng DNF và tính toán truth table.
Sinh kịch bản kiểm thử: Từ dữ liệu đã được tiền xử lý, sinh các ca kiểm thử bất thường.

# Slide 7
Module sinh ca kiểm thử bất thường sử dụng phương pháp kiểm thử bất thường. Phương pháp tiến hành cô lập một khối thực thi của kịch bản, giả lập lỗi trong phần cô lập và kiểm tra phản hồi của giao diện. Một khối thực thi sẽ bao gồm các dòng lệnh và dòng kiểm tra ở cuối. Trong ví dụ này, khi cô lập khối thực thi, các dòng lệnh trước khối thực thi sẽ được thay bằng dữ liệu hợp lệ, các dòng hành động sau khối thực thi bị loại bỏ, đảm bảo nếu ca kiểm thử xảy ra lỗi sẽ do các lệnh trong khối cô lập gây ra.

Về công thức tính toán số ca kiểm thử sinh ra, số ca kiểm thử được sinh ra bằng tổng số trường hợp hợp lệ nhân tổng số trường hợp bất thường nhân số bộ dữ liệu đầu vào.

# Slide 8
Ví dụ, ở trong kịch bản sau, khi cô lập khối thực thi gồm dòng 3, 4, dòng 1, 2 được thay dữ liệu hợp lệ và sinh được 3 trường hợp hợp lệ, dòng 3, 4 được thay dữ liệu bất thường và sinh ra 3 trường hợp bất thường, số ca kiểm thử là 3 x 3 = 9 x 2 bộ dữ liệu là 18 ca kiểm thử được sinh ra.

# Slide 9
Về thực nghiệm đầu tiên, hệ thống được thực nghiệm trên website Saucedemo, một website benchmark e-commerce cho phép giả lập nhiều luồng hành động người dùng.
Phương pháp đề xuất sẽ được so sánh với Playwright, một giải pháp kiểm thử tự động theo dạng Record & Play
Các thông số được quan tâm là thời gian sinh ca kiểm thử và thời gian sinh ca kiểm thử.

# Slide 10
Kịch bản được thực nghiệm bao gồm người dùng truy cập vào trang web, đăng nhập, kiểm tra địa chỉ trang chủ, tiến hành thêm sản phẩm vào giỏ hàng, kiểm tra xem sản phẩm đã được thêm thành công vào giỏ hàng hay không.

Từ kịch bản trên, sau khi được mô tả sử dụng UBL sẽ có dạng sau và có 2 khối thực thi cần được cô lập.

# Slide 11
Khối thực thi đầu tiên có 3 dòng hành động, sau khi sinh các trường hợp bất thường thu được 4 trường hợp

# Slide 12
Khối thực thi thứ 2 có 2 dòng hành động, khối thực thi 1 sau khi được thay dữ liệu hợp lệ sinh ra 1 trường hợp, khối thực thi 2 khi sinh các trường hợp bất thường sinh được 2 trường hợp, số ca kiểm thử được sinh ra là 2 + 4 = 6, nhân 2 bộ dữ liệu thu được 12 ca kiểm thử.

# Slide 13
Kết quả thực nghiệm như sau:
Phương pháp đề xuất có thời gian sinh ca kiểm thử nhanh hơn so với Playwright, 243s so với 412s, điều này do phương pháp đề xuất sinh 12 ca kiểm thử từ 1 kịch bản, còn Playwright phải ghi lại thủ công từng ca kiểm thử một và thay dữ liệu.

Phương pháp đề xuất có thời gian thực thi ca kiểm thử lâu hơn so với Playwright, 55s so với 37s, điều này do Playwright là một test runner được xây dựng để tối ưu thời gian thực thi, giải pháp đề xuất chỉ có thể sinh ra các ngôn ngữ hiện có và không thể tối ưu các lệnh được sinh ra.

# Slide 14
Về thực nghiệm 2:
Phương pháp đề xuất được khảo sát với các kiểm thử viên chưa có nhiều kinh nghiệm lập trình.
Các kiểm thử viên tiến hành chọn một luồng hành động và thực hiện mô tả sử dụng UBL
Thông số cần quan tâm:
Độ chính xác
Thời gian chạy trung bình

# Slide 15
Kết quả thực nghiệm như sau:
Phương pháp đề xuất cho phép các kiểm thử viên mô tả luồng hành động với độ chính xác cao từ 71 đến 87.5%
Thời gian thực thi kiểm thử trong các môi trường khác nhau giao động trong khoảng 6-11s, cho thấy thời gian thực thi phương pháp tương đối ổn định qua các điều kiện phần cứng khác nhau.

# Slide 16
Kết luận:
Hệ thống thành công trong việc giảm sự phụ thuộc của quá trình kiểm thử vào trình độ của kiểm thử viên
Có khả năng sinh ca kiểm thử tự động các trường hợp bất thường, tăng độ phủ và chất lượng ca kiểm thử

Tuy nhiên, hệ thống còn vài hạn chế DSL chưa hỗ trợ các tính năng nâng cao biến, vòng lặp, điều kiện.
Sinh dữ liệu bất thường chưa thể thích ứng với các loại trang web, phần tử khác nhau.

Hướng phát triển tương lai bao gồm cải thiện cơ chế sinh dữ liệu không hợp lệ sử dụng kỹ thuật fuzzing và loại bỏ yêu cầu syntax cho UBL, hướng đến tạo kịch bản kiểm thử sử dụng ngôn ngữ tự nhiên.

# Slide 17
Cảm ơn quý thầy cô đã chú ý lắng nghe.
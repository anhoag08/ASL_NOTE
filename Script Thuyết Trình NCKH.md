# Slide 1
- Kính thưa hội đồng, em tên là Phạm Hoàng Ân, đại diện cho nhóm trình bày báo cáo nghiên cứu khoa học về đề tài AutUI - Công cụ hỗ trợ sinh kịch bản kiểm thử giao diện ứng dụng web. Nhóm chúng em đã thực hiện nghiên cứu này với sự hướng dẫn của thầy Lê Khánh Trình. Sau đây, em xin trình bày nội dung báo cáo.

# Slide 2
- Bài báo cáo của chúng em bao gồm 4 phần chính là Giới thiệu, Phương pháp đề xuất, Thực nghiệm và Kết luận

# Slide 3
- Hiện nay, trong quá trình phát triển phần mềm, việc kiểm thử giao diện người dùng là một thách thức lớn, tuy nhiên các công ty vẫn thường thực hiện một cách thủ công dẫn đến tốn kém thời gian, chất lượng của bộ kiểm thử phụ thuộc vào trình độ kỹ năng của kiểm thử viên nên khó bao quát hết các trường hợp.
- Các phương pháp hiện tại vẫn còn nhiều hạn chế do vẫn còn phụ thuộc vào kiến thức của kiểm thử viên trong trường hợp của phương pháp R&P hoặc có thể sinh ra các kịch bản thừa trong nỗ lực bao quát hết các trạng thái của hệ thống với phương pháp kiểm thử dựa trên mô hình.
- Từ đó dẫn đến nhu cầu cho một giải pháp giúp làm giảm yêu cầu kỹ thuật cho kiểm thử viên và giúp tự động hóa việc bao quát các trường hợp khi sinh kịch bản kiểm thử.
- Nghiên cứu của nhóm chúng em đề xuất phát triển một ngôn ngữ miền chuyên biệt - DSL để mô tả kịch bản kiểm thử ở mức trừ tượng cao, giúp kiểm thử viên dễ dàng mô tả các hành động kiểm thử mà không cần kỹ thuật cao, đồng thời tăng khả năng bao quát các trường hợp một cách tự động.

# Slide 4
- Tổng quan phương pháp như sau:
- Bước đầu người dùng sẽ tạo kịch bản kiểm thử sử dụng DSL có tên User Behavior Language viết tắt là UBL. UBL sẽ có dạng gần ngôn ngữ tự nhiên giúp làm giảm yêu cầu kỹ thuật với người dùng
- Sau đó, hệ thống sẽ hỗ trợ người dùng tạo kịch bản kiểm thử. Ở bước này, kịch bản kiểm thử sẽ được chuyển thành tập lệnh chi tiết chứa các thông tin về hành động và ràng buộc.
- Ở bước thứ ba hệ thống sẽ xác định vị trí của các phần tử web sử dụng XPath một cách tự động
- Sau đó hệ thống sẽ sinh các ca kiểm thử dựa trên kịch bản, dữ liệu người dùng và vị trí phần tử. Hệ thống sẽ sinh luồng hợp lệ để kiểm tra luồng cơ bản của kiểm thử viên định nghĩa và sinh luồng bất thường để kiểm tra phản hồi của hệ thống khi nhận các dữ liệu không hợp lệ.
- Cuối cùng, hệ thống sẽ thực thi bộ kiểm thử và ghi lại kết quả và trả lại báo cáo cho người dùng.

# Slide 5
- Mô hình của UBL được thiết kế như sau:
- Một Test Scenario (Kịch bản kiểm thử) sẽ bao gồm một hoặc nhiều chuỗi hành động. Chuỗi hành động là các bước người dùng thực hiện thao tác với giao diện trong kịch bản.
- Một chuỗi hành động sẽ bao gồm một hoặc nhiều lệnh, một lệnh sẽ miêu tả một hành động cụ thể do người dùng thực hiện và bao gồm 2 thành phần là $<action>$ là mô tả loại hành động và targeted element mô tả phần tử được thao tác.  Ví dụ Click add to cart backpack mô tả hành động nhấp vào nút thêm giỏ hàng của phần tử backpack.
- Ngoài ra chuỗi hành động có thể bao gồm 0 hoặc nhiều ràng buộc. Ràng buộc sẽ liên kết các lệnh trong chuỗi hành động bằng các phép toán logic AND hoặc OR. Ví dụ Input username & Input password sẽ tiến hành ràng buộc dữ liệu được nhập của 2 hành động phải cùng một bộ.
- Hiện tại hệ thống hỗ trợ 6 loại hành động Open, Hover, Click, Fill, Select, Verify.

# Slide 6
- Để xác định phần tử web có trong kịch bản, chúng em sử dụng thuật toán tính độ tương đồng giữa thông tin trong kịch bản với thông tin các phần tử được trích xuất. 
- Với thông tin trong kịch bản được biểu diễn bằng chuỗi đầu vào s, qua bước chuẩn hóa thu được tập hợp các từ W. 
- Từ nội dung trang Web, hệ thống trích xuất nội dung văn bản (t) và các thuộc tính của phần tử web thu được lần lượt các multiset T, A. 
- Tất cả các thông tin của phần tử được biểu diễn qua M ( M = T + A). Từ các thông tin thu được, tính toán độ tương đồng qua 3 trọng số Match Attribute, Match Score và Weight. 

# Slide 7
- Trong đó, Match Attribute là số lượng thuộc tính chung giữa kịch bản và phần tử.
- Matched Score (MS): Số lượng văn bản chung giữa kịch bản và phần tử
- Weight (Trọng số): Độ tương đồng tổng thể, ưu tiên phần tử chứa nhiều từ hơn từ xâu đầu vào.
- Thứ tự ưu tiên so sánh metric: MS > MA > Weight, do người dùng thường dựa vào văn bản hiển thị khi viết kịch bản.

# Slide 8
- Ví dụ cho cách tính toán như sau: người dùng nhập mô tả "Title in contact person", sau khi chuẩn hóa sẽ thu được tập từ "Title, contact, person".
- Từ nội dung của phần tử trên trang web, sau khi chuẩn hóa thu được văn bản "Title" và tập các từ thuộc tính.
- Tính toán sẽ đưa ra MS = 1, MA = 2 và trọng số = 3

# Slide 9
- Ngoài ra khi nhiều phần tử có cùng điểm tương đồng, phần tử gần nhất với phần tử mục tiêu của hành động trước đó sẽ được chọn (cơ chế lan sóng).

# Slide 10
- Sau khi nhận được kịch bản kiểm thử, vị trí phần tử và dữ liệu người dùng, hệ thống tiến hành sinh các ca kiểm thử.
- Đầu tiên hệ thống sẽ sinh luồng hợp lệ. Từ kịch bản kiểm thử, hệ thống sẽ tách các chuỗi hành động và tiến hành xử lý logic sinh các trường hợp cho từng chuỗi hành động. Sau đó sinh ca kiểm thử bằng cách sinh tất cả tổ hợp của các chuỗi hành động.
- Ví dụ: Chuỗi hành động 1 là Fill A OR Fill B từ đó sinh ra 3 trường hợp hợp lệ là Fill A, Fill B và Fill A và Fill B. Chuỗi hành động 2 đơn chỉ sinh ra 1 trường hợp. Tổ hợp các trường hợp trên sinh ra 3 ca kiểm thử.

# Slide 11
- Sau đó, hệ thống sẽ tiến hành kiểm thử các hành vi bất thường của người dùng - abnormal behaviors, bằng cách cô lập một bộ phận của kịch bản kiểm thử để kiểm tra phản hồi từ giao diện.
- Ví dụ hệ thống cô lập các chuỗi hành động trong dòng 3, 4. Các chuỗi hành động trước đó sẽ được thay dữ liệu hợp lệ để đảm bảo kịch bản failed không phải do các chuỗi hành động này. Các chuỗi được cô lập sẽ được thay dữ liệu không hợp lệ (String rỗng, String sai) để kiểm tra phản hồi của hệ thống khi nhận các dữ liệu bất thường.

# Slide 12
- Về phần thực nghiệm, hệ thống được thực nghiệm trên 2 website Saucedemo và Shoppingdemo và được so sánh với tool đối thủ là Katalon Studio và so sánh khả năng nhận diện phần tử với phương pháp nghiên cứu của Kirinuki và cộng sự
- Các tiêu chí so sánh cho DSL bao gồm
	- Thời gian trung bình để tạo một ca kiểm thử
	- Thời gian học sử dụng công cụ
- Các tiêu chí so sánh cho thuật toán nhận diện phần tử bao gồm:
	- Số ca kiểm thử thành công
	- Độ chính xác xác định phần tử
	- Thời gian xác định phần tử trung bình

# Slide 13
- Về kết quả thực nghiệm DSL, kiểm thử viên sử dụng Katalon Studio và phương pháp đề xuất để sinh 44 ca kiểm thử. Katalon Studio tạo thủ công mất trung bình 33s để tạo ca kiểm thử. Phương pháp đề xuất với khả năng sinh ca kiểm thử tự động và UBL miêu tả ca kiểm thử dễ sử dụng có thể rút ngắn thời gian trung bình tạo ca kiểm thử xuống 15s.
- Đồng thời, với UBL gần với ngôn ngữ tự nhiên, các kiểm thử viên có thể học sử dụng công cụ nhanh hơn học syntax của Katalon với thời gian học trung bình là 2 tiếng so với 4 tiếng.

# Slide 14
- Về kết quả thực nghiệm xác định phần tử web, phương pháp của Kirinuki đạt độ chính xác thấp ở Shoppingdemo với 3/96 phần tử và 28/53 phần tử ở Saucedemo. Trong khi đó, phương pháp đề xuất đạt độ chính xác cao với 88/96 phần tử ở Shoppingdemo và 53/53 ở Saucedemo.
- Với độ chính xác cao khi nhận diện phần tử, số lượng ca kiểm thử thành công của phương pháp cũng đạt được hiệu suất cao với 42/50 tại Shoppingdemo và 26/26 tại Saucedemo so với 1/50 và 19/26 với phương pháp của Kirinuki.
- Đồng thời, thời gian xác định phần tử trung bình của phương pháp Kirinuki là 45s cho trang Shoppingdemo và 20s cho Saucedemo , trong khi đó, phương pháp đề xuất đạt hiệu suất cao với thời gian chỉ còn 30s và 5s. 

# Slide 15
- Để kết luận, phương pháp đề xuất giúp giảm sự phụ thuộc của quá trình kiểm thử giao diện với trình độ lập trình.
- Phương pháp kiểm thử bất thường giúp kiểm thử viên kiểm tra phản hồi của giao diện trong trường hợp bất thường, tăng chất lượng của bộ kiểm thử
- Phương pháp xác định phần tử tự động giúp giảm tác động của thay đổi cấu trúc HTML của trang web và tăng khả năng tái sử dụng của ca kiểm thử.
- Tuy nhiên, giải pháp còn tồn tại một số hạn chế như:
- DSL chưa hỗ trợ các tính năng nâng cao như lưu biến, vòng lặp, điều kiện
- Phương pháp còn gặp khó khăn khi xử lý các web sử dụng tải phần tử động hoặc Single Page App
- Phương pháp chưa tích hợp kỹ thuật xử lý ngôn ngữ tự nhiên để xử lý các từ đồng nghĩa.
- Đề tài nghiên cứu đã có 02 công bố được xuất bản trên tạp chí KSE và chấp nhận tại tạp chí VNU-JCSCE.

# Slide 16
- Em xin cảm ơn các quý thầy cô đã chú ý lắng nghe.
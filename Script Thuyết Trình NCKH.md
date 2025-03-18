Xin chào các thầy cô trong hội đồng, hôm nay chúng em xin phép trình bày báo cáo nghiên cứu khoa học về AutUI - Công cụ hỗ trợ sinh kịch bản kiểm thử giao diện ứng dụng web. Nhóm chúng em gồm 3 thành viên và bọn em đã thực hiện nghiên cứu này với sự hướng dẫn của thầy Lê Khánh Trình. Sau đây, em xin trình bày nội dung báo cáo.

Bài báo cáo của chúng em bao gồm 4 phần chính là Giới thiệu, Phương pháp đề xuất, Thực nghiệm và Kết luận

Đầu tiên em xin trình bày giới thiệu về bối cảnh của đề tài
Trong quá trình phát triển phần mềm, việc kiểm thử giao diện người dùng là một thách thức lớn, tuy nhiên thường được thực hiện một cách thủ công nên rất tốn thời gian, phụ thuộc vào trình độ kỹ năng của kiểm thử viên và khó bao quát hết các trường hợp.
Các phương pháp hiện tại vẫn còn nhiều hạn chế do vẫn còn phụ thuộc vào kiến thức của kiểm thử viên trong trường hợp của R&P hoặc có thể sinh ra các kịch bản thừa trong nỗ lực bao quát hết các trạng thái của hệ thống với kiểm thử mô hình hóa.
Nghiên cứu của nhóm chúng em đề xuất phát triển một ngôn ngữ miền chuyên biệt - DSL để mô tả kịch bản kiểm thử ở mức trừ tượng cao, giúp kiểm thử viên dễ dàng mô tả các hành động kiểm thử mà không cần kỹ thuật cao, đồng thời tăng khả năng bao quát các trường hợp một cách tự động

Tiếp theo em sẽ trình bày tổng quan về phương pháp đề xuất của nhóm chúng em:
Bước đầu người dùng sẽ tạo kịch bản kiểm thử sử dụng DSL có tên User Behavior Language viết tắt là UBL.
Sau đó, hệ thống sẽ hỗ trợ người dùng tạo tập lệnh kiểm thử. Ở bước này, kịch bản kiểm thử sẽ được chuyển thành tập lệnh chi tiết.
Ở bước thứ ba hệ thống sẽ xác định định danh của các phần tử web (ví dụ: XPath) một cách tự động.
Sau đó hệ thống sẽ sinh các ca kiểm thử dựa trên kịch bản, dữ liệu người dùng và vị trí phần tử.
Cuối cùng, hệ thống sẽ chạy ca kiểm thử và ghi lại kết quả và trả lại báo cáo cho người dùng.


Mô hình của DSL được thiết kế như sau:
Một Test Scenario (Kịch bản kiểm thử) sẽ bao gồm một hoặc nhiều chuỗi hành động. Chuỗi hành động là các bước người dùng thực hiện thao tác với giao diện trong kịch bản.
Một chuỗi hành động sẽ bao gồm một hoặc nhiều lệnh, một lệnh sẽ miêu tả một hành động cụ thể do người dùng thực hiện và bao gồm 2 thành phần là $<action>$ là mô tả loại hành động và targeted element mô tả phần tử được thao tác.  Ví dụ Click add to cart backpack mô tả hành động nhấp vào nút thêm giỏ hàng của phần tử backpack.

Ngoài ra chuỗi hành động có thể bao gồm 0 hoặc nhiều ràng buộc. Ràng buộc sẽ liên kết các lệnh trong chuỗi hành động bằng các phép toán logic AND hoặc OR. Ví dụ Input username & Input password sẽ tiến hành ràng buộc dữ liệu được nhập của 2 hành động phải cùng một bộ.

Hiện tại hệ thống hỗ trợ 6 loại hành động

Để xác định phần tử web có trong kịch bản, chúng em sử dụng thuật toán tính độ tương đồng giữa thông tin trong kịch bản với thông tin các phần tử được trích xuất. 
Với thông tin trong kịch bản được biểu diễn bằng chuỗi đầu vào s, qua bước chuẩn hóa thu được tập hợp các từ W. 
Trích xuất nội dung văn bản (t) và các thuộc tính của phần tử web thu được lần lượt các multiset T, A. 
Tất cả các thông tin của phần tử được biểu diễn qua M ( M = T + A). Từ các thông tin thu được, tính toán độ tương đồng qua 3 trọng số Match Attribute, Match Score và Weight. 
Ở đó, Match Attribute là số lượng thuộc tính chung giữa kịch bản và phần tử.
Matched Score (MS): Số lượng text chung giữa kịch bản và phần tử
Weight (Trọng số): Độ tương đồng tổng thể, ưu tiên phần tử chứa nhiều từ hơn từ xâu đầu vào.
Thứ tự ưu tiên so sánh metric: MA > MS > Weight, do người dùng thường dựa vào văn bản hiển thị khi viết kịch bản.
Ngoài ra khi nhiều phần tử có cùng điểm tương đồng, phần tử gần nhất với phần tử mục tiêu của hành động trước đó sẽ được chọn (cơ chế lan sóng).

Giải pháp sẽ tiến hành kiểm thử bất thường - negative testing, kiểm thử các hành vi bất thường của người dùng - abnormal behaviors, bằng cách cô lập một bộ phận của kịch bản kiểm thử để kiểm tra phản hồi từ giao diện.

Ví dụ hệ thống cô lập các chuỗi hành động trong dòng 3, 4. Các chuỗi hành động trước đó sẽ được thay dữ liệu hợp lệ để đảm bảo kịch bản failed không phải do các chuỗi hành động này. Các chuỗi được cô lập sẽ được thay dữ liệu không hợp lệ (String rỗng, String sai) để kiểm tra phản hồi của hệ thống khi nhận các dữ liệu bất thường.

Về phần thực nghiệm, hệ thống được thực nghiệm trên 2 website Saucedemo và Shoppingdemo và được so sánh với tool đối thủ là Katalon Studio và so sánh khả năng nhận diện phần tử với phương pháp nghiên cứu của Kirinuki và đồng nghiệp

Các tiêu chí so sánh cho DSL bao gồm
Thời gian trung bình để tạo một ca kiểm thử
Thời gian học sử dụng công cụ

Các tiêu chí so sánh cho thuật toán nhận diện phần tử bao gồm:
Thời gian trung bình để tạo một ca kiểm thử
Thời gian học sử dụng công cụ

Về kết quả thực nghiệm DSL, phương pháp đề xuất đạt được thời gian tạo test suite nhanh hơn 54% so với Katalon Studio với số lượng ca kiểu thử được tạo ra bằng nhau với 44 ca kiểm thử. Các kiểm thử viên cũng đã được sử dụng cả 2 tool kiểm thử và với việc cho phép miêu tả ca kiểm thử gần với ngôn ngữ tự nhiên sử dụng DSL, các kiểm thử viên có thể sử dụng giải pháp nhanh gấp đôi so với học sử dụng Katalon Studio

Về kết quả thực nghiệm xác định phần tử web, phương pháp đề xuất giúp tăng số ca kiểm thử chạy thành công từ 1 lên 42/50 và 19 lên 26/26 ở 2 trang web so với phương pháp của Kirinuki. Độ chính xác khi nhận diện phần tử cũng được cải thiện từ 3 lên 88/96 và 28 lên 53/53. Số ca kiểm thử có thể thực thi được tăng từ 2 lên 50/50 với trang Shoppingdemo. Cuối cùng, thời gian kiểm thử trung bình được cải thiện từ 45s xuống 30s ở Shoppingdemo và 20s xuống 5s ở saucedemo.

Về phần kết luận
Phương pháp đề xuất giúp giảm sự phụ thuộc của quá trình kiểm thử giao diện với trình độ lập trình.
Phương pháp nhận diện phần tử tự động giúp giảm tác động của thay đổi cấu trúc HTML của trang web và tăng khả năng tái sử dụng của ca kiểm thử.
Phương pháp kiểm thửu bất thường giúp kiểm thử viên kiểm tra phản hồi của giao diện trong trường hợp bất thường, tăng chất lượng của bộ kiểm thử

Tuy nhiên, giải pháp còn tồn tại một số hạn chế như:
DSL chưa hỗ trợ các tính năng nâng cao như lưu biến, vòng lặp, điều kiện
Phương pháp còn gặp khó khăn khi xử lý các web sử dụng tải phần tử động hoặc  Single Page App
Phương pháp chưa tích hợp kỹ thuật xử lý ngôn ngữ tự nhiên để xử lý các từ đồng nghĩa.

Đề tài nghiên cứu đã được xuất bản trên tạp chí khoa học uy tín như KSE và VNU-JCSCE.
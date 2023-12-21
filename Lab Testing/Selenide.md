#LabTesting
Điểm mạnh

Bao gồm các thư viện rất mạnh:
- Allure: Cung cấp report,  logs UI cho tester, kết hợp với ScreenCapture cho phép tester check lại từng bước trong quá trình kiểm thử.
- Grid: Cho phép chạy Selenium trên nhiều máy khác nhau cùng lúc, giúp kiểm thử UI trên nhiều phiên bản web browser và hệ điều hành khác nhau.
- Docker: Cho phép chạy Selenium trên máy ảo, giúp dễ dàng cài đặt các đặc điểm của môi trường test như phiên bản browser, hệ điều hành, và giúp đóng gói test cho dễ dàng trao đổi giữa các thiết bị test khác nhau.
- WebDriver: Cho phép người dùng cài đặt driver của các phiên bản browser khác nhau một cách tự động.
- Hỗ trợ nhiều ngôn ngữ cho kiểm thử: C#, Java, Python, Ruby,...
- Có IDE extension cho các browser, giúp test kiểm thử ngay trên các browser tùy chọn.
- Là công cụ được sử dụng phổ biến nhất trong 4 công cụ

Điểm yếu:

- Không thể target được các items có tag name được sinh ra.
- Thời gian set-up: Do việc cần nhiều thư viện để có thể hoạt động tốt nhất theo yêu cầu của tester, Selenium sẽ cần nhiều thời gian để cài đặt và setup.
- Lỗi kỹ thuật: Do là một thư viện open-sourced, các phiên bản mới của Selenium và các thư viện hỗ trợ đều có nguy cơ bị lỗi.
- Không có report và log cho test nếu như không cài đặt thêm các thư viện.
- Độ khó cao: Với việc set up cho mỗi thư viện là khác nhau và syntax phức tạp, để tester sử dụng hiệu quả Selenium sẽ cần thời gian dài sử dụng.



Đặc trưng: Là một project open-sourced bao gồm nhiều thư viện và tool nhằm hỗ trợ cho việc kiểm thử  thự động có lịch sử lâu đời từ 2002. Cung cấp sự tùy chỉnh hoàn toàn cho tester và cung cấp nhiều sự lựa chọn cho các nhu cầu kiểm thử khác nhau. Tuy nhiên đi kèm là sự phức tạp trong việc học và sử dụng.


Ý kiến cá nhân: Selenium là một công cụ rất hoàn thiện với các thư viện đáp ứng các nhu cầu khác nhau của người dùng, đồng thời có số lượng người sử dụng cao nhất và lượng thư viện hỗ trợ lớn nhất và luôn được cập nhật. Đánh đổi sự phức tạp trong việc sử dụng và syntax là một công cụ có thể được tùy chỉnh để đáp ứng gần như mọi nhu cầu của người dùng.
#LabTesting


Reference:
UI Testing Guide: https://www.lambdatest.com/learning-hub/ui-testing
Top 40 UI Testing Tools: https://www.lambdatest.com/blog/best-ui-testing-tools/
Selenium Tutorial: https://www.lambdatest.com/selenium
Wiki for UI Testing Tools: https://en.wikipedia.org/wiki/Comparison_of_GUI_testing_toolsv

1. Các app lựa chọn
- Free - open source:
	- Selenity
	- Cypress
	- Playwright
	- Puppeteer
	- Appium

- License:
	- Testsigma
	- ACCELQ
	- TestCraft
	- Ranorex
	- TestStudio



Xử lý n-wise testing cho n câu lệnh expr trong 1 test case
Xử lý cách pick các Test data combo cho Test case.


Xin chào các thầy cô đang lắng nghe bài thuyết trình của em
Em tên là Phạm Hoàng Ân và em xin trình bày báo cáo về phương pháp cải thiện độ phủ cho test suites sinh bởi user interface cho web app

1

Đầu tiên em xin trình bày phần đặt vấn đề.
UI Testing là một trong các lĩnh vực testing quan trọng do ảnh hưởng trực tiếp đến trải nghiệm người dùng. Tuy nhiên UI Testing còn rất tốn kém về nhân lực và thời gian cũng như các kịch bản test cho UI thường rất phức tạp.
Hiện nay đã có nhiều giải pháp trên thị trườgn cho việc kiểm thử UI tự động tuy nhiên còn nhiều hạn chế (không thể hiện quan hệ giữa các phần tử => thiếu sự chính xác trong việc mô hình hóa hành động của trang web)

Báo cáo của em nhắm đến các mục tiêu sau:
Sử dụng constraint data để mô tả quan hệ giữa các phần tử
Sử dụng negative testing kết hơp với constraint để tăng độ phủ khi testing

2

Tiếp theo em xin trình bày về phần thiết kế hệ thống.
Hệ thống chia làm 3 module chính:
Tiền xử lý data
Xử lý toán logic
Sinh bộ test invalid

Module tiền xử lý dữ liệu nhận vào kịch bản, dữ liệu và xử lý rồi lưu lại
Xử lý kịch bản bằng cách xử lý constraint bằng module logic rồi lưu truth table + kịch bản
dữ liệu được xử lý và lưu thành HashMap

Module Logic có nhiệm vụ xử lý các constraint data dưới dạng biểu thức logic thành truth table và giao tiếp với chương trình chính chạy trong JAVA bằng HTTP

Module sinh bộ test invalid hoạt động như sau:
Thay dữ liệu hợp lệ cho các assertion Block trước Block cần cô lập
sử dụng dữ liệu không hợp lệ cho Block cần cô lập
Xóa các Block phía sau block cần cô lập

Xử lý assertion
Chuyển biểu thức assertion thành dạng dnf
chuyển dạng dnf thành array
Dịch sang ngôn ngữ đầu ra

Lặp qua các array dnf
Lặp qua từng phần tử trong array
nếu một phần tử false thì cả array false
nếu tất cả array false thì trả false

Custom keyword check giá trị
Tự tìm các attribute có ảnh hưởng đến giao diện
=> thân thiện người dùng

Sử dụng thuật toán đệ quy để tìm phần tử con nhỏ nhất
Không kiểm tra sai phần tử bọc ngoài

Đa ngôn ngữ:
Cài đặt syntax từng ngôn ngữ cho từng phần tử

 3
Thí nghiệm
Kịch bản:
Vào url saucedemo
Nhập username password
Click login
Click Add to cart
Click vào cart
Kiểm tra có backpack bên trong

=> 2 Assertion block

Assertion block 1 có 2 action line 1 biểu thức => 4 dạng invalid
Assertion Block 2 có 2 action line => 2 invalid + 1 valid => 2 template

Kết quả
tạo tay selenium mất 5p
chạy tạo test mất 3s

thời gian chạy 43s 52s do ngôn ngữ script đầu ra, script sinh ra có thể không tối ưu như người viết

4 Kết luận

Sinh test cho UI tốn kém và phức tạp
Sử dụng biểu thức logic miêu tả quan hệ giữa các phần tử cho phép sử dụng data hiệu quả và sinh test chính xác hơn
Sử dụng biểu thức để tìm các trường hợp sai sử dụng negative test cho phép tăng độ phủ khi test


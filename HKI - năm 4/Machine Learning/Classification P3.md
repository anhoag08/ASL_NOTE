#ML 

Format giữa kỳ:

10 TN
2 Tự luận (dựa trên HW)

# Problem Setting
- Phân chia 2 miền dữ liệu
- 2 nhãn y = {+1, - 1}
Goal
- Tìm optimal linear plane (decision boundary)
f(x) = sgn(wTx + b)

# Intuition
- Có thể có nhiều đường đúng
- Đường nào phân chia tốt nhất
Margin: Khoảng cách từ đường phân chia tới điểm dữ liệu gần nhất
- Ý tưởng của SVM: Tìm đường phân chia tối đa Margin

# Support Vector Machines (SVM)
![[Pasted image 20241018101824.png|500]]
Chỉnh sửa:  Margin = 2/ || w ||^2

Đặc điểm bài toán:
- Bài toán hàm lồi, có cực tiểu toàn cục

# Linearly Non-separable Cases
- Nếu các điểm không thể chia linear
=> Hard margin SVM không thể áp dụng trực tiếp

# Soft Margin SVM
- Thêm biến mềm
- Phạt việc gán nhãn sai
![[Pasted image 20241018102610.png|500]]

C càng lớn thì việc giảm thiểu sự gán nhãn sai của SVM
C càng nhỏ thì margin càng lớn
=> Soft Margin SVM đánh đổi giữa việc tối ưu hóa margin và giảm thiểu gán nhãn sai

![[Pasted image 20241018102958.png|500]]

Hàm mất mát cho SVM => có thể sử dụng Gradient Descent cho bài toán SVM

Các điểm nằm ngoài margin thì sẽ không gây mất mát
Các điểm nằm giữa lề và đường phân chia sẽ gây mất mát nhỏ
Các điểm lệch sang miền lề còn lại sẽ gây mất mát lớn

![[Pasted image 20241018103530.png|500]]

# SVM Nonlinear Case
- Đưa dữ liệu lên không gian nhiều chiều hơn để tìm đường chia
1: Định nghĩa một feature mapping mới
2: Tìm siêu phẳng chia trong chiều không gian mới
3: Đưa về dạng SVM cơ bản

# Kernel Functions

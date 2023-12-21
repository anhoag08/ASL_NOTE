
# Probability
- Phép thử: Một thí nghiệm hoặc quan sát
- Không gian mẫu: Tập các kết quả cơ bản của phép thử
- Biến cố: Một tập con của không gian mẫu
- Kết quả cơ bản: Các kết quả có thể xảy ra của phép thử

![[Pasted image 20231214153148.png|500]]

# Kết quả phép thử
- Tạo các kết quả phép thử từ các kết quả khác dùng các phép toán logic
![[Pasted image 20231214153425.png|500]]

- Với A là kết quả của một phép thử
	- Tồn tại P(A), xác suất xảy ra A. Xác xuất này = 1 nếu A chắc chắn xảy ra và = 0 nếu A là kết quả rỗng, nếu A và B là 2 kết quả độc lập thì P(A v B) = P(A) + P(B)
	![[Pasted image 20231214154628.png|500]]

# Định nghĩa cổ điển của xác suất
- Nếu xác suất xảy ra của mọi kết quả cơ bản là như nhau thì P(wi) = 1/N với wi là kết quả cơ bản thứ i của phép thử. Công thức:
  ![[Pasted image 20231217164249.png|500]]
# Một số tính chất của xác suất
  ![[Pasted image 20231217164408.png|500]]
# Ví dụ 1
![[Pasted image 20231217164452.png|500]]
# Ví dụ 2
![[Pasted image 20231217164744.png|500]]

# Xác suất có điều kiện
- Xác suất của biến cố A khi biết B có thể tính bằng:
![[Pasted image 20231217173608.png|500]]
- Xác suất hội
![[Pasted image 20231217173650.png|500]]

# Công thức Bayes
![[Pasted image 20231219202657.png|500]]
# Độc lập
- Biến cố A và B độc lập nếu P(AB) = P(A)P(B)
- Nếu P(B) > 0, biến cố A và B độc lập khi và chỉ khi P(A|B) = P(A)

# Biến ngẫu nhiên
- Biến ngẫu nhiên là kết quả số học của một thử nghiệm
- Thông thường, một biến ngẫu nhiên là một hàm:
![[Pasted image 20231219204248.png|500]]
- Hàm khối xác suất (pmf) hoặc một phân bố xác xuất:![[Pasted image 20231219204429.png|500]]
# Giá trị mong đợi và độ lệch
- Giá trị mong đợi của một biến ngẫu nhiên X được định nghĩa như sau:![[Pasted image 20231219204743.png|500]]
- Độ lệch chuẩn của biến ngẫu nhiên X là bình phương khoảng cách từ X đến giá trị mong đợi:![[Pasted image 20231219204845.png|500]]
# Phân bố điều kiện và phân bố hội
- Phân bố hội pmf của 2 biến ngẫu nhiên x,y là: p(x,y) = P(X=x,Y=y)
- Phân bố điều kiện của x,y:![[Pasted image 20231219205446.png|500]]
- Với nhiều biến hơn, ta có:![[Pasted image 20231219205549.png|500]]
# Phân bố biên
- Cho một hàm khối xác xuất hội p(x, y) = P(X=x, Y=y), xác suất biên của chúng là:![[Pasted image 20231219210034.png|500]]
# Phân phối nhị thức
- Từ một loạt các phép thử với 2 kết quả cơ bản, mỗi phép thử độc lập với nhau.
- VD: Liên tục tung một đồng xu (có thể không cân bằng) là một ví dụ điển hình
- Ta có phân bố nhị thức của chúng như sau:![[Pasted image 20231219211339.png|500]]
- Với k là số lần phép thử thành công và $\theta$ là xác suất phép thử thành công và (n, k):![[Pasted image 20231219211440.png|500]]
# Phân bố chuẩn
- Là một hàm phân bố liên tục:![[Pasted image 20231219211542.png|500]]
- Với $\mu$ là giá trị mong đợi và $\sigma$ là độ lệch
- Tên khác: Phân bố Gauss
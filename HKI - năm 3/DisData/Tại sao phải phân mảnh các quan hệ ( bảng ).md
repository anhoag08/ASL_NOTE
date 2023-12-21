
# Một số vấn đề phát sinh khi phân mảnh
- Khó khăn trong việc kiểm tra sự toàn vẹn của dữ liệu
- Một số thao tác cần nhiều mảnh, cần liên kết lại
- Có thể có ứng dụng không thích ứng với phân mảnh


# Các kiểu phân mảnh quan hệ (bảng)
##    Phân mảnh ngang (phân đoạn)

- Quan hệ được chia theo chiều ngang, tạo ra các mảnh ( đoạn ) là các quan hệ nhỏ hơn
- Mỗi mảnh tương tứng với phép toán chọn, bao gồm các bộ thỏa mãn điều kiện cho trước

##   Phân mảnh dọc

- Quan hệ được chia thành các quan hệ (mảnh) nhỏ theo chiều dọc, tạo ra các mảnh bao gồm một số cột của quan hệ gốc.
- Mỗi mảnh tương ứng với phép toán chiếu.

# Mức độ phân mảnh

- Phân mảnh ít nhất: Toàn bộ quan hệ là một mảnh
- Phân mảnh nhiều nhất: Mỗi bộ (hay thuộc tính) la một mảnh

##   Tính đúng đắn của phân mảnh

###      Tính đầy đủ

- Thao tác phân mảnh quan hệ R thành các quan hệ (mảnh) R1, R2, .. Rn được gọi là đầy đủ khi và chỉ khi mỗi phần tử dữ liệu của R phải thuộc vào một mảnh Ri nào đó.

###      Tính tái tạo

- Thao tác phân mảnh quan hệ R thành các quan hệ mảnh thì phải tồn tại phép toán hợp quan hệ sao $\theta$ sao cho 
- R = $\theta$ Ri 1 <= i <= n

###      Tính tách rời

- Thao tác phân mảnh quan hệ R thành các quan hệ được gọi là tách rời nếu không có một đơn vị dữ liệu nào của R đồng thời thuộc vào nhiều hơn một mảnh R

###      Các kiểu cấp phát

- **Yêu cầu** : Giả sử có các phân mảnh (F1, F2, ..., Fn); các site (S1, S2, ... Sn ) trên amngj và tập tứng dụng (Q1, Q2, ... Qn) thực hiện trên đó
- Việc cấp phát đảm bảo
	- Chi phí nhỏ nhất: lưu trữ Fi tại site Sj, truy xuất tại mảnh Fb cập nhật tại các site, chi phí trao đổi thông tin
	- Hiệu năng tối ưu: Giảm thời gian đáp ứng, tăng lưu lượng xử lý tại mỗi site
- Không nhân bản (phân hoạch): Mỗi mảnh nằm chỉ tại mội site
- Nhân bản đầy đủ: Mọi mảnh nằm trên mọi site
- Nhân bản từng phần: Mỗi mảnh có thể nằm trên một số site

=> Quy tắc: Nếu số truy vấn đọc >> số truy vấn ghi thì nhân bản là có lợi

# Phân đoạn ngang

# Phân mảnh dọc
- Mỗi mảnh bao gồm một số thuộc tính của quan hệ ban đầu
- Mỗi mảnh đều chứa khóa
- Mỗi mảnh đều chứa mọi bộ của quan hệ ban đầu
- Số khả năng phân mảnh là lớn


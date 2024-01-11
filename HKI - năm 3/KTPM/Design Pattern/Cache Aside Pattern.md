#Design_Pattern 

# Link Azure:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/cache-aside

# Vấn đề
- Ứng dụng sử dụng cache để cải thiện truy xuất liên tục tới dữ liệu lưu trong data store. Tuy nhiên, thực tế là khó khăn để dữ liệu trong cache luôn đồng bộ với kho dữ liệu. Ứng dụng nên triển khai một mô hình giúp đảm bảo dữ liệu trong cache luôn đồng bộ với dữ liệu trong kho nhưng đồng thời nhận diện và xử lý các tình huống khi dữ liệu trong cache ít được truy xuất

# Giải pháp
- Nhiều hệ thống cache thương mại cung cấp khả năng read-through và write-through/write-behind. Trong các hệ thống đó, khi ứng dụng truy xuất data bằng cách truy cập cache. Nếu data không ở trong cache, data sẽ được truy xuất về từ kho và thêm và cache. Mọi thay đổi dữ liệu tới data trong cache sẽ tự động được viết về kho lưu trữ
- Với các cache không cung cấp khả năng trên, ứng dụng sẽ phải đảm bảo việc kiểm soát data
- Một ứng dụng có thể bắt chước tính năng read-through bằng cách triển khai mô hình cache-aside. Mô hình này lưu dữ liệu và cache theo yêu cầu

![[Pasted image 20240110231052.png|500]]

- Nếu một ứng dụng muốn cập nhật thông tin, có thể sử dụng mô hình write-through để sửa kho lưu trữ và loại bỏ dữ liệu tương ứng trong cache
- Khi dữ liệu cần được truy xuất lại, mô hình cache-aside sẽ cập nhật dữ liệu từ kho tới cache

# Vấn đề
- Vòng đời dữ liệu
- Loại bỏ dữ liệu cũ
- Tải dữ liệu có thể cần của ứng dụng
- Tính đồng bộ
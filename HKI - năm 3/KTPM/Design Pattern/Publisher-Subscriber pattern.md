#Design_Pattern 

# Link Azure:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/publisher-subscriber

# Định nghĩa

Mô hình Publisher-Subscriber (hay còn được gọi là Observer pattern) là một mô hình thiết kế phần mềm, nơi một đối tượng, được gọi là "Publisher" (Người phát hành), duy trì danh sách các đối tượng quan tâm, được gọi là "Subscribers" (Người đăng ký), và tự động thông báo tới chúng về bất kỳ thay đổi nào trong trạng thái của nó. Mô hình này thường được sử dụng để triển khai các hệ thống xử lý sự kiện và thông báo trong các ứng dụng.

**Cách Hoạt Động:**

1. **Publisher (Người Phát Hành):**
    
    - Publisher là đối tượng chịu trách nhiệm về việc duy trì danh sách các Subscribers và thông báo cho chúng về các sự kiện hoặc thay đổi trong trạng thái của nó.
2. **Subscribers (Người Đăng Ký):**
    
    - Subscribers là các đối tượng quan tâm đến sự kiện hoặc thông báo từ Publisher. Chúng đăng ký để nhận thông báo về các sự kiện cụ thể.
3. **Đăng Ký và Hủy Đăng Ký:**
    
    - Subscribers đăng ký để nhận thông báo bằng cách đăng ký với Publisher. Ngược lại, chúng có thể hủy đăng ký nếu họ không muốn nhận thông báo nữa.
4. **Thông Báo (Publish):**
    
    - Khi có sự kiện hoặc thay đổi trong trạng thái của Publisher, nó thông báo cho tất cả Subscribers được đăng ký. Thông báo này có thể chứa dữ liệu liên quan đến sự kiện.
5. **Cập Nhật Subscribers:**
    
    - Mỗi Subscriber nhận thông báo và tự động cập nhật trạng thái của mình dựa trên nội dung của thông báo. Quá trình này giúp đảm bảo rằng tất cả các Subscribers được thông báo khi có thay đổi.

**Ưu Điểm:**

- **Tính Linh Hoạt:** Mô hình Publisher-Subscriber giúp tạo ra một cơ chế linh hoạt để quản lý sự kiện và thông báo trong hệ thống.
- **Giảm Kết Nối Trực Tiếp:** Subscribers không cần biết về sự tồn tại của nhau. Điều này giảm sự kết nối trực tiếp giữa các thành phần.

**Ứng Dụng:**

- Mô hình này thường được sử dụng trong xử lý sự kiện, giao diện người dùng, quản lý tác vụ đồng bộ, và nhiều ngữ cảnh khác trong phát triển phần mềm.

Mô hình Publisher-Subscriber giúp tạo ra một cách mạnh mẽ để quản lý giao tiếp giữa các thành phần của hệ thống mà không làm tăng tính kết nối giữa chúng.
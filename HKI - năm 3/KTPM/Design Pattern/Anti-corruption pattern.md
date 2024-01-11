#Design_Pattern 

# Link Azure:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/anti-corruption-layer

# Định nghĩa
- Triển khai một lớp adapter giữa các hệ thống con không chia sẻ cùng yêu cầu ngữ nghĩa. Lớp này sẽ biên dịch yêu cầu tự hệ thống con này sang hệ thống con khác. Mô hình này đảm bảo thiết kế hệ thống không bị giới hạn bởi dependencies của các hệ thống con khác.
# Bài toán
- Đa số ứng dụng phụ thuộc vào các hệ thống khác cung cấp dữ liệu hoặc chức năng. Nếu một ứng dụng legacy được chuyển sang hệ thống hiện đại, chúng có thể vẫn yêu cầu các tài nguyên legacy tuy nhiên các chức năng mới vẫn cần phải gọi được hệ thống legacy
- Hệ thống legacy có thể gặp các vấn đề về chất lượng APIs. Việc bảo trì kết nối giữa hệ thống cũ và mới có thể yêu cầu hệ thống mới phải thay đổi để phù hợp với các yêu cầu của API hệ thống cũ, dẫn đến ảnh hưởng tới thiết kế của hệ thống mới

# Giải pháp
- Cô lập hệ thống con bằng cách triển khai một lớp anti-corruption giữa chúng. Lớp này sẽ biên dịch yêu cầu giữa 2 hệ thống, cho phép một hệ thống có thể giữ nguyên kiến trúc và hệ thống khác có thể không phải thỏa hiệp thiết kế và công nghệ của nó

![[Pasted image 20240110220407.png|500]]

- Hình trên biển diễn một ứng dụng gồm 2 hệ thống con. Hệ thống A gọi tới hệ thống B qua lớp anti-corruption. Giao tiếp giữa hệ thốgn A và lớp ac luôn dùng kiếm trúc theo hệ thống A. Giao tiếp giữa hệ thống B và lớp ac dùng kiến trúc hệ thống B. Lớp ac sẽ chứa các logic cần thiết để biên dịch yêu cầu giữa 2 kiến trúc của 2 hệ thống khác nhau

# Vấn đề
- Có thể tạo độ trễ
- Tạo thêm dịch vụ con (lớp ac) cần được bảo trì và quản lý
- Scale lớp ac
- Cần 1 hay nhiều lớp ac
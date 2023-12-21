#Design_Pattern 

Layered Architecture Style

- Presentation Layer
- Business Layer
- Persistence Layer
- Database Layer


Đặc điểm
- Tách biệt các mối quan tâm
- Phân chia lớp theo khía cạnh kỹ thuật
- Không giới hạn số lớp
- Có thể ràng buộc về tương tác giữa các lớp
- Lớp được chia một cách logic (so với triển khai thực tế).

Anti-pattern: architecture sinkhole, các yêu cầu gửi đến một lớp nhưng lớp đấy không xử lý gì thêm, chỉ forward đến lớp tiếp theo.


Pipeline:
- Là các bộ filter xử lý data và có pipe dẫn đến các filter khác.

Khác biệt giữa kiến trúc pipeline và layered architecture: Layered architecture dựa trên các hàm request và return tạo dòng dữ liệu 1 chiều, còn pipeline giữa các filter không có sự liên quan đến nhau.


Microkernel Architecture
- Bao gồm các component được kết nối đến một core system.
- Core cung cấp chức năng cơ bản, các chức năng khác được cung cấp bởi các plugin
- Plugin có thể được xóa/thêm sau khi core system được cài đặt.

Service-based Architecture Style
- Bao gồm UI cho phép người dùng truy cập tới các component và truy xuất dữ liệu từ database

Event-Driven Architecture Style (BTL):
- Bao gồm một Event Producer gửi các event với một Event Broker phân chia event thành các topic, rồi gửi event theo pipe topic của nó tới các Event Consumer.


SOA and Microservices

Microservices
- Is an approach to developing a single application as suite of small services, each running in its own process and communicating with lightweight mechanisms, often an http resource API

Advantages of microservices
- High modularity
- Reduce development time
- Flexible in choosing technologies
- Independent deployment
- Easy to scale

Disadvantages
- How big a micro service can be ?
- A type of distributed systems -> need time for communication, more complex than monolith
- Databases may be redundant
- Complicated testing
- Many different technologies may be a barrier

Monolith systems
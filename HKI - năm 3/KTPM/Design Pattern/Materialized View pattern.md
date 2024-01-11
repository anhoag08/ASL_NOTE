#Design_Pattern 

# Link Azure:
*https://learn.microsoft.com/en-us/azure/architecture/patterns/materialized-view

Mô hình "Materialized View" là một biện pháp thiết kế trong hệ thống cơ sở dữ liệu để tối ưu hóa hiệu suất truy vấn bằng cách lưu trữ và duy trì trước các kết quả của một truy vấn phức tạp hoặc tính toán phức tạp, thay vì phải tính toán chúng mỗi khi có yêu cầu truy vấn. Mô hình này thường được sử dụng để giảm thiểu thời gian và tài nguyên tính toán cần thiết cho truy vấn, đồng thời cung cấp một cách hiệu quả để truy cập dữ liệu đã được tiền xử lý.

**Cách Hoạt Động:**

1. **Tạo và Lưu Trữ Trước (Materialization):**
    
    - Khi một truy vấn phức tạp được thực hiện và kết quả của nó thường xuyên được yêu cầu, một "Materialized View" được tạo ra để lưu trữ kết quả của truy vấn đó. Điều này có nghĩa là dữ liệu được tính toán và lưu trữ trước.
2. **Duy Trì Cập Nhật:**
    
    - Các "Materialized View" thường được duy trì cập nhật thông qua các kịch bản hoặc quy trình đồng bộ hóa. Khi dữ liệu nguồn (cơ sở dữ liệu gốc) thay đổi, "Materialized View" cũng cần được cập nhật để đảm bảo rằng nó vẫn chính xác và đồng bộ với nguồn dữ liệu.
3. **Tối Ưu Hóa Truy Vấn:**
    
    - Việc lưu trữ trước kết quả của truy vấn giúp tối ưu hóa hiệu suất truy vấn. Thay vì phải thực hiện tính toán phức tạp mỗi khi có yêu cầu truy vấn, hệ thống có thể truy cập trực tiếp vào "Materialized View" để nhận kết quả.
4. **Chỉ Cập Nhật Khi Cần:**
    
    - Cập nhật "Materialized View" có thể được kích hoạt bởi các sự kiện cụ thể hoặc lên lịch trình định kỳ. Điều này giúp giảm thiểu tải cho hệ thống và đảm bảo rằng dữ liệu đã được tiền xử lý chỉ được cập nhật khi cần thiết.
5. **Thích Ứng Với Môi Trường Dữ Liệu:**
    
    - "Materialized View" có thể được tinh chỉnh để đáp ứng các yêu cầu cụ thể của ứng dụng hoặc hệ thống. Điều này bao gồm việc xác định cách cập nhật, lọc dữ liệu và quản lý bộ nhớ.
6. **Thích Nghi Với Tần Suất Truy Vấn:**
    
    - Sự lựa chọn về cách cập nhật "Materialized View" có thể phụ thuộc vào tần suất và độ quan trọng của dữ liệu nguồn. Đối với dữ liệu ít thay đổi, cập nhật có thể thực hiện ít khi hơn để giảm tải hệ thống.
7. **Dùng Cho Truy Vấn Phức Tạp:**
    
    - Mô hình này thường được sử dụng cho các truy vấn phức tạp, tính toán công phu, hoặc các truy vấn thường xuyên được sử dụng để cung cấp kết quả nhanh chóng mà không phải chịu tải tính toán lớn mỗi lần truy vấn.

"Materiazlied View" là một công cụ quan trọng trong quản lý cơ sở dữ liệu để cải thiện hiệu suất truy vấn và giảm độ trễ khi xử lý các yêu cầu truy vấn phức tạp.
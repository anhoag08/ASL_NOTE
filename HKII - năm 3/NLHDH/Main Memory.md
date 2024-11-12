#OS 

**Logical address:
- Là tập các địa chỉ được sinh ra bởi CPU, còn được gọi là virtual address
**Physical address
- Địa chỉ thực tế tính bởi đơn vị bộ nhớ

- Địa chỉ logic và địa chỉ thực thế giống nhau trong cơ chế gắn địa chỉ ***compille-time*** và ***load-time*** và khác nhau trong cơ chế gắn địa chỉ ***execution-time***.
# Memory Management Unit (MMU)
- Phần cứng xử lý quá trình ánh xạ từ địa chỉ logic -> địa chỉ vật lý trong lúc chạy chương trình

- ## Base Register (Relocation Register)
	- Giá trị trong relocation register được cộng vào địa chỉ logic sinh ra bởi chương trình để tạo thành địa chỉ vật lý

- ## Contigous Allocation
	- Kiểm tra địa chỉ logic có nằm trong khoảng giới hạn của chương trình, nếu không báo lỗi, nếu có thì địa chỉ vật lý = base + limit
	![[Pasted image 20240325093435.png|800]]
- ## Variable Partition
	![[Pasted image 20240325093733.png|800]]
	- CPU lưu địa chỉ các ô nhớ được chiếm và các ô nhớ trống
	- Khi có tiến trình đến, CPU cung cấp ô nhớ đủ để lưu trữ tiến trình
	- CPU chạy xong thì trả ô nhớ

- ## Dynamic Storage-Allocation
	- **First-fit:** Quét từ địa chỉ 0, cấp phất ô nhớ đầu tiên đủ để lưu trữ tiến trình (***Tốc độ tốt nhất***)
	- **Best-fit:** Quét toàn bộ bộ nhớ, cung cấp ô nhỏ nhất có thể để lưu trữ tiến trình (***Tối đa bộ nhớ tốt nhất***)

# Fragmentation
- **External Fragmentation:** Tổng bộ nhớ tồn tại để thỏa mãn một yêu cầu nhưng không liên tục
- **Internal Fragmentation:** Cấp phát bộ nhớ có thể lớn hơn bộ nhớ yêu cầu, phần bộ nhớ thừa trực thuộc bộ nhớ được cấp phát nhưng không được sử dụng
- Với chiến thuật ***first-fit***, cứ với N ô nhớ được cấp phát, 0.5N ô nhớ bị mất do phân mảnh => 1/3 ô nhớ không sử dụng được => 50-percent rule

# Segmentation
![[Pasted image 20240325101715.png|800]]

![[Pasted image 20240325102232.png|800]]

- Địa chỉ logic bây giờ lưu dưới dạng tuple <segmentNo, offset>, địa chỉ các segment được lưu trong segment table, khi có một yêu cầu, kiểm tra xem offset có vượt quá limit => error, nếu không thì địa chỉ vật lý = segmentBase + offset.
- Tồn tại ***External Fragmentation*** do tổng 2 segment có thể bằng yêu cầu cấp phát nhưng k liên tục, không tồn tại ***Internal Fragmentation*** do chương trình cấp phát dynamic trong fragment => không cấp phát lớn hơn yêu cầu

# Paging
- Không tồn tại ***External Fragmentation*** do còn ram trống => còn frame trống => có thể lưu page
- Có tồn tại ***Internal Fragmentation*** do mỗi frame cung cấp có thể lớn hơn yêu cầu của page

![[Pasted image 20240325110406.png|800]]

$PhysAdd = FrameNo * FrameSize + Offset$

![[Pasted image 20240401093202.png|800]]

$EffAccTime=CacheHitRate * (CacheAccTime + RAMAccTime)+CacheMissRate * (RAMAccTime * 2)$ 

***Valid bit***: Là bit chứa frame nằm trong địa chỉ logic của tiến trình
***Invalid bit***: Là bit chứa frame không nằm trong địa chỉ logic của tiến trình








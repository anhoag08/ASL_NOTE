

Variable Defined:
Use:
- p-use
- c-use

CFG:
- def-clear: là đường không có một phép gán của một biến cụ thể (VD: def-clear path của biến x)
- complete-path: là đường từ node entry tới exit

Definition-use pair (DU-pair): là một cặp (d, u)
- d là node định nghĩa biến v
- với c-use của v thì u là node sử dụng biến v.
- với p-use của v thì u là một cạnh đi ra của dòng lệnh điều kiện
- Tồn tại một def-clear path của v giữa d và u.

All-defs:
- Với mỗi biến v, ít nhất một đường def-clear từ mỗi def của v tới ít nhất 1 c-use hoặc p-use của v được phủ

All-use:
- Với mỗi biến v, ít nhất một đường def-clear từ mỗi def của v tới mỗi c-use và mỗi p-use của v phải được phủ
- Với p-use, bao gồm tất cả cạnh đi ra của dòng lệnh điều kiện
- Yêu cầu là tất cả DU-pairs được phủ

Simple path: là đường mà các cạnh trong đường là độc nhất
Một đường không vòng lặp nếu tất cả các đỉnh là độc nhất

DU-path: nếu v định nghĩa ở node đầu và 1 trong 2 dkien sau thỏa mãn:
- Có 1 c-use của v ở node cuối và đường P là đường def-clear đơn giản.
- Có 1 p-use của v ở cạnh cuối và P là đường def clear không lặp.

Task: chứng minh độ mạnh yếu các pp test

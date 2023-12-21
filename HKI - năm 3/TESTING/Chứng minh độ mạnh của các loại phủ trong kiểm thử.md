
# Path - All-DU-Path
- Không phải tất cả các đường là DU-Path (yêu cầu với c-use phải là đường cơ bản, với p-use phải loop-free)
=> Phủ path sẽ phủ nhiều hơn All-DU-Path

# All-DU-Path - All-Uses
- Phủ All-DU-Path sẽ phủ hết tất cả các Def của các biến, còn phủ All-Uses chỉ phủ tất các các uses của các biến => không phủ hết các def của các biến đó => Phủ All-DU-Path > Phủ All-Uses

# Phủ All-Uses - All-P-Uses/Some-C-Uses
- Phủ All-Uses sẽ phủ hết cả p-uses cả c-uses còn All-P-Uses/Some-C-Uses chỉ phủ một phần c-uses => All-Uses > All-P-Uses/Some-C-Uses

# Phủ All-Uses - All-C-Uses/Some-P-Uses
- Tương tự trên

# Phủ All-P-Uses/Some-C-Uses - All-P-Uses
- All-P-Uses không phủ c-use

# All-C-Uses/Some-P-Uses - All-C-Uses
- All-C-Uses không phủ p-uses

#  All-C-Uses/Some-P-Uses | Phủ All-P-Uses/Some-C-Uses - All-Defs
- All-Defs chỉ phủ ít nhất một p-use và một c-use

# All-P-Uses - Branch
- Phủ branch sẽ không phủ hết các def như All-P-Uses

# Branch - Statement
- Vẽ CFG cho trường hợp phủ statement mà không phủ branch
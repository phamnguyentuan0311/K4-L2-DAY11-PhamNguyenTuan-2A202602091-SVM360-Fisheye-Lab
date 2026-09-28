# Quan sát vạch ô đỗ

- Hai vạch `parking_line` đã vẽ (mô tả vị trí trong ảnh): Các vạch sơn màu trắng vuông góc với mép dưới của ảnh, nằm ở tiền cảnh và đóng vai trò phân chia các ô đỗ xe kề nhau.
- Một vạch/dấu sơn hoặc biên **không** vẽ, và vì sao: Không vẽ đường biên hoặc vạch chạy ngang dài chia đôi làn đường ở phía xa vì đó là lối dẫn xe đi qua lại trong bãi, không phải là vạch chia một ô đỗ cụ thể.
- Polygon `free_space` dừng ở đâu; có phần bị che nào không: Dừng ở mép các vạch phân ô đỗ phía trước, giáp với dải cây/bãi cỏ phía xa và tránh đi xuyên qua thân chiếc xe màu đỏ đang đỗ.
- Ca chưa chắc cần hỏi người soát (nếu không có, ghi “không có”): không có.

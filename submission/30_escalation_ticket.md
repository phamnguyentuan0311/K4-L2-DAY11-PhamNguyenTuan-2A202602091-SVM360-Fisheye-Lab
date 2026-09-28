# Escalation Ticket

- **Frame:** `adasind_258420.jpg`
- **Ảnh chụp:** ![Lỗi méo hình](../screenshots/1.png)
- **Expected impact:** Nếu model không bắt được xe máy ở góc viền fisheye, hệ thống cảnh báo điểm mù (Blind Spot Detection) sẽ không hoạt động khi có xe máy tạt đầu từ góc khuất, gây rủi ro va chạm cực cao.
- **Owner:** `ai_team`
- **Recommendation:** Yêu cầu AI Team kiểm tra lại tập training set xem tỷ lệ dữ liệu xe máy ở vùng mép (Edge) có bị mất cân bằng (imbalanced) không. Cần tăng cường data augmentation (chỉnh góc méo quang học) cho vùng này.

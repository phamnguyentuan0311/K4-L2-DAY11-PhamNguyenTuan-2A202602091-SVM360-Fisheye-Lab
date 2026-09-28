# Kế hoạch lấy mẫu Gold Set (Bốn camera)

| Camera | Normal / Tần suất | Hard / Tần suất | Cần lưu ý gì khi làm luật | Số lượng dự kiến |
|---|---|---|---|---|
| front | Đường thẳng, nắng đẹp | Ngược sáng rọi thẳng ống kính | Xử lý chói lóa (lens flare) che lấp vật thể | 50 |
| rear | Bãi đỗ xe trống | Xe phía sau bám đuôi sát sạt | Xác định ranh giới `ego_body` ở cản sau rõ ràng | 50 |
| left | Đường thoáng | Xe máy cặp hông tại điểm mù | Phân biệt bóng râm của xe ego với vạch kẻ đường | 50 |
| right | Đường thoáng | Khách bộ hành/xe đạp tạt ngang | Xử lý vật thể bị kéo giãn đột ngột ở mép ống kính | 50 |

- Khi nào cần refresh gold set (đổi camera, calibration hoặc rule): Khi thay đổi vị trí gắn (rigging) camera, nâng cấp firmware ống kính làm thay đổi độ méo, hoặc khi nâng cấp rules_version mới.
- Một ca seam/cross-camera cần policy và evidence trước khi ghép hai box: Một xe đạp đang di chuyển từ góc camera `front` sang góc camera `left` (vùng chồng lấn - seam).
- Vì sao peer agreement hoặc quality report trên ảnh một camera chưa chứng minh gold set đúng cho cả bốn camera: Bốn camera có góc nghiêng, vị trí gắn (rig) và cường độ phơi sáng khác nhau. Thuật toán có thể chạy rất tốt ở camera trước nhưng lại nhận diện sai hoàn toàn ở camera hông do vật thể bị kéo giãn ngang.

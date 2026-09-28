# Kế hoạch review từ lỗi quan sát được

Từ `findings.csv` và `zone_table.md`, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| B4-dense / 258420.jpg | 5 MISSING, 3 SPURIOUS | Vùng viền (edge) méo fisheye rất nặng, dễ sót nhãn Pedestrian ở góc. | Ảnh screenshot vật thể bị biến dạng ở viền. |
| B4-dense / 310008.jpg | 4 WRONG_CLASS, 2 MISSING | Khu vực đông người (dense), tỷ lệ che khuất (occlusion) cao gây nhầm lẫn nhãn. | Ảnh crop vị trí các vật thể bị che khuất chồng lên nhau. |

Giới hạn của kết luận từ ba frame ADASIND: Việc phân tích 3 frame chỉ mang tính cục bộ tại một khoảnh khắc rất ngắn của 1 camera, hoàn toàn không đại diện cho độ phủ của toàn bộ tập dữ liệu (thời tiết, ánh sáng) hay điểm mù đặc thù của các camera khác (rear, left, right).

## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở `45_sampling_plan.csv` (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh như nhiều ca độc lập), và vì sao kế hoạch đó chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi:
Khi lấy mẫu 200 frame, phải áp dụng quy tắc giãn cách thời gian (ví dụ cách nhau ≥ 5 giây) để tránh các frame liền kề có bối cảnh y hệt nhau. Kế hoạch này là lấy mẫu có chủ đích tập trung vào "ca khó" (targeted sampling / hard mining) nhằm lùng sục lỗi để sửa rule. Do đây không phải lấy mẫu ngẫu nhiên (random sampling) phân bố đều, tỷ lệ lỗi đếm được ở đây không đại diện cho độ chuẩn xác (accuracy) thực tế của mô hình.

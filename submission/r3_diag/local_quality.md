# Đối chiếu chất lượng cục bộ — rectangle

Teaching reference, không phải gold set đã phê duyệt; không có điểm đạt tự động.
Nguồn: export r1_craft đã khóa SHA256 `aebbd053f8d4c693bd510ac83efd661e410e647c569e511d04761f8a96a1c295`; slice `B4-dense`.
Ghép hình học greedy một-một theo IoU ≥ 0.50, rồi so class; H ≥ 40 px.
Box trái nằm chủ yếu trong ignore_region reference không tính. Polygon, polyline, track không được chấm.
Đây là phép tính offline của lab, không phải báo cáo hay kết quả tương đương CVAT Premium.

Frame được tính: adasind_258420.jpg, adasind_270517.jpg, adasind_310008.jpg. Frame thiếu trong export: không.
TP=13; FP=9; FN=7; số lần đối chiếu=23; mean IoU của TP=0.743.

| Chỉ số | Micro | Macro | Nhãn thấp nhất |
|---|---:|---:|---:|
| accuracy | 0.565 | 0.826 | 0.609 |
| precision | 0.591 | 0.500 | 0.000 |
| recall | 0.650 | 0.667 | 0.000 |
| jaccard | 0.448 | 0.495 | 0.000 |
| dice | 0.619 | 0.549 | 0.000 |

| Nhãn | TP | FP | FN | Accuracy | Precision | Recall | Jaccard | Dice |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Bike | 4 | 1 | 0 | 0.957 | 0.800 | 1.000 | 0.800 | 0.889 |
| Car | 2 | 8 | 1 | 0.609 | 0.200 | 0.667 | 0.182 | 0.308 |
| Pedestrian | 7 | 0 | 0 | 1.000 | 1.000 | 1.000 | 1.000 | 1.000 |
| ThreeWheeler | 0 | 0 | 6 | 0.739 | 0.000 | 0.000 | 0.000 | 0.000 |

| Frame | TP | FP | FN | Accuracy | Precision | Recall |
|---|---:|---:|---:|---:|---:|---:|
| adasind_258420.jpg | 4 | 6 | 4 | 0.364 | 0.400 | 0.500 |
| adasind_270517.jpg | 5 | 2 | 2 | 0.714 | 0.714 | 0.714 |
| adasind_310008.jpg | 4 | 1 | 1 | 0.800 | 0.800 | 0.800 |

Confusion matrix: hàng = teaching reference; cột = export đã khóa.
`<missing>` là thiếu box; `<extra>` là box thừa. Xem `local_quality_confusion.csv`.

| Reference \ Export | Bike | Car | Pedestrian | ThreeWheeler | <missing> |
|---|---:|---:|---:|---:|---:|
| Bike | 4 | 0 | 0 | 0 | 0 |
| Car | 0 | 2 | 0 | 0 | 1 |
| Pedestrian | 0 | 0 | 7 | 0 | 0 |
| ThreeWheeler | 0 | 6 | 0 | 0 | 0 |
| <extra> | 1 | 2 | 0 | 0 | 0 |

Chi tiết xung đột trong `local_quality_conflicts.csv`; dữ liệu máy đọc trong `local_quality.json`.
Mismatching label đóng góp một FP cho class vẽ và một FN cho class reference; attribute khác được báo riêng.
Micro accuracy đếm mỗi cặp ghép sai class là một lần đối chiếu; Jaccard đếm cả FP và FN.
Macro/worst bỏ nhãn không xuất hiện ở cả hai phía; chỉ số không có mẫu là N/A.

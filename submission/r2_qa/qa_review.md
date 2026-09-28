# QA review · B3-center

Mã khóa: 673A-7072
Người soát (reviewer): Tuân (tuan)
Người gán nhãn gốc (annotator):nhi (B3-center)

| frame              | object_ref            | rule_id | nhận xét                                                                                                                                                                                                                                         |
| --------------------| -----------------------| ---------| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| adasind_152940.jpg | BOX Truck (xtl=326)   | R04     | Box bao phương tiện nhỏ bên trái, nhìn tọa độ (326,810)–(389,863) — chiều ngang chỉ 63px, dáng hẹp, có thể là xe ba bánh hoặc xe máy tải nhỏ. Đề nghị zoom kỹ để xác nhận có phải Truck hay nên là `ThreeWheeler`.                               |
| adasind_152940.jpg | POLY Bike, POLY Truck | R02     | Có 2 Polygon mang nhãn `Bike` và `Truck` thay vì nhãn `ignore_region` — polygon dùng để bao vùng loại trừ (R06) hoặc hỗ trợ bố cục, không nên gán nhãn phương tiện bằng polygon. Nếu đây là vật thể cần box thì phải vẽ thêm bounding box riêng. |
| adasind_212280.jpg | BOX Car (xtl=0)       | R05     | Box Car ở rìa trái (0,765)–(134,1084) bị cắt hoàn toàn bởi mép ảnh, `truncated=true` đã được đánh dấu đúng. Tuy nhiên cần kiểm tra xem đây có phải xe ba bánh không (R04), vì phần nhìn thấy rất hẹp và nằm ở vùng méo fisheye nặng.             |
| adasind_212280.jpg | BOX Bike (xtl=297)    | R05     | Box Bike (297,845)–(368,1047), chiều cao 202px, `occluded=false` nhưng nhìn tọa độ cho thấy vật thể nằm giữa ảnh có thể bị xe khác che khuất một phần — đề nghị soát lại attribute `occluded`.                                                   |
| adasind_167700.jpg | BOX Bike trunc=true   | R02     | Box Bike (758,732)–(1080,1434) bị cắt nặng ở mép phải, `truncated=true` đúng. Tuy nhiên chiều rộng rất lớn (322px), có thể ôm thêm cả rider đang ngồi — kiểm tra xem có cần tách box theo R03 không.                                             |

Mẫu (pattern) chung nhận thấy: Annotator có xu hướng sử dụng Polygon để gán nhãn phương tiện thay vì bounding box (vi phạm quy trình — polygon chỉ dùng cho `ignore_region`). Ngoài ra cần soát kỹ hơn attribute `occluded` ở vùng xe đông đúc (dense).

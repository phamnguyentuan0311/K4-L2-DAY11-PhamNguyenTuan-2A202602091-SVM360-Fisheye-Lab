# Phân tích lỗi theo zone (Center / Mid / Edge)

- Zone nào người (L) và model (M) gãy nhiều nhất, dẫn số ở bảng trên: Zone `Mid` (Model có 10 ca Spurious, 3 ca Missing) và Zone `Edge` (Người có 6 ca Missing).
- Giả thuyết vì sao (méo fisheye, box lỏng, thiếu `ego_body`, ...) và giới hạn của slice ba frame:
  1. Zone Edge bị méo quang học nặng nhất, vật thể bị kéo dãn khiến người gán nhãn bỏ sót, còn Model thì nhận diện sai (Spurious).
  2. Zone Mid thường là nơi xe cộ/người đi bộ bắt đầu đi vào điểm mù của `ego_body` hoặc bị chồng lấn (occlusion).
  Giới hạn: Slice 3 frame không đủ để kết luận đây là lỗi hệ thống cố hữu của Model, cần kiểm thử thêm trên tập validation lớn hơn.

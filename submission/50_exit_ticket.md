# Exit Ticket Day 11

1. Sau khi xem compare và confusion matrix, bạn thấy một luật (rule) nào bạn tưởng đã hiểu rõ nhưng hóa ra bạn áp dụng khác với reference hoặc nguyên tắc chung?
   - Tôi từng nghĩ cứ vật nào bị che là đánh dấu `truncated`. Sau bài này tôi mới rõ `truncated` chỉ dùng khi bị cắt bởi KHUNG HÌNH / VIỀN ỐNG KÍNH, còn bị vật khác che thì phải là `occluded`.
2. Tracking (identity) trong một camera: thế nào là một xe mới (new track), thế nào là xe cũ ra khỏi tầm nhìn (Outside)? Nêu bằng chứng sẽ cần trước khi nối track qua hai camera.
   - Xe mới là xe xuất hiện từ rìa ảnh vào. Xe Outside là xe đã di chuyển khuất hẳn sau `ego_body` hoặc biến mất khỏi viền ảnh. Để nối track qua hai camera, bắt buộc phải có timestamp (thời gian đồng bộ) và thông số hiệu chuẩn camera (calibration matrix) để chứng minh tọa độ 3D của 2 box là của cùng 1 xe.
3. Nhìn lại phần tự làm (r1_craft / B4-dense) và bảng local quality, có ca nào bạn nghĩ mình đã làm sai và nếu làm lại bạn sẽ đổi gì trong cách làm?
   - Tôi đã vẽ sót khá nhiều object nhỏ ở vùng rìa (Edge). Nếu làm lại, tôi sẽ zoom kỹ vào khu vực sát `lens_border` và giảm độ tương phản của ảnh xuống để soi các vật thể tối màu đang nằm lẫn vào vùng méo.

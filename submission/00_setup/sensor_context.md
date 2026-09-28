# Sensor context

- Rig: Camera được gắn xung quanh xe (như cản trước, đuôi xe, và dưới 2 gương chiếu hậu) để tạo thành hệ thống nhìn toàn cảnh 360 độ (SVM).
- `ego_body` nhìn thấy ở khu vực rìa dưới hoặc mép cạnh của frame (hiện rõ một phần cản xe, biển số hoặc sườn xe).
- Vòng kính (lens circle) có dạng hình tròn nằm ở trung tâm ảnh, chiếm phần lớn khung hình với bốn góc ngoài cùng thường có vùng đen (do giới hạn trường nhìn của thấu kính fisheye).

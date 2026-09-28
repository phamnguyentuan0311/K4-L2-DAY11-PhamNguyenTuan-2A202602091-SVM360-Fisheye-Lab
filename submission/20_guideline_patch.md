# Đề xuất vá luật (Guideline Patch)

- **Rule mới đề xuất:** R12 — Xử lý vật thể bị che khuất bởi vùng loại trừ. Nếu một phương tiện bị che khuất >50% bởi `ego_body` nhưng vẫn nhận diện rõ đó là xe, bọc bounding box cho toàn bộ phần diện tích có thể nhìn thấy và đánh dấu `occluded = true`.
- **Áp dụng cho:** Tất cả các class phương tiện giao thông (Car, Bus, Truck, Bike).
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** Luật hiện tại R09 chỉ cấm vẽ box nếu vật nằm ≥50% trong polygon ignore, dẫn đến việc bỏ sót các xe đi sát ngay cạnh cản xe (ego body), rất nguy hiểm cho hệ thống ADAS.
- **`rules_version` mới:** v1.1.0
- **Hiệu lực từ:** Round R4 (Rework tiếp theo)

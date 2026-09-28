# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B4 | MISSING | 11 |
| center | B4 | SPURIOUS | 5 |
| center | C0 | MISSING | 3 |
| edge | B4 | MISSING | 11 |
| edge | B4 | SPURIOUS | 1 |
| edge | C0 | MISSING | 1 |
| mid | B4 | MISSING | 13 |
| mid | B4 | SPURIOUS | 10 |
| mid | C0 | MISSING | 2 |

## Top defects
- MISSING: 41 (ví dụ frame adasind_019560.jpg)
- SPURIOUS: 16 (ví dụ frame adasind_258420.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: Vật thể nằm ở góc ảnh bị méo fisheye nên annotator bỏ sót (MISSING).
- Cách sửa và ai nhận việc (`owner`): Cần vẽ bổ sung box bám sát viền. Owner: annotator.
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): ![Minh chứng](../screenshots/2.png)

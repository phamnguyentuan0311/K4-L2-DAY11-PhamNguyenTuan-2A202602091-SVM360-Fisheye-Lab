# So sánh L với R

Chỉ số L/R là thứ tự box cao ≥ H=40 trong từng frame, theo thứ tự XML; bắt đầu từ 1.
Box L trong ignore_region được báo IGNORE_SCOPE, không tính SPURIOUS.

## adasind_258420.jpg
- L1+R4 center WRONG_CLASS
- L2+R8 center WRONG_CLASS
- L3+R5 mid BOX_GEOMETRY
- L7+R1 edge WRONG_CLASS
- L9 mid SPURIOUS
- L10 mid SPURIOUS
## adasind_270517.jpg
- L5 mid IGNORE_SCOPE
- L6+R3 edge ATTRIBUTE
- L2+R4 center WRONG_CLASS
- L8+R2 center WRONG_CLASS
## adasind_310008.jpg
- L4+R1 mid WRONG_CLASS

## Theo zone
| zone | n_ref | matched | missing | spurious |
|---|---|---|---|---|
| center | 6 | 2 | 4 | 4 |
| mid | 7 | 5 | 2 | 4 |
| edge | 7 | 6 | 1 | 1 |

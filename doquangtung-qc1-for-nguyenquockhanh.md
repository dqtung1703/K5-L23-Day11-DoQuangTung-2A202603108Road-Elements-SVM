# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Nguyễn Quốc Khánh (`nguyenquockhanh`)        Người kiểm (học viên): Đỗ Quang Tùng (`doquangtung`)  
Ngày: 2026-11-21                          Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): `nguyenquockhanh-front.zip`, `nguyenquockhanh-fisheye.zip` (revision 1)  
Số ảnh kiểm: 6 (`A01`, `A02`, `A08`, `A11`, `B02`, `B04`) (+ 0 ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag): 108 (84 shape + 24 tag)  

*(Ghi chú: ảnh `A02` được kiểm đầy đủ 10 nhãn = 6 shape + 4 tag và ghi nhận **không lỗi**).*

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 24 | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 10 | 1 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 14 | 3 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 14 | 0 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 14 | 1 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 14 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 30 | 0 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 21 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 35 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 14 | 1 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 24 | 10 | chính |
| QC1-12 file | lỗi file | 108 | 1 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-03 | A01 | `lane#2@(1280,707)` | nặng | Vạch vàng liền sát lề phải gán sai `position = R1` (đúng là `R2`, bị trùng `R1` với `lane#1`). |
| 2 | QC1-03 | A01 | `lane#3@(0,599)` | nặng | Vạch trắng đôi sát mép trái gán sai `position = L1` (đúng là `L2`, trùng `L1` với `lane#5`). |
| 3 | QC1-03 | A01 | `lane#8@(0,603)` | nặng | Vẽ trùng thêm một polyline nữa cho cùng vạch trắng đôi sát mép trái và gán sai `position = L1`. |
| 4 | QC1-05 | A08 | `lane#22@(764,449)` + `lane#23@(653,319)` | chính | Vạch `R1` bị tách thành 2 polyline cùng `position = R1` (một đoạn `dashed`, một đoạn `solid`). |
| 5 | QC1-10 | A08 | `traffic_sign` (phía trên `#4@(754,61)`) | chính | Thiếu hộp riêng cho biển phụ *"PASSENGER CARS ONLY"* (`group = supplementary`) gắn phía trên biển chỉ dẫn xanh lá. |
| 6 | QC1-02 | A11 | `lane` (thiếu `L1`) | nặng | Bỏ sót vạch vàng đôi sát bên trái làn xe đang đi (`L1`) dù vạch hiện rất rõ trên ảnh. |
| 7 | QC1-12 | B02 | `road_curb#7@(1187,660)` | nhẹ | Có 1 điểm lặp liền nhau (do click đúp), cần xóa điểm thừa. |
| 8 | QC1-11 | B02 | `road_curb#8@(133,672)` | chính | Polyline trên ảnh fisheye chỉ có 3 điểm, chưa đủ điểm bám theo cung cong. |
| 9 | QC1-11 | B02 | `road_curb#9@(66,591)` | chính | Polyline trên ảnh fisheye chỉ có 3 điểm, chưa đủ điểm bám theo cung cong. |
| 10 | QC1-11 | B02 | `road_curb#12@(423,397)` | chính | Polyline trên ảnh fisheye chỉ có 2 điểm thẳng, không đi theo cung cong. |
| 11 | QC1-11 | B02 | `road_curb#13@(530,386)` | chính | Polyline trên ảnh fisheye chỉ có 2 điểm thẳng, không đi theo cung cong. |
| 12 | QC1-11 | B02 | `traffic_light#0@(109,114)` | chính | Tâm box nằm ngoài 80% bán kính vòng ảnh fisheye nhưng chưa bật `edge_zone = true`. |
| 13 | QC1-11 | B02 | `traffic_light#1@(63,63)` | chính | Tâm box nằm ngoài 80% bán kính vòng ảnh fisheye nhưng chưa bật `edge_zone = true`. |
| 14 | QC1-11 | B02 | `traffic_light#2@(1076,77)` | chính | Tâm box nằm ngoài 80% bán kính vòng ảnh fisheye nhưng chưa bật `edge_zone = true`. |
| 15 | QC1-11 | B02 | `traffic_light#3@(1097,22)` | chính | Tâm box nằm ngoài 80% bán kính vòng ảnh fisheye nhưng chưa bật `edge_zone = true`. |
| 16 | QC1-11 | B04 | `traffic_sign#1@(1065,170)` | chính | Tâm box biển cấm nằm ngoài 80% bán kính vòng ảnh fisheye nhưng chưa bật `edge_zone = true`. |
| 17 | QC1-11 | B04 | `traffic_light#3@(105,314)` | chính | Tâm box đèn giao thông nằm ngoài 80% bán kính vòng ảnh fisheye nhưng chưa bật `edge_zone = true`. |

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| A08 | Tag `weather` của ảnh A08 nên chọn `clear` hay `overcast` (trời nhiều mây sáng, đường khô)? | Chưa cần Hold vì lô đã Rework do lỗi nặng ở A01, A11 và tỉ lệ lỗi chính > 5 %. |

## Quyết định
Lỗi nặng: 4   Lỗi chính: 12 / 108 nhãn = 11.1 %   Lỗi nhẹ: 1   Ca chờ lead: 0  
Quyết định (Release / Hold / Rework): **Rework**  
Lý do (theo luật của phiếu): Có 4 lỗi nặng (`QC1-02` thiếu `L1` ở A11; `QC1-03` sai/trùng `position` ở A01) và tỉ lệ lỗi chính `12 / 108 = 11.1 %` vượt ngưỡng `5 %` nên theo luật bắt buộc trả về **Rework**.  

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](docs/qc_severity_road_v1.0.md).

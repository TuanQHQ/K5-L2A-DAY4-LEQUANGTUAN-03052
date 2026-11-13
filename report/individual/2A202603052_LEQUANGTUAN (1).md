# BÁO CÁO CÁ NHÂN — NGÀY 04: KEYPOINT & POSE

**Học viên:** Lê Quang Tuấn  
**MSSV:** 2A202603052  
**Lớp:** K5-L2A  
**Repository:** https://github.com/TuanQHQ/K5-L2A-DAY4-LEQUANGTUAN-03052  
**Dữ liệu kiểm tra:** `LEQUANGTUAN_persons.zip`, `LEQUANGTUAN_faces.zip` người học cung cấp.

> **Tình trạng: Bản báo cáo dựng từ dữ liệu ZIP thật, chưa đủ điều kiện nộp hoàn chỉnh.**
> Những chỗ ghi `[TỰ ĐIỀN]` cần xác nhận bằng thao tác thực tế. Không tự điền thông số giả, không tạo chứng cứ giả. Đặc biệt, **danh sách ảnh trong hai ZIP không khớp ảnh được giao theo MSSV này** (xem mục 5).

## 0. Thông tin học viên

| Trường thông tin | Giá trị |
|---|---|
| Họ tên | Lê Quang Tuấn |
| MSSV | 2A202603052 |
| Lớp | K5-L2A |
| Email | [TỰ ĐIỀN] |
| Link repository | https://github.com/TuanQHQ/K5-L2A-DAY4-LEQUANGTUAN-03052 |
| Hệ điều hành | Windows (theo môi trường thực hành) |
| Phiên bản Python dùng khi kiểm tra cục bộ | Python 3.15 (qua lệnh `py`) |
| RAM | [TỰ ĐIỀN] GB |
| Phiên bản CVAT (Help → About) | [TỰ ĐIỀN] |
| CVAT cục bộ / lite | [TỰ ĐIỀN, chỉ ghi đúng môi trường đã dùng] |
| `src/exports/assignment.json` do `lab.py setup` tạo | Chưa được cung cấp để xác minh |
| Giờ bắt đầu / kết thúc | [TỰ ĐIỀN THỜI GIAN THẬT] |

## 1. Kiểm tra label (CP0)

Kiểm tra dựa trên **schema thực tế trong hai file COCO export** (không thay cho ảnh chụp label constructor trên CVAT):

| Label | Kiểu | Số điểm | Tên điểm đúng bộ schema? | Thứ tự theo bộ schema? | Số cạnh |
|---|---|---:|---|---|---:|
| `person` | Skeleton | 17 | Có, theo bản export | Có, theo bản export | 19 |
| `face` | Skeleton | 13 | Có, theo bản export | Có, theo bản export | 13 |

- `person`: 17 điểm bắt đầu từ `nose`, `left_eye`, `right_eye` và kết thúc ở `left_ankle`, `right_ankle`.
- `face`: 13 điểm gồm các điểm mắt trái/phải, `nose_tip`, hai khóe miệng và hai điểm môi.
- Skeleton mẫu người quay mặt về camera, `left_*` nằm bên phải khung mẫu: **[TỰ XÁC NHẬN TRÊN CVAT]**.
- Cách bật `occluded` / `outside` cho một điểm trên phiên bản CVAT đã sử dụng: **[TỰ GHI LẠI THAO TÁC ĐÃ LÀM]**.

Quy ước cờ dùng trong bài: `v = 2` là nhìn thấy rõ; `v = 1` là bị che nhưng có thể ước lượng; `v = 0` là ngoài ảnh hoặc không thể xác định.

## 2. Số lượng đã gán và thời gian (CP1–CP2)

**Số liệu được đếm từ file JSON trong ZIP, không phải số liệu ước lượng:**

| Nhóm ảnh | Số ảnh | Số skeleton đã gán | Người dưới 60 px bỏ qua | Poster/gương/màn hình bỏ qua | Thời gian (phút) |
|---|---:|---:|---|---|---|
| `easy` | 5 | 5 | Chưa kiểm | Chưa kiểm | Chưa ghi |
| `occluded` | 3 | 7 | Chưa kiểm | Chưa kiểm | Chưa ghi |
| `back` | 2 | 4 | Chưa kiểm | Chưa kiểm | Chưa ghi |
| `small` | 1 | 1 | Chưa kiểm | Chưa kiểm | Chưa ghi |
| `crowd` | 1 | 3 | Chưa kiểm | Chưa kiểm | Chưa ghi |
| `faces` | 8 | 8 | — | Chưa kiểm | Chưa ghi |
| **Tổng** | **20** | **28** | — | — | — |

Thống kê visibility xuất từ JSON:

| Nhóm | `v = 0` | `v = 1` | `v = 2` | Tổng điểm |
|---|---:|---:|---:|---:|
| Người | 71 | 19 | 250 | 340 |
| Mặt | 9 | 0 | 95 | 104 |

- Số ảnh người đã xong tại mốc phút 105: [TỰ ĐIỀN] / 10.
- Thời gian thực tế CP1 / CP2 / CP3: [TỰ ĐIỀN] / [TỰ ĐIỀN] / [TỰ ĐIỀN] phút.
- Ảnh tốn thời gian nhất và lý do: [TỰ ĐIỀN THEO TRẢI NGHIỆM].

## 3. Bảng ca khó (CP1–CP2)

**Bắt buộc học viên tự xác nhận từ job thật.** Gợi ý những ảnh có nhiều điểm `v = 0` trong file xuất để kiểm lại; điều này *không có nghĩa* tự động là ca khó đã gặp.

| Ảnh cần xem lại | Người / mặt | Điểm đã cân nhắc | Cờ đã chọn | Phân vân giữa | Lý do chọn |
|---|---|---|---|---|---|
| `000000461389.jpg` | [TỰ ĐIỀN] | [TỰ ĐIỀN] | [ ] | `v=1` / `v=0` | [TỰ ĐIỀN] |
| `000000381889.jpg` | [TỰ ĐIỀN] | [TỰ ĐIỀN] | [ ] | [ ] | [TỰ ĐIỀN] |
| `face_256814.jpg` | [TỰ ĐIỀN] | [TỰ ĐIỀN] | [ ] | `v=1` / `v=0` | [TỰ ĐIỀN] |

## 4. Bảng tự review (CP3)

Theo quy định, phải tự review **5 ảnh người** (tối thiểu 2 ảnh `back` hoặc `crowd`) và **3 ảnh mặt**. Các ảnh được chọn sẵn dưới đây là ảnh có thật trong ZIP; **mã lỗi và nhận xét cần điền sau khi tự xem lại**.

| Ảnh | Người / mặt | Điểm | Mã lỗi | Ghi chú từ việc tự review | Đã sửa? |
|---|---|---|---|---|---|
| `000000043500.jpg` (`back`) | [ ] | [ ] | [ ] | [TỰ ĐIỀN] | [ ] |
| `000000311300.jpg` (`back`) | [ ] | [ ] | [ ] | [TỰ ĐIỀN] | [ ] |
| `000000381889.jpg` (`crowd`) | [ ] | [ ] | [ ] | [TỰ ĐIỀN] | [ ] |
| `000000091637.jpg` (`occluded`) | [ ] | [ ] | [ ] | [TỰ ĐIỀN] | [ ] |
| `000000162046.jpg` (`easy`) | [ ] | [ ] | [ ] | [TỰ ĐIỀN] | [ ] |
| `face_256814.jpg` (`kinh_ram`) | [ ] | [ ] | [ ] | [TỰ ĐIỀN] | [ ] |
| `face_415073.jpg` (`nghieng`) | [ ] | [ ] | [ ] | [TỰ ĐIỀN] | [ ] |
| `face_105668.jpg` (`nghieng`) | [ ] | [ ] | [ ] | [TỰ ĐIỀN] | [ ] |

Mã lỗi hợp lệ: `lr_swap`, `vis_flag`, `position`, `missing`, `extra`, `ok`.

| `lr_swap` | `vis_flag` | `position` | `missing` | `extra` | `ok` |
|---:|---:|---:|---:|---:|---:|
| [TỰ ĐẾM] | [TỰ ĐẾM] | [TỰ ĐẾM] | [TỰ ĐẾM] | [TỰ ĐẾM] | [TỰ ĐẾM] |

Điểm còn phân vân giữa `v = 1` và `v = 0`, cùng lý do đưa ra quyết định: [TỰ ĐIỀN].

## 5. Kiểm file xuất và kết quả tự kiểm (CP4)

**Đã kiểm tra độc lập dữ liệu ZIP được cung cấp:**

- Hai ZIP đều có file `annotations/person_keypoints_default.json` và đều đọc JSON được.
- ZIP `persons` có **12 bản ghi ảnh** và **20 annotation** thuộc label `person`.
- ZIP `faces` có **8 bản ghi ảnh** và **8 annotation** thuộc label `face`.
- Mỗi annotation người có **51 phần tử** trong `keypoints`, mỗi annotation mặt có **39 phần tử**.
- Các cờ `v` đều thuộc tập {0, 1, 2}.
- Với mọi annotation, trường `num_keypoints` khớp số điểm có `v > 0`.
- Không phát hiện điểm có `v > 0` với tọa độ nằm ngoài kích thước ảnh.
- Hai ZIP **không kèm JPG/PNG** (đã bỏ ảnh gốc khi export).
- Tổng cộng **80 điểm** có `v = 0` nhưng JSON vẫn giữ tọa độ khác `(0,0)`; đây là đặc điểm có thể gặp khi xuất từ CVAT, không tự sửa JSON.

Kiểm tay 3 annotation làm mẫu:

| File | Ảnh / annotation | Số phần tử `keypoints` | `num_keypoints` thực tế | Cờ / cấu trúc hợp lệ? |
|---|---|---:|---:|---|
| `LEQUANGTUAN_persons.zip` | `000000043500.jpg` / id 1 | 51 | 12 | Có |
| `LEQUANGTUAN_persons.zip` | `000000580257.jpg` / id 19 | 51 | 16 | Có |
| `LEQUANGTUAN_faces.zip` | `face_256814.jpg` / id 4 | 39 | 5 | Có về cấu trúc; **cần xem lại cờ mắt** |

**Vấn đề cần khắc phục trước khi nộp:**

1. **Ảnh không đúng bộ theo MSSV.** So sánh với danh sách do thuật toán trong `lab.py` chọn cho MSSV `2A202603052`: **12/12 ảnh người và 7/8 ảnh mặt trong ZIP không thuộc bộ được giao.** Thiếu file `src/exports/assignment.json` thật để xác minh cách tạo task. **Không đổi tên ảnh, không sửa tay JSON để làm khớp**; cần chạy lại `lab.py setup` đúng MSSV và làm trên bộ ảnh của mình nếu coach yêu cầu.
2. **Ảnh kính râm `face_256814.jpg`:** 8/13 điểm mặt đang có `v=0`, trong khi hướng dẫn khuyến nghị các điểm mắt bị kính râm tối che nhưng vẫn suy ra được thường dùng `occluded (v=1)`. Cần mở CVAT xem lại ảnh thật và mức độ xác định được điểm trước khi sửa.
3. **Kết quả script kiểm chính thức:** chưa có log từ `py src/check_submission.py`. Kết quả kiểm độc lập ở trên **không đồng nghĩa** thông báo chính thức `Kết quả: ĐẠT`.

Dán nguyên văn phần TÓM TẮT từ script khi đã chạy:

```text
[CHƯA CÓ OUTPUT THẬT — DÁN SAU KHI CHẠY SCRIPT]
```

Trạng thái 2 Job trên CVAT: [TỰ XÁC NHẬN — completed / chưa completed].

## 6. Ảnh chụp màn hình (4 minh chứng)

> **Chưa có ảnh chụp giao diện CVAT thật trong hai file ZIP nhận được.** Các hình minh họa dựng từ JSON không thay thế ảnh chụp màn hình. Sau khi tự chụp, lưu bốn file PNG đúng tên trong `report/individual/images/`.

1. Label `person` đủ 17 điểm trong CVAT:

   ![Label person](images/1_label_person.png)

2. Người quay lưng với skeleton và cờ trong CVAT:

   ![Người quay lưng](images/2_nguoi_quay_lung.png)

3. Khuôn mặt với 13 điểm, phóng to khu vực mắt:

   ![Khuôn mặt](images/3_mat_phong_to.png)

4. Một đoạn JSON export, thấy `keypoints` và `num_keypoints`:

   ![JSON export](images/4_json_export.png)

Nguồn ảnh theo đề: COCO val2017 và Wikimedia Commons, dùng trong lớp.

## 7. Tự đánh giá (học viên tự viết sau khi review)

1. **Lỗi bản thân mắc nhiều nhất và cách phòng tránh trong dự án thật:** [TỰ ĐÁNH GIÁ]
2. **Quy tắc muốn bổ sung vào guideline (có ví dụ cụ thể):** [TỰ ĐÁNH GIÁ]
3. **Một lỗi bản thân đã sửa và tác động của nó lên model (heatmap, loss hoặc lật ảnh):** [TỰ ĐÁNH GIÁ]

## 8. Khó khăn và lỗi kỹ thuật

**Sự cố đã xuất hiện trong quá trình thao tác thực tế trên Windows:**

- Gõ `python` trong PowerShell có lúc báo `Python was not found`; sau đó chạy được qua lệnh `py`.
- Lệnh `py lab.py` chạy từ `C:\WINDOWS\system32` bị lỗi không tìm thấy `lab.py`.
- Lệnh `py lab.py` tiếp tục báo không tìm thấy file khi Terminal đặt ở thư mục chưa chứa `lab.py`.
- Đã được hướng dẫn mở đúng thư mục bằng VS Code → Terminal, tìm `lab.py`, sau đó chạy kiểm tra và setup theo MSSV.

**Cách xử lý thực tế sau cùng, trạng thái Docker/CVAT và các lỗi phát sinh khi annotation hoặc export:** [TỰ ĐIỀN/XÁC NHẬN].

## Bonus (nếu thực hiện)

- B1 — Ba ảnh người khó thêm: **Chưa có dữ liệu bonus được cung cấp**.
- B2 — Năm ảnh mặt đen trắng/hồng ngoại: **Chưa có dữ liệu bonus được cung cấp**.
- B3 — So sánh với model: **Chưa có dữ liệu bonus được cung cấp**.

## 9. Tài liệu tham khảo và công cụ AI đã sử dụng

1. Đề Lab Ngày 4 — Keypoint Pose: `README.md`, `CHECKPOINTS.md`, `RUBRIC.md`, `RULES.md`, `SUBMISSION.md` trong repository bài tập.
2. Quy chuẩn gán nhãn: `docs/GUIDELINE.md`; cấu trúc COCO: `docs/COCO_KEYPOINTS.md`.
3. Bộ dữ liệu học tập: COCO val2017 / Wikimedia Commons theo thông tin đề bài.
4. **ChatGPT:** hỗ trợ cách chạy Python/VS Code và CVAT; đọc thống kê cấu trúc từ hai ZIP; tạo bố cục và chỉnh câu chữ của báo cáo. ChatGPT **không gán thêm keypoint và không điền thay đánh giá cá nhân**.

---

### Kiểm tra cuối trước khi gửi LMS

- [ ] Có `src/exports/assignment.json` được tạo tự động cho MSSV đúng.
- [ ] Đã xác nhận bộ ảnh trong hai ZIP đúng MSSV.
- [ ] Đã tự review 5 ảnh người và 3 ảnh mặt; điền đủ mục 3, 4, 7.
- [ ] Có 4 ảnh màn hình CVAT thật trong `report/individual/images/`.
- [ ] Chạy script tự kiểm chính thức; sửa lỗi hoặc ghi lý do cảnh báo.
- [ ] Hai Job chuyển `completed` trên CVAT.
- [ ] Repo đã có đủ ZIP và báo cáo tại đúng đường dẫn; không tải ảnh gốc hoặc mật khẩu lên GitHub.

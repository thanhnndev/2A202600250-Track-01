# Template — Bảng chấm điểm chọn Quick Win nhanh

> Dùng cùng `worksheet/01-frame/2-quick-win.md`. Mục đích: so sánh các use case để chọn lát cắt làm trước. **Điểm là gợi ý, không phải đáp án** — quyết định vẫn là của nhóm.

---

## 4 trục chấm (mỗi trục 1–5)

| Trục | Hỏi gì | 1 điểm | 5 điểm |
|---|---|---|---|
| **Tác động (Impact)** — trọng số 30% | Nếu làm được, đỡ pain lớn cỡ nào? | Pain nhỏ, ít người | Pain lớn, nhiều người, thường xuyên |
| **Khả thi (Feasibility)** — 25% | Làm được trong pilot nhỏ, ngân sách nhỏ, dữ liệu sẵn? | Cần platform lớn / dữ liệu chưa có | Dùng tool/API sẵn, dữ liệu mẫu là đủ |
| **Bằng chứng nhanh (Evidence)** — 25% | Chứng minh có/không hiệu quả trong ~1–2 tuần? | Phải nhiều tháng mới biết | Thấy kết quả trong 1–2 tuần |
| **Rủi ro nếu sai (Risk)** — 20% | *Điểm cao = rủi ro THẤP* | Sai → mất uy tín / điểm sai / mất trust | Sai cũng không gây hậu quả lớn |

> Lưu ý trục **Rủi ro đảo chiều**: an toàn = điểm cao. Nhớ kỹ khi điền.

---

## Cách tính tổng

```text
Tổng = Impact×0.30 + Feasibility×0.25 + Evidence×0.25 + Risk×0.20
```

Không cần tính chính xác đến số lẻ — chỉ cần đủ để xếp hạng tương đối.

---

## Bảng điền (copy vào worksheet/01-frame/2-quick-win.md nếu cần)

| Use case | Impact (×.30) | Feasibility (×.25) | Evidence (×.25) | Risk an toàn (×.20) | Tổng | Hạng |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| | | | | | | |
| | | | | | | |
| | | | | | | |
| | | | | | | |
| | | | | | | |

---

## Ví dụ minh họa (KHÔNG phải đáp án — chỉ cho thấy cách điền)

> Track giả định: AI Lab Copilot. Đây là ví dụ cách dùng bảng, không phải lựa chọn đúng cho nhóm bạn.

| Use case | Impact | Feasibility | Evidence | Risk an toàn | Tổng | Hạng |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| Review bài nộp trước khi submit (thiếu chỉ số/ngân sách?) | 4 | 5 | 5 | 4 | 4.45 | 1 |
| Hint bot không cho đáp án | 4 | 4 | 4 | 3 | 3.80 | 2 |
| Code/debug assistant cho 1 lab kỹ thuật | 5 | 2 | 3 | 2 | 3.05 | 3 |

Đọc bảng: dòng 1 thắng không phải vì tác động cao nhất, mà vì **khả thi + bằng chứng nhanh + an toàn** — đúng tinh thần Quick Win.

---

## Sau khi chấm — bắt buộc tự hỏi

```text
- Use case điểm cao nhất có người trong AI20k ỦNG HỘ không? (ủng hộ > điểm)
- Nhóm có đang thiên vị cái QUEN / cái DỄ DEMO không?
- Nếu fail — hậu quả gì? Quay lại được không?
```

Điểm chỉ giúp **so sánh**. Lý do chọn (viết ở `worksheet/01-frame/2-quick-win.md`) mới là thứ bị chấm ở Cổng 2.

---

*Template Quick Win scoring · D28.*

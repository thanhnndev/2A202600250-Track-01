---
artifact: 3 — Quick Win Selection
bai-tap: Frame — chọn lát cắt làm trước
phase: Double Diamond vòng 1 · ◆ siết
input: 1-intake-breakdown.md · BEETUTOR-MARKETPLACE.md
nop-cuoi: Không — file trung gian
---

# 2 — Quick Win: chọn lát cắt làm trước

## Phần A — Chấm điểm 4 trục (1-5 mỗi trục)

| Use case | Impact | Feasibility | Evidence nhanh | Risk (cao = an toàn) | Tổng |
|---|:--:|:--:|:--:|:--:|:--:|
| Chuẩn hóa intake học viên/phụ huynh | 4 | 5 | 4 | 5 | 18 |
| Tạo top 3 shortlist gia sư có lý do | 5 | 4 | 4 | 3 | 16 |
| Phát hiện thông tin thiếu/mâu thuẫn | 4 | 5 | 5 | 5 | 19 |
| Tóm tắt hồ sơ gia sư thành card có nguồn | 4 | 4 | 4 | 4 | 16 |
| Gợi ý giá/thời lượng phù hợp | 3 | 3 | 3 | 3 | 12 |
| Kiểm tra hồ sơ gia sư đủ giấy tờ | 5 | 3 | 4 | 2 | 14 |

## Phần B — 1 lý do nên / 1 lý do không, cho top 2

**Ứng viên A — Phát hiện thông tin thiếu/mâu thuẫn trong intake**

```text
Nên chọn vì: rất khả thi, giảm hỏi đi hỏi lại, ít rủi ro vì AI chỉ flag thiếu dữ liệu thay vì quyết định matching.
Không nên vì: impact nhìn thấy với phụ huynh thấp hơn shortlist; chưa chứng minh được giá trị cốt lõi "kết nối đúng gia sư".
```

**Ứng viên B — Tạo top 3 shortlist gia sư có lý do**

```text
Nên chọn vì: chạm đúng core marketplace: giúp phụ huynh thấy 3 lựa chọn phù hợp thay vì tự lọc quá nhiều biến.
Không nên vì: rủi ro cao hơn; cần guardrail mạnh, nguồn từ hồ sơ, và ops review trước khi gửi.
```

## Phần C — Chốt Quick Win

- **Quick Win tôi chọn**: AI tạo top 3 shortlist gia sư Toán THPT cho một yêu cầu học viên/phụ huynh, kèm lý do phù hợp và flag dữ liệu thiếu/rủi ro để ops review.
- **Vì sao chọn cái này trước**: Đây là lát cắt chứng minh trực tiếp giá trị của BEETUTOR Marketplace: kết nối đúng người học với đúng gia sư. Điểm feasibility đủ cao vì có thể dùng hồ sơ gia sư, nhu cầu học viên và rule matching rõ ràng từ outline. Dù risk thấp hơn intake-only, rủi ro được giảm bằng human review và citation từ hồ sơ.
- **Ai trong BEETUTOR sẽ ủng hộ pilot này**: Ops/CS phụ trách tư vấn gia sư sẽ ủng hộ vì họ giảm thời gian lọc hồ sơ và có lý do rõ để giải thích cho phụ huynh. Phụ huynh cũng care vì nhận ít lựa chọn hơn nhưng có giải thích cụ thể.
- **Tôi KHÔNG chọn gì + vì sao**: 1. Không chọn build full marketplace vì quá rộng, cần UI, thanh toán, booking, verification, review, tracking cùng lúc. 2. Không chọn kiểm tra giấy tờ gia sư trước vì quan trọng nhưng rủi ro pháp lý cao và cần quy trình xác minh thật. 3. Không chọn gợi ý giá vì có thể gây tranh cãi nếu chưa có dữ liệu thị trường đủ tin cậy.

## Phát hiện ban đầu

- Quick Win tốt nhất không phải use case điểm tổng cao nhất; shortlist có core value rõ hơn intake validation.
- Matching phải có hard filters trước khi AI ranking: môn/lớp, hình thức, khu vực, lịch, ngân sách, verification.

## Câu hỏi mở (mang sang Problem Framing)

- Baseline shortlist hiện tại mất bao nhiêu phút/yêu cầu?
- Tỷ lệ phụ huynh đặt học thử sau khi nhận shortlist hiện tại là bao nhiêu?
- Cần bao nhiêu trường hồ sơ bắt buộc để được đưa vào shortlist?

## Tổng kiểm tra trước khi sang `3-FINAL-problem-framing.md`

| Hạng mục | Xong? |
|---|---|
| Có bảng chấm 4 trục cho >=4 use case | Xong |
| Chốt 1 Quick Win, lý do bám số/impact | Xong |
| Nêu rõ ai ủng hộ pilot này | Xong |
| Ghi rõ >=2 phần KHÔNG chọn + lý do | Xong |

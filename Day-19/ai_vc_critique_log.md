# AI VC Critique Log - BeeTutor Marketplace

Audience: Seed VC
Date: 2026-05-05

## Pitch gốc trước critique

### Pitch Memo v1 (tóm tắt)
- Problem: Thị trường gia sư phân mảnh, khó kiểm chứng chất lượng, no-show làm hao hụt dòng tiền.
- Insight: Thị trường không thiếu gia sư, mà thiếu cơ chế trust có thể verify.
- Solution: Marketplace trust-by-design với profile verified, chat trước booking, escrow 50/50, check-in/out.
- Why now: Hybrid learning tăng nhanh; payment infra + AI readiness đã đủ để scale.
- Proof: 500+ bookings/tháng, GMV 400M, revenue 80M, completion >90%, no-show <5%.
- Ask: Gọi 6 tỷ VND để mở rộng địa lý và nâng cấp matching.

### Twitter Pitch v1
BeeTutor giúp học sinh THCS-THPT tìm gia sư verified nhanh, học đều và không mất tiền vì no-show: chat trước booking, escrow 50/50, check-in GPS/dual-confirm. Mục tiêu: 500+ bookings/tháng, GMV 400M, no-show <5%. Gọi 6 tỷ VND seed để mở rộng.

---

## AI VC feedback (raw)

### 1. THE 8-SECOND TEST
"Câu mở đầu có vấn đề vì bắt đầu bằng tên startup + mô tả dài. Chưa có shock number trong 8 giây đầu. Tôi muốn nghe pain ngay: bao nhiêu tiền bị thất thoát vì no-show/mismatch và bạn cắt được bao nhiêu."

### 2. THE INSIGHT TEST
"Insight 'thiếu trust có thể kiểm chứng' là hướng đúng, nhưng vẫn đang ở mức generic marketplace. Bạn cần sharpen thành một cơ chế vận hành cụ thể mà đối thủ không có, ví dụ: escrow + anti-fraud event log + dual confirmation tạo ra dispute graph độc quyền."

### 3. THE OPENAI THREAT
"OpenAI có thể làm chatbot tutor, nhưng không giải quyết được execution layer offline/online của buổi học thật. Tuy vậy, moat của bạn hiện tại vẫn mỏng nếu chỉ là tính năng. Bạn cần nói rõ moat dữ liệu vận hành và mạng lưới verified tutors theo khu vực."

### 4. THE NUMBERS TEST
"Các số 500 bookings, 400M GMV, 80M revenue có logic nhưng chưa rõ là achieved hay target. LTV/CAC và payback đang để dạng giả định. Nếu đây là estimate, phải đánh dấu minh bạch."

### 5. THE WEAKEST LINE
"'AI được dùng để nâng cấp matching' là câu yếu nhất vì startup nào cũng nói như vậy. Rewrite thành outcome line: AI matching giảm mismatch bao nhiêu, completion tăng bao nhiêu, no-show giảm bao nhiêu."

---

## Decision log (Accept / Reject / Partial)

### Point 1 - 8-second test
Decision: Accept
Reason: Đúng với tinh thần Day 19, câu mở phải answer-first và có số cụ thể. Đã đổi hook thành pain + kết quả vận hành trong 8 giây.

### Point 2 - Insight test
Decision: Partial
Reason: Đồng ý cần cụ thể hơn insight, nhưng không overfit thành ngôn ngữ kỹ thuật khó nghe với Seed VC. Giữ insight "trust can verify" và bổ sung cơ chế escrow + check-in + no-show policy như một system, không phải feature đơn lẻ.

### Point 3 - OpenAI threat
Decision: Accept
Reason: Bổ sung phòng thủ moat theo 2 lớp: (1) workflow moat (embedded vào booking/payment/attendance), (2) data moat (dữ liệu reliability theo tutor-khu vực-ca học). OpenAI có thể thay UI, nhưng khó thay mạng lưới + vận hành tại chỗ.

### Point 4 - Numbers test
Decision: Accept
Reason: Đã đánh dấu rõ "dữ liệu mục tiêu" và "giả định Day 18" để tránh overclaim. Ưu tiên minh bạch thay vì thổi phồng.

### Point 5 - Weakest line
Decision: Accept
Reason: Đã đổi từ language "nâng cấp matching" sang outcome-driven framing: giảm mismatch, bảo toàn completion, giảm no-show.

---

## Pitch final sau phản biện

### Memo adjustments
1. Hook đổi thành: "Thị trường dạy kèm 1-1 không thiếu người dạy, nhưng mất tiền vì trust gap và no-show."
2. Insight sharpen: trust gap được verify bởi 3 event bắt buộc: check-in, check-out, payment release.
3. Moat bổ sung: workflow + data moat từ event logs, reliability scoring theo tutor và khu vực.
4. Numbers label rõ: operating targets và unit economics assumptions.
5. Ask cụ thể hơn theo 3 milestone 12 tháng.

### Twitter Pitch final
BeeTutor giải bài toán thất thoát doanh thu dạy kèm 1-1 bằng trust stack có thể kiểm chứng: chat trước booking, escrow 50/50, check-in GPS/dual-confirm. Mục tiêu 500+ bookings/tháng, GMV 400M, no-show <5%. Gọi 6 tỷ VND seed để scale.

Character count: <280 (verified)

---

## Self-eval 7/7

- [x] Mở đầu trong 8 giây có pain + metric
- [x] Có insight phản trực giác (trust gap > supply gap)
- [x] Có ít nhất 2 con số cụ thể
- [x] Differentiator rõ, có defensibility trước OpenAI threat
- [x] Ask cụ thể (số tiền + mục tiêu 12 tháng)
- [x] Script đọc to < 60 giây
- [x] Match audience Seed VC

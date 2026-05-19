---
artifact: 5 — Solution Approach (phần khám phá)
bai-tap: Solution — tìm lời giải đã có sẵn trước khi tự xây
phase: Double Diamond vòng 2 · ◇ giãn
input: 01-frame/3-FINAL-problem-framing.md · 00-context.md
nop-cuoi: Không — file trung gian
---

# 1 — Find existing solutions

## Bước 0 — Bài này thực ra là dạng bài gì?

- **Quick Win, viết lại thành 1 dạng bài chung**: Từ một yêu cầu có cấu trúc và một tập hồ sơ ứng viên, hệ thống lọc điều kiện bắt buộc, xếp hạng mức phù hợp, rồi tạo shortlist có giải thích và nguồn để người review duyệt.
- **Input → output thực chất là gì**: Yêu cầu người dùng + hồ sơ ứng viên → top 3 ứng viên phù hợp, lý do match/mismatch, flag dữ liệu thiếu, mức tự tin.
- **Ràng buộc không bỏ được**: Privacy, không bịa thông tin, citation từ hồ sơ, human review trước khi gửi, budget nhỏ, chỉ pilot Toán THPT.

## Phần A — Deep research: ai giải dạng bài này rồi, giải sao?

| Tầng | Hỏi AI/web câu gì | Tìm được gì | Nguồn / 🧮 nếu là giả định |
|---|---|---|---|
| 1 · Map | "Candidate matching/ranking with explanations usually uses which approaches?" | Các hướng phổ biến: rule-based hard filter + weighted scoring; semantic matching bằng embedding; LLM rerank có explanation; hybrid retrieval + human review. | 🧮 Tổng hợp pattern sản phẩm AI phổ biến; cần kiểm bằng tài liệu vendor nếu làm thật |
| 2 · Tiền lệ | "Which products shortlist candidates/tutors/jobs with explanations?" | Job boards/ATS, marketplace matching, recommendation systems và tutor platforms đều dùng profile fields + availability + price/rating + review. | 🧮 Lab assumption dựa trên pattern LinkedIn/ATS/marketplace; chưa dùng làm fact định lượng |
| 3 · Phản chứng | "Why do matching recommenders fail?" | Fail khi dữ liệu hồ sơ thiếu/sai, ranking không giải thích được, tối ưu click thay vì fit thật, bias theo rating/giá, và người dùng không trust đề xuất. | 🧮 Pattern rủi ro đã biết; trong pilot chuyển thành guardrail |
| 4 · Thu hẹp | "With small budget, human review, and citation, what works for a 6-week pilot?" | Không build recommender phức tạp. Làm hybrid: hard filter + weighted score + LLM explanation từ hồ sơ + ops review. | 🧮 Chọn theo ràng buộc lab và outline BEETUTOR |

## Phần B — Rút về 2-3 hướng khả thi

| Hướng giải khả thi | Ai làm rồi (gần bài mình nhất) | Nguồn / 🧮 | Hợp ràng buộc `00-context`? |
|---|---|---|---|
| Rule-based hard filter + weighted scoring | Marketplace/ATS cơ bản: lọc theo điều kiện bắt buộc rồi chấm điểm | 🧮 | Có, dễ giải thích, chi phí thấp, nhưng explanation có thể khô cứng |
| Embedding/semantic match giữa nhu cầu và bio gia sư | Search/recommendation trên hồ sơ văn bản | 🧮 | Có một phần, nhưng rủi ro nếu bio thiếu chuẩn và khó giải thích hơn |
| Hybrid Boost: filter + score + LLM viết lý do có nguồn + ops review | Internal copilots/review assistants | 🧮 | Có, hợp budget nhỏ và human review, không cần build platform lớn |

**"Đi từ 5 lên" — kế thừa cụ thể cái gì**:

```text
Kế thừa pattern đã quen của candidate matching: hard filters loại điều kiện bắt buộc, weighted score cho mức phù hợp, explanation để người dùng tin, và human review để kiểm rủi ro. Pilot không phát minh marketplace AI mới mà boost workflow shortlist hiện có.
```

## Phát hiện ban đầu

- Hướng "AI tự chọn gia sư tốt nhất" quá rủi ro; nên giới hạn thành "AI đề xuất shortlist để ops duyệt".
- Hard filter phải chạy trước LLM để tránh đề xuất người sai môn/sai lịch/sai ngân sách.
- Explanation phải dựa vào field hồ sơ cụ thể, không viết chung chung kiểu "phù hợp với bạn".

## Câu hỏi mở (mang sang bước chốt)

- Trọng số match nên do ai quyết: ops lead, product owner, hay học viên tự chỉnh?
- Có nên cho AI giải thích cả lý do không chọn một số gia sư không?
- Cần log gì để audit khi phụ huynh hoặc gia sư thắc mắc?

## Tổng kiểm tra trước khi sang `2-FINAL-solution.md`

| Hạng mục | Xong? |
|---|---|
| Gọi được dạng bài trong 1 câu, không còn chữ domain | Xong |
| Đủ 4 tầng deep research, tầng nào cũng có kết quả | Xong |
| Mỗi kết quả có nguồn hoặc đánh dấu giả định | Xong |
| Rút về 2-3 hướng + nói được "đi từ 5 lên" | Xong |

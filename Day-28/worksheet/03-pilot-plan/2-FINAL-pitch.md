---
artifact: 8 — 5-slide Pitch + AI Support Log (bản nộp cuối lab)
bai-tap: Pilot Plan — dồn thành pitch, sẵn sàng phản biện
phase: Double Diamond vòng 2 · ◆ output
input: 1-pilot-plan.md + toàn bộ 01-frame + 02-solution
nop-cuoi: Có
---

# 2 — FINAL: 5-slide Pitch + AI Support Log

## Phần A — 5 slide

| # | Slide | Lấy từ | Nội dung 1-2 gạch đầu dòng | Ai nói |
|---|---|---|---|---|
| 1 | Problem & user | 01-frame/3-FINAL | Phụ huynh/học viên Toán THPT phải chọn gia sư qua quá nhiều biến; ops mất thời gian lọc và giải thích shortlist. Baseline giả định: 50 yêu cầu/tháng x 20 phút = 16,7 giờ/tháng, sẽ đo thật ở tuần 0. | Cá nhân |
| 2 | Breakdown & Quick Win | 01-frame/1,2 | Không build full marketplace. Quick Win: AI tạo top 3 shortlist gia sư Toán THPT có lý do, nguồn và flag rủi ro để ops review trước khi gửi phụ huynh. | Cá nhân |
| 3 | Solution + bản vẽ trực quan | 02-solution/2-FINAL | Boost, không build từ số 0: hard filters → weighted score → LLM explanation có nguồn → ops review → gửi phụ huynh. Human review nằm trước mọi shortlist gửi ra ngoài. | Cá nhân |
| 4 | AI Pilot Plan | 03-pilot-plan/1 | Pilot 6 tuần, 50 yêu cầu Toán lớp 10-12 TP.HCM, 30-100 hồ sơ gia sư. Budget nhỏ: API 20-50 USD/tháng, tool 0-30 USD/tháng, ops review 2-3 giờ/tuần. | Cá nhân |
| 5 | Metric · exit criteria · lời xin | 03-pilot-plan/1 | Xin quyền chạy pilot 6 tuần với data mẫu/CRM thật, 1 ops lead review, và budget tool/API nhỏ. Hứa giao evidence: giảm >=30% thời gian shortlist, lỗi hard filter <=5%, không bịa thông tin, quyết định continue/iterate/stop theo exit criteria. | Cá nhân |

## Slide 3 — visual để paste vào pitch

```text
Parent intake -> Hard filters -> Weighted score -> LLM reason with sources -> OPS REVIEW -> Parent shortlist

Example output:
#1 Tutor Hoang — 86/100
Sources: Math 10-12; Q1/Q3/Binh Thanh; Online+Offline; 250-350K/hour; Verified certificate+video.
Ops flag: 90-minute price may exceed 300K/session budget. Check before sending.
```

## Phần B — Chuẩn bị 3 câu phản biện

1. *"Số liệu / giả định này lấy ở đâu?"* → Số 50 yêu cầu/tháng, 20 phút/yêu cầu và 30% hỏi lại là giả định lab để tính quy mô pain. Pilot tuần 0 bắt buộc lấy baseline thật từ log tư vấn/CRM trong 10-20 yêu cầu gần nhất; nếu baseline thật thấp hơn nhiều, metric sẽ điều chỉnh hoặc dừng.
2. *"Nếu giả định quan trọng nhất của bạn sai thì sao?"* → Giả định quan trọng nhất là hồ sơ gia sư đủ sạch để match. Nếu sai, không chạy shortlist; chuyển pilot về chuẩn hóa hồ sơ/intake validation trước, vì shortlist trên data bẩn sẽ làm mất trust.
3. *"Tình huống nào sẽ khiến bạn dừng pilot?"* → Dừng ngay nếu AI bịa chứng chỉ/rating/lịch, đề xuất gia sư chưa verify cho học sinh vị thành niên, lỗi hard filter >10%, hoặc có khiếu nại nghiêm trọng từ phụ huynh/gia sư.

## Phần C — AI Support Log

| Câu hỏi | Trả lời |
|---|---|
| AI giúp được gì trong lab này? | AI hỗ trợ dựng nháp cấu trúc, gợi ý use case, so sánh Build/Buy/Boost và nhắc các rủi ro như citation, human review, exit criteria. |
| AI đưa output nào nghe hợp lý nhưng tôi phải sửa? | AI dễ gợi ý build recommender đầy đủ hoặc matching tự động; tôi sửa thành Boost + ops review vì dữ liệu nhỏ và rủi ro với học sinh/phụ huynh. |
| Phần nào tôi tự lập luận, KHÔNG copy AI? | Chọn Quick Win shortlist Toán THPT, giới hạn scope BEETUTOR, đặt baseline giả định, metric, exit criteria và lời xin pilot được tự chốt dựa trên outline `BEETUTOR-MARKETPLACE.md`. |

## Tổng kiểm tra trước khi nộp

| Hạng mục | Xong? |
|---|---|
| 5 slide, mỗi slide 1 thông điệp, đã phân ai nói | Xong |
| Slide 5 có lời xin rõ ràng | Xong |
| Có câu trả lời sẵn cho cả 3 câu phản biện | Xong |
| AI Support Log điền đủ 3 dòng | Xong |
| Tất cả file worksheet đã sẵn sàng commit | Xong |

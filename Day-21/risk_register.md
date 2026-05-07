# BeeTutor Day 21 — Risk Register (Workshop 2)

## Baseline quy đổi runway (lấy từ Day 18)

- Fixed cost baseline: **110,000,000 VND/tháng**.
- Initial cash baseline: **1,500,000,000 VND**.
- Runway baseline tham chiếu: ~**13.6 tháng**.

Quy đổi nhanh:
- 55,000,000 VND = 0.5 tháng runway
- 110,000,000 VND = 1.0 tháng runway
- 330,000,000 VND = 3.0 tháng runway
- 660,000,000 VND = 6.0 tháng runway

## 3 risks bắt buộc (Vendor / Customer-facing / Founder-bandwidth)

| Risk | Type | If-Then-Leading to | L | I | Score | Zone |
|---|---|---|---:|---:|---:|---|
| OpenAI rate-limit shock giờ cao điểm | Vendor | **If** OpenAI giảm effective throughput hoặc tăng lỗi 429 vào khung 19:00-21:00, **then** bot hỗ trợ booking không phản hồi, conversion sụt mạnh và đội vận hành phải xử lý tay trong 2-3 tuần, **leading to** mất ~**3.5 tháng runway** do hụt booking + chi phí xử lý khẩn. | 4 | 4 | 16 | KILL ZONE |
| Chatbot bịa policy refund/no-show | Customer-facing | **If** bot tự sinh câu trả lời sai về refund/escrow/no-show, **then** khách hàng làm theo hướng dẫn sai, phát sinh claim hoàn tiền + tranh chấp công khai, **leading to** mất ~**6.5 tháng runway** do hoàn tiền, legal handling, và churn theo niềm tin. | 3 | 5 | 15 | KILL ZONE |
| Founder quá tải trong tuần có incident | Founder-bandwidth | **If** tôi đồng thời xử lý fundraising + product + incident mà không có người trực thay thế, **then** quyết định chậm trong 24 giờ đầu và playbook bị thực thi nửa vời, **leading to** mất ~**2.2 tháng runway** do kéo dài downtime + mất niềm tin nhóm khách pilot. | 4 | 3 | 12 | Watch/Mitigate |

## Risk ưu tiên cho Workshop 3 (Incident Playbook)

Tôi chọn risk **"Chatbot bịa policy refund/no-show"** để viết playbook vì:
- Đây là risk pháp lý + niềm tin khách hàng, khó cứu nhất nếu phản ứng chậm.
- Điểm số ở KILL ZONE (15).
- Tác động trực tiếp lên lõi BeeTutor: booking, escrow, dispute, no-show.

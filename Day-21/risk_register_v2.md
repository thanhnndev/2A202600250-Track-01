# BeeTutor Day 21 — Risk Register v2 (AI-Augmented)

## Baseline runway để quy đổi impact

- Fixed cost baseline (Day 18): **110,000,000 VND/tháng**.
- Initial cash baseline (Day 18): **1,500,000,000 VND**.
- Runway tham chiếu: ~**13.6 tháng**.

## Ghi chú AI augmentation

- Tôi chạy CRO prompt theo Day 21 handbook và merge với risk thủ công.
- Risk được đánh dấu `AI-found` là những rủi ro tôi đã miss ở bản 3-risk ban đầu.

## Register tổng hợp (12 risks, cover đủ 5 types)

| # | Risk short name | Type | If-Then-Leading to (tháng runway) | L | I | Score | Zone | Nguồn |
|---:|---|---|---|---:|---:|---:|---|---|
| 1 | Policy hallucination lawsuit | Customer-facing | **If** chatbot trả lời sai refund/no-show policy, **then** phát sinh claim + hoàn tiền hàng loạt + xử lý pháp lý, **leading to** mất **6.5 tháng runway**. | 3 | 5 | 15 | KILL ZONE | Manual + AI |
| 2 | OpenAI rate-limit peak-hour | Vendor | **If** OpenAI giảm throughput giờ 19:00-21:00, **then** chat conversion sụt và support phải xử lý tay, **leading to** mất **3.5 tháng runway**. | 4 | 4 | 16 | KILL ZONE | Manual + AI |
| 3 | Founder overload incident week | Founder-bandwidth | **If** tôi phải vừa fundraising vừa xử lý incident, **then** quyết định containment trễ >24h, **leading to** mất **2.2 tháng runway**. | 4 | 3 | 12 | Watch | Manual |
| 4 | Prompt injection public abuse | Customer-facing | **If** user prompt-injection khiến bot phát ngôn công kích, **then** nội dung bị chụp màn hình lan truyền và phụ huynh ngừng booking, **leading to** mất **4.0 tháng runway**. | 4 | 4 | 16 | KILL ZONE | AI-found |
| 5 | Chargeback + escrow dispute wave | Reputational | **If** dispute xử lý chậm >72h, **then** phụ huynh mở chargeback đồng loạt, **leading to** mất **3.2 tháng runway**. | 3 | 4 | 12 | Watch | AI-found |
| 6 | ToS change cấm use-case | Vendor | **If** vendor LLM update ToS khiến một phần nội dung học tập bị giới hạn, **then** quality giảm và phải gấp rút chuyển model, **leading to** mất **3.0 tháng runway**. | 3 | 3 | 9 | Watch | AI |
| 7 | Personal data retention breach | Regulatory | **If** chat log chứa dữ liệu trẻ vị thành niên bị lưu quá thời hạn cam kết, **then** khiếu nại pháp lý + bắt buộc remediation, **leading to** mất **4.5 tháng runway**. | 4 | 4 | 16 | KILL ZONE | AI-found |
| 8 | Settlement payout mismatch | Customer-facing | **If** rule release escrow không khớp dữ liệu check-in/check-out, **then** payout sai cho gia sư/học viên và phát sinh tranh chấp lặp lại, **leading to** mất **3.0 tháng runway**. | 3 | 3 | 9 | Watch | AI |
| 9 | Single maintainer failure | Founder-bandwidth | **If** chỉ 1 engineer hiểu module chatbot gateway và người này nghỉ đột xuất, **then** không ai hotfix được sự cố policy, **leading to** mất **4.0 tháng runway**. | 4 | 4 | 16 | KILL ZONE | AI-found |
| 10 | Regulatory transparency non-compliance | Regulatory | **If** sản phẩm không hiển thị rõ "AI-generated response" ở các touchpoint bắt buộc, **then** bị yêu cầu chỉnh sửa khẩn + tạm dừng một số luồng, **leading to** mất **3.0 tháng runway**. | 3 | 3 | 9 | Watch | AI |
| 11 | Tutor trust collapse after no-show scandal | Reputational | **If** 1 case no-show nổi bật xử lý bất công và lan truyền trong cộng đồng gia sư, **then** supply tutor chất lượng rời platform, **leading to** mất **3.8 tháng runway**. | 3 | 4 | 12 | Watch | Manual + AI |
| 12 | Payment rail outage weekend | Vendor | **If** cổng thanh toán lỗi cuối tuần, **then** booking đặt cọc thất bại trong khung traffic cao, **leading to** mất **2.5 tháng runway**. | 3 | 3 | 9 | Watch | AI |

## 2+ risks AI tìm ra mà tôi đã miss (reflection)

1) **Prompt injection public abuse** (`#4`) — `AI-found`  
Tôi đã miss vì tôi quá tập trung vào legal/policy wording, nhưng AI chỉ ra vector tấn công qua prompt input công khai có thể tạo khủng hoảng thương hiệu cực nhanh.

2) **Single maintainer failure** (`#9`) — `AI-found`  
Tôi đã miss vì tôi giả định "team nhỏ thì ai cũng biết codebase", nhưng thực tế chatbot gateway đang có knowledge concentration.

3) **Personal data retention breach** (`#7`) — `AI-found`  
Tôi đã miss vì tôi nghĩ retention là chuyện backend hygiene, nhưng AI nhắc đây là risk regulatory trực tiếp vì dữ liệu trẻ vị thành niên.

## Top 5 KILL ZONE và mitigation options (<$500/tháng)

## Risk #2 — OpenAI rate-limit peak-hour (Score 16)

Option A: Multi-model failover (OpenAI -> Anthropic) qua abstraction layer (ước tính 120 USD/tháng).  
Option B: Queue + degrade message template khi 429 tăng (40 USD/tháng infra).  
Option C: Hard cap AI replies giờ cao điểm, ưu tiên user trả phí (0 USD, impact trải nghiệm).

**Tôi chọn A + B.**  
Lý do: vừa giữ uptime, vừa không hi sinh toàn bộ trải nghiệm.  
Cost gộp: ~160 USD/tháng.

## Risk #4 — Prompt injection public abuse (Score 16)

Option A: Prompt firewall rule + regex blocklist cho cụm tấn công phổ biến (20 USD/tháng logging + alert).  
Option B: Intent classifier tách "policy intent" khỏi free-text generation (60 USD/tháng compute).  
Option C: Manual moderation cho 100% hội thoại (không khả thi vận hành).

**Tôi chọn A + B.**  
Lý do: triển khai trong 1 tuần và không cần đội moderation lớn.  
Cost gộp: ~80 USD/tháng.

## Risk #9 — Single maintainer failure (Score 16)

Option A: Mỗi module critical bắt buộc 2 owner + on-call shadow rotation (0 USD).  
Option B: Viết runbook + video walkthrough 20 phút/module (0 USD).  
Option C: Thuê consultant part-time standby (300 USD/tháng).

**Tôi chọn A + B ngay, C chỉ bật khi growth tăng.**  
Lý do: giảm bus-factor nhanh, chi phí thấp.  
Cost hiện tại: 0 USD/tháng.

## Risk #1 — Policy hallucination lawsuit (Score 15)

Option A: Khóa toàn bộ policy intent bằng rule-based response cards (30 USD/tháng ops).  
Option B: Human verification cho policy-sensitive sessions (200 USD/tháng ca trực part-time).  
Option C: Post-response policy validator trước khi trả lời khách (90 USD/tháng compute).

**Tôi chọn A + C, B dùng khi incident mode.**  
Lý do: tự động hóa mặc định, chỉ tăng người khi khẩn cấp.  
Cost gộp bình thường: ~120 USD/tháng.

## Risk #7 — Personal data retention breach (Score 16)

Option A: TTL xóa log 90 ngày + redaction PII tự động (50 USD/tháng).  
Option B: Data map + retention policy audit định kỳ 2 tuần/lần (0 USD, founder-led).  
Option C: Mua enterprise DLP full-suite (>1000 USD/tháng, không phù hợp seed stage).

**Tôi chọn A + B.**  
Lý do: đạt hiệu quả compliance cao mà vẫn giữ budget startup.  
Cost gộp: ~50 USD/tháng.

## Tổng chi phí mitigation tháng (giai đoạn hiện tại)

- Rate-limit mitigation: 160 USD
- Injection mitigation: 80 USD
- Single maintainer: 0 USD
- Policy hallucination guard: 120 USD
- Retention guard: 50 USD
- **Tổng:** ~**410 USD/tháng** (<500 USD/tháng theo yêu cầu)

## Founder commitments tuần tới (I will)

- I will ship model failover + queue degrade cho giờ cao điểm trong 7 ngày.
- I will chuyển toàn bộ policy intent sang response cards có version control.
- I will chạy tabletop incident 1 giờ vào thứ Sáu với đúng kịch bản prompt injection.
- I will chốt owner backup cho mỗi module critical và cập nhật runbook ngay tuần này.

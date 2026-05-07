# BeeTutor Day 21 — Incident Playbook (Founder Always-On-Call)

## Scenario trigger

09:30 sáng: một phụ huynh đăng screenshot trên Facebook/TikTok nói bot BeeTutor trả lời sai policy hoàn tiền. 200+ share trong 30 phút.

Mục tiêu của tôi: contain trong 60 phút đầu, giữ trust, giảm runway loss.

## 0-60 phút: Time-box cố định

### 0-5 phút — VERIFY (không suy đoán)

Checklist tôi chạy ngay:
1. Mở `https://us.helicone.ai` -> project `beetutor-prod` -> filter `intent:refund OR intent:no_show` trong 2 giờ gần nhất.
2. Tìm conversation theo timestamp trong screenshot, đối chiếu `user_id`, `session_id`, prompt và response raw.
3. So khớp screenshot với log để loại trừ ảnh chỉnh sửa.
4. Chụp bằng chứng nội bộ (log URL + screenshot) vào kênh incident.

Nếu không tìm thấy log trùng trong 5 phút: tôi coi là nghi ngờ giả mạo, nhưng vẫn chuyển mức theo dõi cao và trả lời công khai "đang verify".

### 5-15 phút — STOP THE BLEEDING (chọn 1 option, không mơ hồ)

Tôi chọn: **Soft kill**.

Action:
1. Tắt route trả lời policy bằng LLM (`POLICY_LLM_ENABLED=false`).
2. Chuyển fallback sang rule-based policy cards từ DB (`refund_policy_v1`, `no_show_policy_v1`, `escrow_policy_v1`).
3. Giữ bot chạy cho intent thông tin lớp học thông thường, nhưng block intent policy cứng.

Lý do tôi chọn soft kill:
- Giảm ngay khả năng phát sinh thêm câu trả lời sai.
- Không làm sập toàn bộ trợ lý chat, vẫn giữ conversion cơ bản.
- Triển khai được bằng 1 env switch đã chuẩn bị trước.

### 15-30 phút — CUSTOMER COMM (founder personal voice)

#### DM gửi khách bị ảnh hưởng (template dùng ngay)

Hi [Tên khách], I am [Tên Founder], founder của BeeTutor.  
I checked your case and the chatbot gave a wrong policy answer. This is on me.  
I have disabled policy answers from the AI right now and switched to manual policy verification.  
I will refund your affected session fee 100% and add **300,000 VND credit today**.  
If you want to speak with me directly, call me at [SĐT founder] or book [Calendly link].  
I will send you an update within 24 hours.

#### Internal update cho team

"Có incident policy-level. I am handling. AI policy route đã soft-kill. 18:00 hôm nay tôi cập nhật root cause + fix."

### 30-60 phút — PUBLIC RESPONSE + CONTROL LOOP

1. Đăng tweet/FB ngắn từ founder (dưới 280 ký tự).
2. Ghim thông báo trong app: "Policy answers are temporarily manual-verified."
3. Mở incident room với owner rõ ràng:
   - Founder: incident commander.
   - Eng owner: rollback + patch.
   - Ops owner: affected-customer list + compensation.

## Public post (dưới 280 ký tự)

I’m [Founder], BeeTutor founder. I confirmed a wrong chatbot reply about refund policy. I’ve disabled AI policy replies and switched to manual verification. I’m contacting affected users directly and issuing compensation today. Full update in 24h.

## 3-AM test (founder mệt vẫn làm được)

- Có URL verify cụ thể? **Có**.
- Có option stop-the-bleeding đã chọn sẵn? **Có, soft kill**.
- Có message template dùng ngay không cần viết lại? **Có**.
- Có deadline update công khai? **Có, 24h**.

## Exit criteria trong 24 giờ

- Không còn response policy từ LLM ở production.
- 100% user bị ảnh hưởng đã được liên hệ và xử lý.
- Publish postmortem ngắn: cause, fix, prevention.

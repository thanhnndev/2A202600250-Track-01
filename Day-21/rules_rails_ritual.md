# BeeTutor Day 21 — Rules / Rails / Ritual (Founder Draft v1)

Last updated: 07/05/2026 by Founder

## Scope risk lớn nhất tôi đang chặn

Rủi ro số 1 của BeeTutor hiện tại: AI trả lời sai chính sách booking/refund/no-show và tạo nghĩa vụ pháp lý với khách hàng.

Tôi dùng 3R để chặn rủi ro này theo cách seed-stage có thể làm trong 1 tuần.

## R1 — RULES (1 trang, founder-led)

### 1) Cái gì bị cấm

- Không được paste dữ liệu có thể định danh khách hàng (tên thật, số điện thoại, địa chỉ, chat log học viên-gia sư) vào ChatGPT free/Claude free bản public.
- Không được để chatbot tự do trả lời các phần "policy cứng": refund, no-show, escrow release, dispute penalty.
- Không được deploy prompt/policy mới trực tiếp production mà không qua review 4 mắt (Founder + 1 owner vận hành).

### 2) Cái gì được làm (alternative cụ thể)

- Dùng `OpenAI API` qua backend BeeTutor (không cho team paste data tay vào tool public).
- Dùng `Cursor` + repo nội bộ để soạn prompt và review thay đổi.
- Với câu hỏi policy cứng, bot chỉ được trả từ bảng policy whitelist trong DB (`refund_policy_v1`, `no_show_policy_v1`), không được tự sinh.

### 3) Hậu quả vi phạm

- Lần 1: Tôi họp 1-1 ngay trong ngày, ghi note corrective action và deadline fix.
- Lần 2: Tạm ngừng quyền deploy AI-related 2 tuần.
- Lần 3: Dừng hợp tác ở vai trò hiện tại.

### 4) Cách update rules

- Owner cập nhật: Founder (tôi).
- Trigger update: khi có incident, khi đổi vendor AI chính, hoặc khi đổi policy thanh toán.
- SLA update: trong 24 giờ sau khi có thay đổi quan trọng.

## R2 — RAILS (tooling <$500/tháng)

| Mục tiêu | Vendor/tool | Cost/tháng (USD) | Trạng thái |
|---|---|---:|---|
| Chặn lộ secrets trong code | `git-secrets` (AWS Labs) | 0 | Bật pre-commit |
| Log toàn bộ prompt/response production | `Helicone` | 0 (free tier) | Bật cho API gateway |
| Chặn truy cập LLM public từ máy team ops | `NextDNS` | 40 | Bật theo nhóm thiết bị |
| Review bắt buộc trước merge AI policy | `GitHub Branch Protection` | 0 | Require 1 reviewer |
| Cảnh báo lỗi runtime theo thời gian thực | `Sentry` | 26 | Alert cho founder |
| Tổng |  | **66 USD/tháng** | Dưới ngưỡng startup |

Nguyên tắc của tôi: nếu một control có thể làm bằng free/cheap tool thì không mua enterprise stack.

## R3 — RITUAL (hành vi founder + team)

### Weekly cadence (30-45 phút)

- **Thứ Hai 09:00 (15')**: AI risk standup. Tôi xem top 3 cảnh báo tuần trước và owner xử lý tuần này.
- **Thứ Tư 17:30 (10')**: Audit nhanh 10 hội thoại có policy intent trong Helicone.
- **Thứ Sáu 16:30 (20') — Customer Friday**: tôi gọi trực tiếp 2 phụ huynh và 1 gia sư đã chat với bot.

### Câu hỏi tôi sẽ hỏi mỗi tuần (không chung chung)

- "Trong câu trả lời của bot tuần này, có câu nào khiến anh/chị phải chụp màn hình để tự bảo vệ mình không?"
- "Nếu BeeTutor bot trả lời sai về hoàn tiền, anh/chị kỳ vọng tôi xử lý trong bao lâu?"
- "Một câu trả lời nào làm anh/chị mất niềm tin ngay lập tức không?"

### Trigger bắt buộc mở incident playbook

- Có screenshot công khai cho thấy bot trả lời sai policy.
- Có từ 3 ticket liên tiếp cùng 1 lỗi policy trong 24 giờ.
- Có 1 claim đòi hoàn tiền vì làm theo hướng dẫn sai từ bot.

## 7-day implementation plan (seed-stage thực thi được)

- Day 1: chốt policy whitelist trong DB + khóa câu policy cứng.
- Day 2: bật `git-secrets` + branch protection.
- Day 3: nối logging Helicone cho toàn bộ luồng chatbot.
- Day 4: cấu hình NextDNS profile cho máy team vận hành.
- Day 5: viết runbook escalation + phân quyền người trực.
- Day 6: chạy war-game 1 giờ theo kịch bản Air Canada-style.
- Day 7: cập nhật rules v1.1 theo gap tìm được.

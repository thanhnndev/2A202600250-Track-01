# Document Trail — BeeTutor Marketplace

**Date:** 09/05/2026  
**Người thực hiện / Founder:** Nông Nguyễn Thành

## Bảng đối chiếu 5 loại hồ sơ

| # | Loại | Status | Link/Path | Deadline build |
|---|------|--------|-----------|----------------|
| 1 | Nhật ký kiểm thử claim AI | ✗ | *(chưa có repo docs)* | **30/05/2026** — template + sheet log đầu tiên khi bật AI quiz/matching |
| 2 | Hồ sơ rà soát điều khoản vendor | ✗ | *(MoMo, VNPay, Stripe, OpenAI/Azure…)* | **23/05/2026** — checklist DPA + subprocessors + data residency |
| 3 | Nhật ký giám sát giao dịch bất thường | ✗ | *(escrow, refund abuse)* | **16/05/2026** — rule flags + weekly review (anti-pattern **Pips**) |
| 4 | DPIA / CTIA đã nộp | ✗ | *(chưa nộp cổng)* | **Trong 60 ngày** kể từ xử lý DLCN đặc thù + chuyển biên giới — áp dụng khi go-live xử lý PII |
| 5 | Phê duyệt nội dung marketing | ✗ | *(chưa có form founder sign-off)* | **Trước mọi đợt marketing đại trà** — template ký + archive Slack/email |

## TOP 1 ưu tiên

**Loại:** **#3 — Nhật ký giám sát giao dịch bất thường**

**Lý do:** BeeTutor có **escrow hai đợt**, hoàn tiền trial/hủy khóa và **platform fee** — nếu không có quy trình phát hiện “mạng lưới” gian lận hoặc wash booking, founder dễ rơi vào kịch bản **tiếp tay xử lý thanh toán khi đã có dấu hiệu** (pattern **Mr Pips / Điều 324** — analog nền tảng).

## Template build trong 1 tuần

### Người chịu trách nhiệm

**Nông Nguyễn Thành (Founder)** + **CTO/Finance** khi tuyển (hiện ghi nhận Founder là owner).

### Tần suất cập nhật

**Hằng tuần** (review thứ Hai); **ad-hoc** khi rule auto-flag.

### Sample 3–5 dòng (copy vào Google Sheet / Notion DB)

```text
| Tuần | Rule_ID | Mô tả flag | Ví dụ Case_ID | Hành động | Người xử lý | Trạng thái | Link evidence |
|------|---------|------------|---------------|-----------|-------------|------------|---------------|
| 2026-W19 | TXN-01 | ≥3 refund trial cùng device/IP | #BK-10422 | Khóa payout + KYC lại | NT | Đang điều tra | drive/txn-audit/… |
| 2026-W19 | TXN-04 | Tutor–Learner trùng STK/tài khoản MoMo | #PY-8821 | Suspension + báo cáo nội bộ | NT | Escalated | … |
```

### Rule gợi ý (MVP)

- Cùng **thiết bị/IP** tạo ≥N cặp tutor–learner trong 7 ngày  
- Chuỗi **đặt–hủy sau đúng 2 buổi trial** lặp lại  
- **Tốc độ tăng GMV** bất thường trên tutor mới chưa có lịch sử review  

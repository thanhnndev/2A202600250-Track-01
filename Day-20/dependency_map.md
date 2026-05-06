# BeeTutor Day 20 — Dependency Map & Critical Path

## 3 external dependencies

### 1) Payment rail / escrow provider
- **Vendor:** MoMo / VNPay / ZaloPay.
- **Worst-case:** Payment webhook lỗi, payout treo, hoặc chính sách escrow thay đổi khiến booking flow bị kẹt.
- **Plan B:** Chuyển sang bank transfer + manual reconciliation cho pilot; giữ một payment abstraction layer để đổi provider trong 24h.
- **Cost:** 1 tuần dev + 1 tuần ops set-up, khoảng 8-15M VND setup/integration và thêm chi phí support manual.

### 2) LLM / embeddings provider cho matching và summary
- **Vendor:** OpenAI / Anthropic / Gemini.
- **Worst-case:** Rate limit, giá tăng, hoặc model lỗi làm ranking / summary chậm hoặc sai.
- **Plan B:** Fallback sang rule-based scoring theo subject, level, district, rating, availability; cache embedding và dùng model thay thế khi cần.
- **Cost:** 2 tuần dev để hoàn thiện abstraction + 3-5M VND/tháng infra và cache.

### 3) Notification rail
- **Vendor:** Zalo OA / SMS gateway / email provider.
- **Worst-case:** Nhắc lịch không tới nơi làm booking và attendance tụt ngay.
- **Plan B:** Dùng in-app notifications + email trước, SMS chỉ cho các event critical; switch provider qua adapter.
- **Cost:** 3-5 ngày dev + chi phí gửi tin theo volume.

## Critical Path

```text
Tutor verification + consent
        ↓
Data pipeline (profile, availability, booking, attendance)
        ↓
Legal compliance (privacy, child safety, payment terms)
        ↓
Booking + escrow integration
        ↓
Check-in / check-out proof + no-show rules
        ↓
Dispute resolution workflow
        ↓
Pilot launch
```

## Task nào là critical

- **Data Pipeline** là critical vì mọi rule và matching đều cần data sạch.
- **Legal Compliance** là critical vì học viên là nhóm nhạy cảm, lại có payment flow và location data.
- **Booking + Escrow Integration** là critical vì đây là chỗ tiền đi qua.
- **Check-in / dispute flow** là critical vì nó quyết định trust và refund.

## Buffer tasks

- UI polish.
- Marketing site.
- Long-form documentation.
- Advanced analytics dashboard.

## Sanity check

- Có 3 dependency cụ thể với vendor name.
- Có Plan B rõ ràng cho từng dependency.
- Critical path có Data Pipeline và Legal Compliance.
- UI/marketing không nằm trên critical path.
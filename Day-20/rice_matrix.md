# BeeTutor Day 20 — RICE Matrix

## 5 features được chấm

| Feature | Reach | Impact | Confidence | Effort (person-month) | RICE score | Ghi chú |
|---|---:|---:|---:|---:|---:|---|
| Real-time chat + availability sync | 3,500 | 1.5 | 0.8 | 1.0 | 4,200 | Giảm back-and-forth trước booking |
| Escrow + refund/no-show rules | 3,200 | 2.0 | 0.9 | 1.5 | 3,840 | Chốt trust layer cho marketplace |
| Smart matching + verified ranking | 5,000 | 2.0 | 0.7 | 2.5 | 2,800 | Nâng quality của booking và retention |
| GPS/dual-confirm attendance proof | 2,500 | 1.5 | 0.8 | 1.5 | 2,000 | Chống tranh chấp và no-show |
| AI lesson voice assistant | 500 | 0.5 | 0.5 | 4.0 | 31 | Visionary nhưng chưa đủ tác động |

### Cách hiểu các số

- Reach đã discount nhẹ so với estimate lạc quan ban đầu.
- Confidence chưa có pilot sâu chỉ được giữ ở mức 50-80%.
- Effort đã cộng buffer cho QA, integration và vận hành hậu launch.

## 2x2 Value-Effort Matrix

```text
                      Effort
                  Low              High
            ┌────────────────┬────────────────┐
Value High  │ Quick Wins     │ Strategic Bets │
            │                │                │
            │ 1. Chat +     │ 2. Smart       │
            │    availability│    matching    │
            │ 4. GPS proof   │ 2. Escrow +    │
            │                │    refund rules│
            ├────────────────┼────────────────┤
Value Low   │ Fill-ins       │ Non-starters   │
            │                │ 5. Voice AI    │
            │                │    assistant   │
            └────────────────┴────────────────┘
```

## Quyết định ưu tiên

- **Quick Win:** Real-time chat + availability sync. Đây là bước nhanh nhất để giảm friction trước booking.
- **Strategic Bet:** Escrow + refund/no-show rules. Đây là lớp trust và payout cần làm đúng để mở rộng bền vững.
- **Non-starter:** AI lesson voice assistant. Cool, nhưng quá đắt và chưa tạo tác động đủ lớn lên completed paid sessions.

## Sanity check

- Có ít nhất 1 feature Confidence dưới 80%: có.
- Có non-starter rõ ràng: có.
- Effort đã nhân buffer 1.5x ở các hạng mục phức tạp: có.
- Bảng có Quick Win và Strategic Bet rõ ràng: có.
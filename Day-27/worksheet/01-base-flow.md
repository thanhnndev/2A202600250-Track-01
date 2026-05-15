# 01 · Base Flow + Chốt 3 Knobs

> **Mục tiêu**: Hiểu chatbot hoạt động ra sao ở mức base — và xác định 3 knobs sẽ tweak.

---

## Bước 1 — Đọc base flow

Đã đọc cost-reference-card.md phần Base Flow. Hiểu rõ:

1. Intent classification (keyword-based, $0) → route đến 5 nhánh
2. Visa/Policy → RAG (+ optional web search)
3. Guide/Destination → RAG only
4. Weather/Event → Web search
5. Tour/Booking → Handoff sales ($0 LLM)
6. Complaint → Escalate manager ($0 LLM)
7. Context assembly → Response generation

---

## Bước 2 — Vẽ lại flow

```text
Tourist message
       │
       ▼
┌─ Intent Classification (keyword, $0) ─────────────┐
│  "visa", "passport", "entry" → Visa/Policy         │
│  "where", "what to do", "suggest" → Guide          │
│  "weather", "rain", "festival" → Weather/Event     │
│  "book", "reserve", "tour" → Tour/Booking          │
│  "complaint", "missed", "problem" → Complaint      │
└────────┬───────────────────────────────────────────┘
         │
    ┌────┼────┬──────────┬───────────┐
    ▼    ▼    ▼          ▼           ▼
  Visa  Guide  Weather  Booking   Complaint
    │    │      │         │          │
    ▼    ▼      ▼         ▼          ▼
 ┌──────────────────┐  ┌────────┐  ┌──────────┐
 │ RAG top-5 chunks │  │Handoff │  │ Escalate │
 │ + Web (if ON)    │  │ Sales  │  │ Manager  │
 │ ($0 LLM)         │  │ ($0)   │  │ ($0)     │
 └────────┬─────────┘  └────────┘  └──────────┘
          │
          ▼
 ┌─ Context Assembly ────────────────────────────────┐
 │  System prompt (500) + History + RAG (1,250)       │
 │  + Web results (800, if ON) + User msg (80)        │
 └────────┬───────────────────────────────────────────┘
          │
          ▼
 ┌─ Response Generation ─────────────────────────────┐
 │  Model creates response (~180 tokens output)       │
 └────────────────────────────────────────────────────┘
```

---

## Bước 3 — Xác định 3 Knobs

### Knob 1 — Model tier

**Suy nghĩ của nhóm:**
- Tourist hỏi cả câu đơn giản (weather) lẫn phức tạp (itinerary planning).
- Dùng 1 model cho tất cả = waste tiền cho câu dễ, hoặc quality thấp cho câu khó.
- → Nên Mix: cheap cho Guide/Weather, strong cho Visa (info nhạy cảm, sai =法律问题).

### Knob 2 — Web search

**Suy nghĩ của nhóm:**
- Visa policy thay đổi thường xuyên → RAG alone không đủ → cần web cho Visa.
- Weather = real-time tự nhiên → bắt buộc web.
- Guide/Destination = KB đủ (destinations không thay đổi nhanh) → không cần web.
- → ON selective: bật cho Visa + Weather.

### Knob 3 — History management

**Suy nghĩ của nhóm:**
- Scenario A (4 turns): Last 5 hoặc Full đều không khác nhau nhiều.
- Scenario B (7 turns): Full history đắt — mỗi turn thêm 260 tokens × 6 prior = 1,560 tokens thêm.
- Tourist hay reference "tôi nói budget $500 ở turn 1" → cần ít nhất Last 5.
- → Last 5 là cân bằng tốt nhất.

---

## Bước 4 — Phác thảo 3 combo

**Combo 1 (Budget Bot)**:

```text
Model: Gemini 2.5 Flash-Lite (cheap)    Web: ON selective (Visa, Weather)    History: Last 3
Đặt tên dự kiến: Budget Bot
```

**Combo 2 (Premium Concierge)**:

```text
Model: Claude Sonnet 4.6 (strong)    Web: ON selective (Visa, Weather)    History: Full
Đặt tên dự kiến: Premium Concierge
```

**Combo 3 (Smart Mix)**:

```text
Model: Mix — Gemini Flash-Lite (Guide/Weather), DeepSeek V4 Pro (Visa)    Web: ON selective    History: Last 5
Đặt tên dự kiến: Smart Mix
```

---

## Bảng kiểm trước khi sang file tiếp theo

- [x] Đã vẽ flow base có đủ 4 bước
- [x] Hiểu Booking + Khiếu nại = $0 LLM cost
- [x] Đã phác thảo ≥3 combo khác nhau
- [x] Nhóm đồng thuận về hướng đi mỗi combo

Xong → mở `02-config-design.md`.

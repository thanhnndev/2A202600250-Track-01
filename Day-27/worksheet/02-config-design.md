# 02 · Configuration Design — Đặt tên + Chốt knobs cho ≥3 Configs

---

## Config 1

**Tên config**:

```text
Budget Bot
```

### 3 Knobs

**① Model tier**:

```text
Response model: Gemini 2.5 Flash-Lite → giá $0.10 / $0.40 per 1M tokens (input/output)
Classifier model: Keyword-based → $0
```

**② Web search**:

```text
☑ ON selective — bật cho intent: Visa/Policy, Weather/Event
```

**③ History management**:

```text
☑ Last 3
```

### Lý do nhóm chọn config này

Config này phục vụ tình huống volume cao, budget thấp nhất có thể — phù hợp mùa thấp điểm (Scenario A, 300 conv/ngày) khi chi phí là ưu tiên số 1. Gemini Flash-Lite rẻ nhất trong bảng pricing ($0.10/$0.40), vẫn đủ good cho câu hỏi đơn giản như Guide/Destination và Weather. Web selective bật cho Visa/Weather vì 2 intent này cần real-time info.

### Rủi ro lớn nhất của config này

Visa info từ RAG có thể outdated — dù có web search, Flash-Lite model yếu hơn có thể không interpret policy changes chính xác, dẫn đến trả lời sai cho khách về visa requirements.

---

## Config 2

**Tên config**:

```text
Premium Concierge
```

### 3 Knobs

**① Model tier**:

```text
Response model: Claude Sonnet 4.6 → giá $3.00 / $15.00 per 1M tokens
Classifier model: Keyword-based → $0
```

**② Web search**:

```text
☑ ON selective — bật cho intent: Visa/Policy, Weather/Event
```

**③ History management**:

```text
☑ Full
```

### Lý do nhóm chọn config này

Config này phục vụ khách VIP và mùa cao điểm (Scenario B, 1,200 conv/ngày) khi quality quan trọng hơn cost. Claude Sonnet cho output chất lượng cao — trả lời chính xác, tone professional, ít hallucination. Full history đảm bảo chatbot nhớ toàn bộ conversation (7 turns) — tourist hay reference "tôi nói budget $500 ở turn 1" và sẽ thất vọng nếu bot quên.

### Rủi ro lớn nhất của config này

Cost cao — Claude Sonnet đắt hơn Flash-Lite 30× (input) và 37.5× (output). Ở Scenario B với 1,200 conv/ngày × 7 turns × Full history, cost có thể vượt human baseline $0.50/conv cho một số intent.

---

## Config 3

**Tên config**:

```text
Smart Mix
```

### 3 Knobs

**① Model tier**:

```text
Response model: Mix theo intent
  → Guide/Destination: Gemini 2.5 Flash-Lite ($0.10/$0.40)
  → Visa/Policy: DeepSeek V4 Pro ($1.74/$3.48) — cần accuracy cao
  → Weather/Event: Gemini 2.5 Flash-Lite ($0.10/$0.40)
Classifier model: Keyword-based → $0
```

**② Web search**:

```text
☑ ON selective — bật cho intent: Visa/Policy, Weather/Event
```

**③ History management**:

```text
☑ Last 5
```

### Lý do nhóm chọn config này

Config này balance giữa cost và quality — dùng model rẻ cho intent đơn giản (Guide, Weather) và model mạnh cho intent nhạy cảm (Visa — sai info = khách bị deny entry). DeepSeek V4 Pro là "strong" model nhưng rẻ hơn Claude Sonnet ~4× (input $1.74 vs $3.00). Last 5 đủ context cho hầu hết conversation (4-5 turns) mà không quá đắt như Full history.

### Rủi ro lớn nhất của config này

Phức tạp vận hành — cần routing logic để chọn model theo intent. Nếu routing sai (VD: dùng Flash-Lite cho Visa), chất lượng giảm đáng kể.

---

## Config 4 (optional)

**Tên config**:

```text
Night Mode (không dùng — chỉ thiết kế 3 configs chính)
```

---

## Bảng kiểm trước khi tính cost

- [x] ≥3 configs đã đặt tên (Budget Bot, Premium Concierge, Smart Mix)
- [x] Mỗi config đã chốt rõ 3 knobs
- [x] Mỗi config có ≥2 câu lý do
- [x] 3 configs đủ khác biệt: Cheap vs Premium vs Mix
- [x] Nhóm đồng thuận đây là 3 configs đáng so sánh

Xong → mở `03-cost-calculation.md`.

# 04 · Comparison Table — Bảng so sánh đầy đủ

---

## Bảng chính

| | Config 1: Budget Bot | Config 2: Premium Concierge | Config 3: Smart Mix |
|---|---|---|---|
| **Tên** | Budget Bot | Premium Concierge | Smart Mix |
| **① Model** | Gemini 2.5 Flash-Lite ($0.10/$0.40) | Claude Sonnet 4.6 ($3.00/$15.00) | Mix: Flash-Lite (Guide/Weather) + DeepSeek V4 Pro (Visa) |
| **② Web search** | ON selective (Visa, Weather) | ON selective (Visa, Weather) | ON selective (Visa, Weather) |
| **③ History** | Last 3 | Full | Last 5 |
| **Intent classifier** | Keyword ($0) | Keyword ($0) | Keyword ($0) |
| **Cost / conv (Scenario A — 4 turns)** | $0.003800 | $0.034624 | $0.009486 |
| **Cost / conv (Scenario B — 7 turns)** | $0.003282 | $0.042541 | $0.009721 |
| **Monthly A** (300 conv/day × 30) | $34.20 | $311.62 | $85.37 |
| **Monthly B** (1,200 conv/day × 30) | $118.15 | $1,531.48 | $349.96 |
| **vs human $4,500/mo (A)** | rẻ 117.9× | rẻ 14.5× | rẻ 52.6× |
| **vs human $18,000/mo (B)** | rẻ 152.5× | rẻ 11.7× | rẻ 51.4× |
| **Savings % (A)** | 99.24% | 93.08% | 98.10% |
| **Savings % (B)** | 99.34% | 91.49% | 98.06% |
| **Quality estimate** | Low | High | Medium-High |
| **Speed estimate** | High (~200ms/turn) | Low (~1-3s/turn) | Medium-High (~200ms Guide, ~500ms Visa) |
| **Điểm yếu chính** | Visa quality thấp — model yếu có thể interpret policy sai | Cost cao nhất, Full history đắt ở conv dài | Phức tạp vận hành — cần routing logic đúng model/intent |
| **Best for** | Mùa thấp điểm, volume cao, budget siết | Khách VIP, mùa cao điểm, quality-first | Deploy quanh năm — balance cost/quality tốt nhất |

---

## Quan sát nhanh từ bảng

### Câu 1 — Config rẻ nhất là gì? Đắt nhất là gì?

```text
Rẻ nhất: Budget Bot — monthly B = $118.15
Đắt nhất: Premium Concierge — monthly B = $1,531.48
Chênh: 13.0× lần
```

### Câu 2 — Knob nào ảnh hưởng cost nhiều nhất?

```text
Model tier ảnh hưởng nhiều nhất: Budget Bot → Premium tăng cost 9.1× (Scenario A)
và 13.0× (Scenario B). DeepSeek V4 Pro (Strong) rẻ hơn Sonnet 4× → Smart Mix
tiết kiệm hơn Premium 3.6× (Scenario A) và 4.4× (Scenario B).

History: Full vs Last 3 chênh ~57% ở Turn 7 (Premium: T7 $0.01287 vs T1 $0.00819).
Web search: Bật/tắt chênh $0.008/turn — significant khi web ON nhiều turn, nhưng
nhỏ so với model cost.
```

### Câu 3 — Tại sao Scenario B không đắt ×4 lần Scenario A?

```text
Volume Scenario B = ×4 lần Scenario A (1,200 vs 300 conv/ngày). Turns dài hơn
(7 vs 4 = ×1.75). Mong đợi monthly B ≈ monthly A × 7. Thực tế: Budget Bot B/A =
$118/$34 = 3.5× (thấp hơn 7×). Lý do: Scenario B có Booking+Complaint占比 45%
(so với 15% ở A) — đây là $0 LLM cost vì handoff. Intent mix khác biệt kéo avg
cost/conv Scenario B THẤP HƠN Scenario A (Budget Bot: $0.003282 < $0.003800).
```

### Câu 4 — Có config nào AI đắt hơn human không?

```text
KHÔNG — tất cả 3 configs đều rẻ hơn human baseline $0.50/conv.
Budget Bot: rẻ nhất (99%+ savings). Premium Concierge: vẫn tiết kiệm 91-93%.
→ AI luôn rẻ hơn human cho travel chatbot, ngay cả với model mạnh nhất.
Tuy nhiên, cần justify: AI không replace human cho booking convert — sales agent
vẫn cần thiết để close deals. AI thắng ở 24/7 availability, đa ngôn ngữ, và
scale linear khi volume tăng đột biến (lễ hội, Tết).
```

---

## Bảng kiểm trước khi sang file tiếp theo

- [x] Bảng đầy đủ — không còn ô trống
- [x] Đã có 4 câu trả lời cho 4 quan sát ở trên
- [x] Nhóm đồng thuận về số trong bảng (đã sanity check)

Xong → mở `05-recommendation.md`.

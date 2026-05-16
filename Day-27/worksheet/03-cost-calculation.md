# 03 · Cost Calculation — Tính chi phí từng Config × 2 Scenarios

---

## Setup chung

```text
System prompt:              500 tokens
User message:                80 tokens
Assistant response:         180 tokens (output)
1 prior turn in history:    260 tokens (80 user + 180 assistant)
RAG top-5 chunks:         1,250 tokens (cố định cho AI-served intents)
Web search results:         800 tokens (khi bật)
Web search API call:       $0.008 / call (Tavily)
Classifier:                Keyword-based → $0 (tất cả configs)
```

**Scenario A**: 300 conv/ngày × 30 = 9,000 conv/tháng, avg 4 turns, AI-served 85%
Intent mix: Guide 50%, Visa 25%, Weather 10%, Booking 10%, Complaint 5%

**Scenario B**: 1,200 conv/ngày × 30 = 36,000 conv/tháng, avg 7 turns, AI-served 55%
Intent mix: Guide 30%, Visa 15%, Weather 10%, Booking 35%, Complaint 10%

**Human baseline**: $0.50/conv → human_A = $4,500/mo, human_B = $18,000/mo

---

## Config 1 — Budget Bot (Gemini 2.5 Flash-Lite $0.10/$0.40, Web selective Visa+Weather, Last 3)

### Step 1 — Cost per turn (Guide intent, no web search)

| Turn | History tokens | Input total | Output | Cost model | Web | Total/turn |
|---|---|---|---|---|---|---|
| 1 | 0 | 1,830 | 180 | $0.000255 | $0 | $0.000255 |
| 2 | 260 | 2,090 | 180 | $0.000281 | $0 | $0.000281 |
| 3 | 520 | 2,350 | 180 | $0.000307 | $0 | $0.000307 |
| 4 | 780 (Last 3 cap) | 2,610 | 180 | $0.000333 | $0 | $0.000333 |
| 5 | 780 (capped) | 2,610 | 180 | $0.000333 | $0 | $0.000333 |
| 6 | 780 (capped) | 2,610 | 180 | $0.000333 | $0 | $0.000333 |
| 7 | 780 (capped) | 2,610 | 180 | $0.000333 | $0 | $0.000333 |

> **Last 3 cap**: Từ Turn 4 trở đi, history = 3 × 260 = 780 (không tăng nữa). Đây là advantage của Last 3 so với Full history.

### Step 2-3 — Cost per conversation × intent

**Guide (4 turns, no web)**: 0.000255 + 0.000281 + 0.000307 + 0.000333 = **$0.001176**
**Visa (4 turns, web Turn 1)**: $0.001176 + $0.008 = **$0.009176**
**Weather (4 turns, web Turn 1)**: **$0.009176**
**Booking/Complaint (1 turn, handoff)**: $0

**Scenario A avg** = 50%×0.001176 + 25%×0.009176 + 10%×0.009176 + 15%×0
= 0.000588 + 0.002294 + 0.000918 = **$0.003800**

**Scenario B (7 turns)**:
Guide 7t = 0.000255+0.000281+0.000307+4×0.000333 = **$0.002175**
Visa 7t = 0.001055+0.000281+0.000307+5×0.000333 = **$0.003303** (web T1 adds 800 tokens + $0.008)

Wait — recalculate Visa T1 with web: input = 500+0+1250+800+80 = 2630
T1 cost = 2630×0.10/1M + 180×0.40/1M + 0.008 = 0.000263+0.000072+0.008 = $0.001055 (web dominates)

Visa 7t = 0.001055 + 0.000281 + 0.000307 + 4×0.000333 = 0.001055+0.000281+0.000307+0.001332 = **$0.002975** + $0.008 web = **$0.010975**

Weather 7t = Guide 7t + web T1 = $0.002175 + $0.008 = **$0.010175**

**Scenario B avg** = 30%×0.002175 + 15%×0.010975 + 10%×0.010175 + 45%×0
= 0.000653 + 0.001646 + 0.001018 = **$0.003317**

### Step 4-5 — Monthly + vs human

| Item | Scenario A (4 turns) | Scenario B (7 turns) |
|---|---|---|
| Cost / conversation (avg) | $0.003800 | $0.003317 |
| Monthly cost | $34.20 | $119.41 |
| Human baseline | $4,500 | $18,000 |
| **Rẻ hơn human** | 117.9× | 150.7× |
| **Savings %** | 99.24% | 99.34% |

**Sanity check**: Cost/conv $0.003-0.004 — hợp lý cho cheap model. Monthly B ~$119 vẫn rất rẻ so với human $18,000.

---

## Config 2 — Premium Concierge (Claude Sonnet 4.6 $3.00/$15.00, Web selective Visa+Weather, Full history)

### Step 1 — Cost per turn (Guide intent, no web)

| Turn | History | Input | Output | Cost model | Web | Total/turn |
|---|---|---|---|---|---|---|
| 1 | 0 | 1,830 | 180 | $0.008190 | $0 | $0.008190 |
| 2 | 260 | 2,090 | 180 | $0.008970 | $0 | $0.008970 |
| 3 | 520 | 2,350 | 180 | $0.009750 | $0 | $0.009750 |
| 4 | 780 | 2,610 | 180 | $0.010530 | $0 | $0.010530 |
| 5 | 1,040 | 2,870 | 180 | $0.011310 | $0 | $0.011310 |
| 6 | 1,300 | 3,130 | 180 | $0.012090 | $0 | $0.012090 |
| 7 | 1,560 | 3,390 | 180 | $0.012870 | $0 | $0.012870 |

### Step 2-3 — Cost per conversation × intent

**Guide (4 turns)**: 0.008190+0.008970+0.009750+0.010530 = **$0.037440**
**Visa (4 turns, web T1)**: $0.037440 + $0.008 = **$0.045440**
**Weather (4 turns, web T1)**: **$0.045440**
**Booking/Complaint**: $0

**Scenario A avg** = 50%×0.037440 + 25%×0.045440 + 10%×0.045440 + 15%×0
= 0.018720 + 0.011360 + 0.004544 = **$0.034624**

**Scenario B (7 turns)**:
Guide 7t = 0.008190+0.008970+0.009750+0.010530+0.011310+0.012090+0.012870 = **$0.073710**
Visa 7t = $0.073710 + $0.008 = **$0.081710**
Weather 7t = **$0.081710**

**Scenario B avg** = 30%×0.073710 + 15%×0.081710 + 10%×0.081710 + 45%×0
= 0.022113 + 0.012257 + 0.008171 = **$0.042541**

### Step 4-5 — Monthly + vs human

| Item | Scenario A | Scenario B |
|---|---|---|
| Cost / conversation (avg) | $0.034624 | $0.042541 |
| Monthly cost | $311.62 | $1,531.48 |
| Human baseline | $4,500 | $18,000 |
| **Rẻ hơn human** | 14.5× | 11.7× |
| **Savings %** | 93.08% | 91.49% |

**Sanity check**: Cost/conv ~$0.035-0.043 — đắt hơn Budget Bot ~11×. Full history ở 7 turns: Turn 7 ($0.01287) đắt hơn Turn 1 ($0.00819) ~57%.

---

## Config 3 — Smart Mix (Flash-Lite cho Guide/Weather, DeepSeek V4 Pro $1.74/$3.48 cho Visa, Web selective, Last 5)

### Step 1 — Cost per turn

**Guide (Flash-Lite, no web)** — same per-turn as Budget Bot:
T1=$0.000255, T2=$0.000281, T3=$0.000307, T4-T5=$0.000333 (Last 5 cap kicks in at T6)

**Visa (DeepSeek V4 Pro, web Turn 1)**:
| Turn | History | Input | Output | Cost model | Web | Total |
|---|---|---|---|---|---|---|
| 1 | 0 | 2,630 | 180 | $0.005300 | $0.008 | $0.013300 |
| 2 | 260 | 2,890 | 180 | $0.005753 | $0 | $0.005753 |
| 3 | 520 | 3,150 | 180 | $0.006207 | $0 | $0.006207 |
| 4 | 780 | 3,410 | 180 | $0.006660 | $0 | $0.006660 |
| 5 | 1,040 | 3,670 | 180 | $0.007113 | $0 | $0.007113 |
| 6 | 1,300 (capped) | 3,670 | 180 | $0.007113 | $0 | $0.007113 |
| 7 | 1,300 (capped) | 3,670 | 180 | $0.007113 | $0 | $0.007113 |

**Weather (Flash-Lite, web Turn 1)**: same per-turn as Guide + $0.008 at T1

### Step 2-3 — Cost per conversation × intent

**Guide (4 turns, Flash-Lite)**: $0.001176
**Visa (4 turns, DeepSeek, web T1)**: 0.013300+0.005753+0.006207+0.006660 = **$0.031920**
**Weather (4 turns, Flash-Lite, web T1)**: $0.001176 + $0.008 = **$0.009176**
**Booking/Complaint**: $0

**Scenario A avg** = 50%×0.001176 + 25%×0.031920 + 10%×0.009176 + 15%×0
= 0.000588 + 0.007980 + 0.000918 = **$0.009486**

**Scenario B (7 turns)**:
Guide 7t (Flash-Lite, Last 5) = 0.000255+0.000281+0.000307+0.000333+0.000333+0.000333+0.000333 = **$0.002175**
Visa 7t (DeepSeek, web T1, Last 5) = 0.013300+0.005753+0.006207+0.006660+0.007113+0.007113+0.007113 = $0.053259 + $0.008 = **$0.061259**

Wait — the $0.008 web is already included in T1 ($0.013300 = $0.005300 model + $0.008 web). So Visa 7t = $0.053259.

Weather 7t (Flash-Lite, web T1) = Guide 7t + $0.008 = $0.002175 + $0.008 = **$0.010175**

**Scenario B avg** = 30%×0.002175 + 15%×0.053259 + 10%×0.010175 + 45%×0
= 0.000653 + 0.007989 + 0.001018 = **$0.009660**

### Step 4-5 — Monthly + vs human

| Item | Scenario A | Scenario B |
|---|---|---|
| Cost / conversation (avg) | $0.009486 | $0.009660 |
| Monthly cost | $85.37 | $347.76 |
| Human baseline | $4,500 | $18,000 |
| **Rẻ hơn human** | 52.6× | 51.7× |
| **Savings %** | 98.10% | 98.07% |

**Sanity check**: Cost/conv ~$0.009-0.010 — nằm giữa Budget Bot ($0.003-0.004) và Premium ($0.035-0.043). Visa tốn nhất (~$0.053/7t) vì DeepSeek V4 Pro + web search, nhưng chỉ 15% (B) nên avg vẫn thấp. DeepSeek V4 Pro rẻ hơn Sonnet ~4× → Smart Mix tiết kiệm hơn Premium ~4.4×.

---

## Quality + Speed estimate (qualitative)

| Config | Quality | Speed | Lý do |
|---|---|---|---|
| 1: Budget Bot | Low | High | Flash-Lite nhanh (~200ms/turn) nhưng quality thấp cho câu phức tạp; web search giúp Visa/Weather có real-time info |
| 2: Premium Concierge | High | Low | Sonnet output chất lượng cao, ít hallucination; Full history + model mạnh = chậm (~1-3s/turn); web search thêm 1-2s |
| 3: Smart Mix | Medium-High | Medium-High | DeepSeek V4 Pro cho Visa accuracy cao (sensitive topic); Flash-Lite cho Guide/Weather đủ tốt + nhanh; Last 5 cân bằng context vs cost |

---

## Bảng kiểm trước khi sang file tiếp theo

- [x] Tất cả 3 configs đã có cost/conv + monthly cho cả 2 scenarios
- [x] Đã so sánh từng config với human baseline ($0.50/conv)
- [x] Có quality + speed estimate cho mỗi config
- [x] Sanity check — cost/conv nằm trong $0.003–$0.043, không có số quá lạ

⚑ **Checkpoint 11:00**: ≥1 config đã tính cost xong &nbsp; · &nbsp; ⚑ **Checkpoint 11:20**: tất cả configs đã tính cost xong cho cả 2 scenarios.

Xong → mở `04-comparison-table.md`.

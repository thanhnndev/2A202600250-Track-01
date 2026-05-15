---
artifact: 3 — Outline 5 mục cho slide deck Analysis Report
bai-tap: 2 — Phân tích 2 sản phẩm AI (nhóm 2 học viên)
phase: Phase 3 — Dựng slide deck
time: 10 phút outline + 5 phút build slide
input: 1-research-notes.md + 2-comparison-table.md + screenshots/
nop-cuoi: Có gián tiếp — outline cho `analysis-report.pdf`
---

# 3 — Outline 5 mục cho slide deck: Notion AI vs Google Docs/Gemini

---

## Thông tin chung

- **Mã + tên**: A20-00250 (Nông Nguyễn Thành)
- **Ngành chọn**: C — Viết lách
- **Nhiệm vụ chung**: Viết email xin lỗi khách hàng vì giao hàng trễ 3 ngày do bão
- **Sản phẩm A**: Notion AI — https://www.notion.so/product/ai
- **Sản phẩm B**: Google Docs/Gemini — https://workspace.google.com/ai/
- **Prompt**: "Viết email cho khách hàng giải thích việc giao hàng trễ 3 ngày do bão. Tông lịch sự, có đề xuất bồi thường."

---

## S1 — Product Moment

### S1.1 — Bảng so sánh nhanh

| Yếu tố | Notion AI | Google Docs/Gemini |
|---|---|---|
| Entry point | Workspace page → "/" command | Blank doc → Gemini sidebar |
| Ý định người dùng | Edit/write trong context page có sẵn | Write mới hoặc edit doc |
| Surface chính | Inline AI trong doc | Sidebar chat panel |
| Đăng nhập/paywall | Đăng nhập, free trial giới hạn | Tài khoản Google, Gemini Business $20/mo |

### S1.2 — Bằng chứng

- Notion workspace với "/" AI command bar (entry)
- Google Docs với Gemini sidebar (entry)

### S1.3 — Nhận định

Notion AI tạo first impression tốt hơn cho người dùng đã có content trong workspace — inline action trực quan, không rời context. Gemini sidebar yêu cầu chuyển context (doc → panel → doc), gây friction cho user mới. Tuy nhiên, Gemini có advantage cho user viết từ blank document vì "Help me write" prompt rõ ràng.

---

## S2 — Workflow Evidence

### S2.1 — Luồng người dùng

```
TRƯỚC: User cần viết email xin lỗi khách hàng

TRONG Notion AI:
1. Mở Notion page (hoặc tạo page mới)
2. Gõ "/" → chọn AI action hoặc type prompt
3. AI generate inline → chọn Insert/Replace

TRONG Google Docs/Gemini:
1. Mở Google Doc (blank hoặc có sẵn)
2. Click "✨" hoặc "Help me write" → mở sidebar
3. Type prompt → Gemini draft → click "Insert" tại cursor

SAU: Copy/send email, lưu trong workspace/doc
```

### S2.2 — 3 Friction Areas

| Friction | Notion AI | Google Docs/Gemini |
|---|---|---|
| Physical load | 2 actions: "/" + Enter | 3 actions: sidebar → type → Insert |
| Cognitive burden | Thấp — select text → pick action | Trung bình — cần viết prompt rõ |
| User workarounds | Viết draft trước → AI chỉnh tone | Copy context từ Gmail vào sidebar |

### S2.3 — Bằng chứng

- Screenshots: Notion inline AI output, Gemini sidebar draft

### S2.4 — Nhận định

Notion AI giảm friction tốt hơn nhờ inline editing — user không rời context. Gemini sidebar tạo cognitive burden vì user phải "nghĩ" prompt thay vì chọn action. Tuy nhiên, Gemini advantage khi cần reference data từ Google ecosystem (Gmail, Drive).

---

## S3 — Output & Trust

### S3.1 — Chất lượng output

- **Notion AI**: Trả lời đúng, email ~180 từ, 5 đoạn, đề xuất bồi thường cụ thể (15% discount). Không bịa thông tin. Đầy đủ.
- **Google Docs/Gemini**: Trả lời đúng, email ~150 từ, 4 đoạn, đề xuất bồi thường chung ("free shipping"). Không bịa. Đầy đủ nhưng ngắn hơn.

### S3.2 — 6 Tín hiệu đáng tin

| Tín hiệu | Notion AI | Google Docs/Gemini |
|---|---|---|
| 1. Dẫn nguồn | N/A | N/A |
| 2. Disclaimer | ❌ Không | ✅ Có |
| 3. Fallback/out-of-scope | ❌ Không rõ | ✅ Safety filters |
| 4. Consistency | ✅ Cao | ✅ Cao |
| 5. User control | ✅ Insert/Replace/Regenerate | ✅ Insert/Regenerate + feedback |
| 6. Explanation | ❌ Không | ❌ Không |

### S3.3 — Nhận định

Notion AI tạo trust qua context awareness — AI "hiểu" page content, output consistent với tone workspace. Gemini tạo trust qua disclaimer + feedback system (thumb up/down) + Google brand. Về output quality, Notion AI chi tiết hơn, nhưng Gemini an toàn hơn với safety filters.

---

## S4 — Business Signal

### S4.1 — Định vị tam giác

- **Notion AI**: **Cân bằng** — Claude model (mạnh), $8/month add-on (rẻ), ~3-5s speed.
- **Google Docs/Gemini**: **Mạnh-đắt** — Gemini model (mạnh), $20/month (đắt), ~2-4s speed.

### S4.2 — Pricing pattern

| Yếu tố | Notion AI | Google Docs/Gemini |
|---|---|---|
| Mô hình giá | Add-on ($8/người/tháng) | Bundled (Gemini Business $20/người/tháng) |
| Free tier | Trial giới hạn | Free Gemini (giới hạn), Business paid |
| Paywall | Hết quota AI response | Tính năng nâng cao (Deep Research, etc.) |

### S4.3 — Nhận định

Notion AI dùng "add-on pricing" — giữ base product affordable, AI là optional upgrade. Gemini dùng "bundled pricing" — AI tích hợp vào workspace, user phải upgrade toàn bộ. Notion AI dễ adopt cho team nhỏ, Gemini phù hợp enterprise đã dùng Google Workspace.

---

## S5 — Product Judgment

### S5.1 — Verdict

- **Notion AI**: **Promising** — Inline editing + workspace context là differentiator, nhưng phụ thuộc Anthropic (model risk).
- **Google Docs/Gemini**: **Strong** — Google distribution + ecosystem integration tạo moat khó copy.

### S5.2 — User base + tăng trưởng

- **Notion AI**: Notion ~30M+ users (2024, công bố chính thức). AI adoption: chưa công khai %, nhưng AI là growth driver chính 2024-2025. Nguồn: Notion blog, Sacra analysis.
- **Google Docs/Gemini**: Google Workspace ~3B+ users (Google I/O 2024). Gemini trong Docs: available cho tất cả Google Workspace subscribers. Tăng trưởng: Gemini adoption growing fast trong enterprise. Nguồn: Google blog, Workspace pricing page.

### S5.3 — Doanh thu / pricing power

- **Notion AI**: Notion ARR ~$200-300M (Sacra estimate 2024). AI Add-on $8/user/mo → pricing power trung bình (user có thể skip AI). Chiến lược: freemium + add-on.
- **Google Docs/Gemini**: Google Workspace revenue ~$30B+/năm (Alphabet earnings). Gemini Business $20/user/mo → pricing power mạnh (bundled, hard to unbundle). Chiến lược: enterprise bundled.

### S5.4 — Moat phân tích

| Moat | Notion AI | Google Docs/Gemini |
|---|---|---|
| Data | Trung bình — workspace data nhưng không dùng để train model | Mạnh — Gmail, Docs, Drive data → fine-tune Gemini |
| Network | Mạnh — collaboration (multi-user docs) | Mạnh — Google Workspace collaboration |
| Switching cost | Trung bình — migrate khỏi Notion được nhưng mất workflow | Mạnh — Google ecosystem lock-in (Gmail + Drive + Docs) |
| Brand | Mạnh — Notion = productivity tool cho startup/creator | Rất mạnh — Google = default office suite |
| Distribution | Trung bình — PLG (product-led growth), word-of-mouth | Rất mạnh — Google Workspace pre-installed, enterprise sales |

**Notion AI moat chủ đạo**: Network effect (collaboration) + Brand. Dễ bị copy vì model (Claude) không độc quyền.
**Gemini moat chủ đạo**: Distribution + Data + Switching cost. Khó bị copy vì Google ecosystem.

### S5.5 — Data flywheel + feedback loop

- **Notion AI**: User dùng AI → output trong page → page shared → user khác thấy → dùng AI. Loop: weak compounding (không auto-improve model). Feedback: Không có rating system cho AI output.
- **Google Docs/Gemini**: User dùng Gemini → thumb up/down → improve model → Gemini better → user dùng nhiều hơn. Loop: compounding (Google dùng feedback để fine-tune Gemini). Feedback: Thumb up/down + implicit signals (insert rate, edit rate).

### S5.6 — Niche Down + AI Feature Map

**Notion AI**:
- Niche: Teams/startup đã dùng Notion workspace — AI augment knowledge management + content creation.
- AI Feature Map:
  - User Value: **Cao** — inline editing, context-aware, multiple AI actions (summarize, translate, change tone).
  - User Alignment: **Cao** — AI actions match user intent trong workspace workflow.
  - Business Value: **Cao** — AI Add-on $8/user/mo tăng ARPU, reduce churn.

**Google Docs/Gemini**:
- Niche: Enterprise dùng Google Workspace — AI cho productivity at scale.
- AI Feature Map:
  - User Value: **Trung bình-Cao** — Gemini mạnh nhưng output generic, cần prompt rõ.
  - User Alignment: **Cao** — Gemini tích hợp Gmail/Calendar/Drive → context-rich.
  - Business Value: **Cao** — Gemini Business $20/user/mo tăng Workspace revenue, enterprise stickiness.

### S5.7 — Spark → Loop → System

- **Notion AI**: **Loop** — AI đã được integrate sâu vào workflow (inline actions, templates), nhưng chưa thành "system" (chưa tự động hóa toàn bộ content pipeline). Dự báo 12 tháng: Notion sẽ thêm AI agent capabilities (auto-create pages, auto-summarize meetings), tiến tới System.
- **Google Docs/Gemini**: **System** — Gemini đã là system trong Google Workspace: AI tự draft email (Gmail), tự summarize meetings (Meet), tự analyze data (Sheets). Docs là 1 part của system. Dự báo 12 tháng: Gemini sẽ deepen enterprise integration (auto-workflows, RPA-like features).

### S5.8 — Liên hệ Lab 1 case (Chegg)

**Notion AI có rủi ro disruption tương tự Chegg không?**
- **Có, nhưng thấp hơn Chegg.** Notion AI phụ thuộc vào Anthropic (Claude) — nếu Anthropic ra standalone writing product hoặc OpenAI integrate GPT vào competing workspace, Notion mất model advantage. Tuy nhiên, Notion có network effect (collaboration) + workspace data mà Chegg không có.

**Google Docs/Gemini có rủi ro disruption không?**
- **Rất thấp.** Google có distribution (3B+ users), data moat (Gmail, Drive, Docs), và model (Gemini) tự sở hữu. Chỉ bị disruption nếu có platform mới thay thế entire Google Workspace — unlikely trong 5-10 năm.

**Bài học từ Lab 1 áp dụng cho 2 sản phẩm**:
1. **Đừng phụ thuộc model của đối thủ**: Notion dùng Claude — nếu Anthropic cut access hoặc raise price, Notion stuck. Chegg không có model risk này nhưng có distribution risk (Google SEO). Lesson: Own your core dependency.
2. **Distribution moat > Content moat**: Chegg mất vì distribution (SEO) bị phá. Gemini có distribution (Google Workspace) — mạnh nhất trong ngành. Notion distribution yếu hơn (PLG) — cần strengthen.
3. **Integrate AI vào workflow hiện có, đừng build product mới**: Chegg build Cheggmate (product mới) → fail. Notion AI integrate inline → success. Gemini integrate vào Docs/Gmail/Sheets → success. Lesson: AI augment, don't replace.

---

## Bảng kiểm trước khi build slide

- [x] S1 → S4 đã điền đầy đủ.
- [x] S5.1 + S5.6 + S5.7 + S5.8 đã hoàn thành.
- [x] S5.2 → S5.5 đã hoàn thành.
- [x] Mỗi nhận định nối được về ảnh/log/số liệu cụ thể.
- [x] Verdict nhất quán với phân tích moat và giai đoạn.

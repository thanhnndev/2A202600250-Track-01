---
artifact: 2 — Bảng so sánh 2 sản phẩm theo 5 mục
bai-tap: 2 — Phân tích 2 sản phẩm AI (nhóm 2 học viên)
phase: Chuyển giao Phase 2 → Phase 3
time: 5 phút
input: 1-research-notes.md + screenshots/
nop-cuoi: Không — file trung gian
---

# 2 — Bảng so sánh Notion AI vs Google Docs/Gemini theo 5 mục

---

## Phần A — Bảng so sánh 5 mục

| Mục | Notion AI | Google Docs/Gemini |
|---|---|---|
| **S1 — Product Moment** | Entry: Workspace page → "/" command hoặc "Ask AI" button. Ý định: Viết/edit content trong context workspace đã có. Surface: Inline AI action trong doc. | Entry: Blank doc → Gemini sidebar ("✨" button). Ý định: Viết content mới hoặc edit doc hiện có. Surface: Sidebar chat panel + insert vào doc. |
| **S2 — Workflow Evidence** | Trước: Đã có content trong Notion page. Trong: "/" → AI prompt → inline response → insert/replace. Sau: Content nằm trong page, dễ share/collaborate. Friction: Cần learn "/" commands, AI giới hạn ở free tier. | Trước: Blank doc hoặc doc có sẵn. Trong: Sidebar → type prompt → Gemini draft → insert at cursor. Sau: Content trong Google Doc, dễ share. Friction: Chuyển context giữa doc và sidebar. |
| **S3 — Output & Trust** | Output: ~180 từ, chi tiết, đề xuất bồi thường cụ thể (15% discount). Không dẫn nguồn, không disclaimer. Trust: Inline editing + context awareness tạo cảm giác "AI hiểu doc của tôi". | Output: ~150 từ, ngắn gọn, professional. Có disclaimer ("may display inaccurate info"). Có thumb up/down. Trust: Google brand + feedback system, nhưng output generic. |
| **S4 — Business Signal** | AI Add-on: $8/tháng/người (on top of Notion plan). Free trial giới hạn. Định vị: Cân bằng — AI augment workspace hiện có, không thay thế. | Gemini Business: $20/tháng/người. Free tier có giới hạn. Định vị: Mạnh-đắt — Gemini mạnh, tích hợp Google ecosystem, nhưng giá cao. |
| **S5 — Product Judgment** | **Promising** — AI augment tốt cho workspace, inline editing là killer feature, nhưng moat yếu (dùng Claude, có thể copy). | **Strong** — Google distribution + Gemini model + ecosystem integration tạo moat mạnh, nhưng output generic có thể bị commoditize. |

---

## Phần B — Đối chiếu 3 friction areas

- **Physical load**: Notion AI thắng — inline "/" command (1 action) vs Gemini sidebar (mở sidebar → type → insert = 3 actions). Notion ít click hơn, không rời context.
- **Cognitive burden**: Notion AI thắng — người dùng không cần prompt engineering, chỉ cần select text → pick action ("Change tone", "Summarize"). Gemini cần viết prompt rõ hơn trong sidebar.
- **User workarounds**: Notion AI — user tự viết draft trước rồi dùng AI chỉnh tone (không phải workaround, mà là workflow intended). Gemini — user phải copy-paste từ Gmail/context khác vào sidebar vì Gemini không auto-read email context nếu không cho permission.

---

## Phần C — Đối chiếu 6 trust signals

| Tín hiệu đáng tin | Notion AI | Google Docs/Gemini |
|---|---|---|
| 1. Dẫn nguồn | Không áp dụng (AI writing) | Không áp dụng (AI writing) |
| 2. Disclaimer khi không chắc | Không có | ✅ Có ("may display inaccurate info") |
| 3. Fallback / dừng lại khi out-of-scope | Không rõ — AI trả lời mọi prompt | ✅ Gemini có safety filters (từ chối harmful content) |
| 4. Consistency | Cao — Claude cho output consistent | Cao — Gemini consistent, có thumb up/down để improve |
| 5. User control | ✅ Insert/Replace/Regenerate + inline select | ✅ Insert/Regenerate + thumb up/down |
| 6. Explanation | Không — AI không giải thích "tại sao viết vậy" | Không — Gemini cũng không giải thích |

---

## Phần D — Định vị 2 sản phẩm trên Cost-Capability-Speed

- **Notion AI nghiêng về**: **Cân bằng** — model Claude (mạnh) nhưng giá $8/month add-on (rẻ), speed ~3-5s (trung bình). Value: AI augment workspace, không standalone.
- **Google Docs/Gemini nghiêng về**: **Mạnh-đắt** — Gemini model mạnh, tích hợp Google ecosystem, speed ~2-4s (nhanh), nhưng $20/tháng (đắt hơn Notion AI 2.5×).

---

## Phần E — Verdict sơ bộ

- **Notion AI — verdict sơ bộ**: **Promising**
  - Lý do: Inline editing + workspace context là differentiator mạnh, nhưng phụ thuộc vào Anthropic (model risk) và moat yếu.
- **Google Docs/Gemini — verdict sơ bộ**: **Strong**
  - Lý do: Google distribution + Gemini model + ecosystem integration (Gmail, Drive, Calendar) tạo defensibility cao. Output generic là rủi ro nhưng được mitigated bởi speed và integration.

---

## Bảng kiểm trước khi sang Bước 3

- [x] Mỗi ô có ít nhất 1-2 câu.
- [x] Mỗi nhận định nối được về ảnh/log trong `1-research-notes.md`.
- [x] Đã định vị cả 2 sản phẩm trên Cost-Capability-Speed.
- [x] Đã có verdict sơ bộ.

Sang `3-FINAL-analysis-outline.md` để dựng outline đầy đủ.

---
artifact: 1 — Ghi chú nghiên cứu khi test 2 sản phẩm AI
bai-tap: 2 — Phân tích 2 sản phẩm AI (nhóm 2 học viên)
phase: Phase 2 — Thử nghiệm + chụp ảnh + research (20 phút)
time: 20 phút
input: group-members.md
nop-cuoi: Không — file trung gian
---

# 1 — Ghi chú nghiên cứu khi test Notion AI vs Google Docs/Gemini

---

## Phần A — Setup chung

- **Nhiệm vụ chung**: Viết email cho khách hàng giải thích việc giao hàng trễ 3 ngày do bão, tông lịch sự, có đề xuất bồi thường.
- **Câu prompt chính xác**: "Viết email cho khách hàng giải thích việc giao hàng trễ 3 ngày do bão. Tông lịch sự, có đề xuất bồi thường."
- **Loại tài khoản dùng**:
  - Notion AI: Free trial (AI Add-on) — model: Claude/Sonnet (Notion dùng Anthropic)
  - Google Docs/Gemini: Gemini Business trial ($20/tháng) — model: Gemini
- **Trình duyệt + thời gian test**: Chrome, 15/05/2026, 10:30 AM ICT

---

## Phần B — Log Notion AI

**Tên sản phẩm A**: Notion AI
**URL**: https://www.notion.so
**Model dưới mui xe**: Claude (Anthropic) — Notion partnership với Anthropic

### B.1 — Entry point + lần chạm đầu

- Trang chủ Notion hiển thị workspace với các page. AI feature được access qua "/" command hoặc nút "Ask AI" ở góc phải.
- Có hint/sample prompt: Notion gợi ý "Summarize", "Translate", "Fix spelling & grammar", "Change tone".
- Cần đăng nhập để dùng AI. Free tier có giới hạn số lần AI response.
- Ảnh: `screenshots/product-A-1-entry.png` (Notion workspace với AI prompt bar)

### B.2 — Khi gõ prompt + nhận output

- Thời gian phản hồi: ~3-5 giây (streaming).
- Output dài: ~180 từ (5 đoạn: greeting, explanation, apology, compensation offer, closing).
- Output không dẫn nguồn — AI writing, không cần citation.
- Không có disclaimer/cảnh báo.
- Email chất lượng tốt, tông lịch sự, có đề xuất bồi thường (giảm giá 15% đơn hàng tiếp theo).
- Ảnh: `screenshots/product-A-2-input.png`, `screenshots/product-A-3-output.png`

### B.3 — Phản hồi sau khi nhận output

- Có nút "Regenerate" — generate lại.
- Có "Insert below", "Replace selection" — dễ tích hợp vào page.
- Không có gợi ý câu hỏi tiếp theo.
- Lưu lịch sử trong Notion page.
- Không có thumb up/down.

### B.4 — Quan sát nổi (3 quan sát)

1. **Inline editing mạnh**: Notion AI có thể chọn đoạn text trong page → "Change tone" → chuyển từ formal → friendly. Đây là điểm khác biệt lớn so với chat-based AI.
2. **Template system**: Notion có sẵn email templates (follow-up, apology, proposal) — AI fill vào template thay vì generate từ scratch.
3. **Context awareness**: Notion AI có thể đọc toàn bộ page content (các section trước đó) để generate consistent content — ví dụ: nếu page có info công ty, AI tự dùng tên công ty trong email.

---

## Phần C — Log Google Docs/Gemini

**Tên sản phẩm B**: Google Docs với Gemini
**URL**: https://docs.google.com
**Model dưới mui xe**: Google Gemini

### C.1 — Entry point + lần chạm đầu

- Google Docs mở với blank document. Gemini sidebar xuất hiện ở góc phải (nút "✨" hoặc "Help me write").
- Có sample prompt: "Help me write", "Help me visualize", "Summarize".
- Cần tài khoản Google. Gemini Business yêu cầu subscription $20/tháng.
- Ảnh: `screenshots/product-B-1-entry.png` (Google Docs với Gemini sidebar)

### C.2 — Khi gõ prompt + nhận output

- Thời gian phản hồi: ~2-4 giây (streaming, nhanh hơn Notion AI).
- Output dài: ~150 từ (4 đoạn, ngắn gọn hơn Notion AI).
- Output không dẫn nguồn.
- Có disclaimer nhỏ ở dưới: "Gemini may display inaccurate info, including about people, so double-check its responses."
- Email chất lượng tốt nhưng tông hơi generic — ít personalization hơn Notion AI.
- Đề xuất bồi thường: "free shipping on your next order" (không cụ thể bằng Notion AI's 15% discount).
- Ảnh: `screenshots/product-B-2-input.png`, `screenshots/product-B-3-output.png`

### C.3 — Phản hồi sau khi nhận output

- Có "Insert" button — chèn vào document tại cursor position.
- Có "Regenerate" — generate lại.
- Có "Draft with Gmail" — Gemini có thể access Gmail context (nếu cho phép).
- Lưu lịch sử trong Gemini sidebar.
- Có thumb up/down feedback.

### C.4 — Quan sát nổi (3 quan sát)

1. **Speed nhanh hơn**: Gemini response nhanh hơn Notion AI (~2-4s vs 3-5s).
2. **Google ecosystem integration**: Gemini có thể access Gmail, Calendar, Drive — nếu email cần reference đơn hàng cụ thể, Gemini có thể pull data từ Gmail.
3. **Generic output**: Gemini viết email ngắn gọn, professional nhưng ít "personality" hơn Notion AI. Có lẽ Gemini được trained để safe hơn.

---

## Phần D — First impressions

1. **Sản phẩm nào "cảm giác" dễ dùng hơn lần đầu? Tại sao?**
   - **Notion AI** — vì inline editing (select text → AI action) trực quan hơn Gemini sidebar. Người dùng không phải chuyển context giữa doc và chat panel.

2. **Sản phẩm nào "cảm giác" cho output đáng tin hơn? Tại sao?**
   - **Notion AI** — email dài hơn, chi tiết hơn, đề xuất bồi thường cụ thể (15% discount). Gemini output ngắn, generic, đề xuất bồi thường mơ hồ ("free shipping").

3. **Câu hỏi chưa trả lời được sau 20 phút test**:
   - Notion AI dùng model nào chính xác? (Claude Sonnet hay khác?) — cần check pricing page.
   - Gemini trong Docs có khác Gemini standalone không?
   - Cả 2 sản phẩm có AI writing quality khác nhau cho tiếng Việt không? (Lab yêu cầu test tiếng Việt)

---

## Bảng kiểm trước khi sang Bước 2

- [x] Câu prompt giống y nhau cho cả 2 sản phẩm.
- [x] Đã chụp tối thiểu 3 ảnh cho mỗi sản phẩm.
- [x] Mỗi quan sát có ảnh / log tham chiếu.
- [x] First impressions ghi rõ.

Sang `2-comparison-table.md` để dựng bảng so sánh.

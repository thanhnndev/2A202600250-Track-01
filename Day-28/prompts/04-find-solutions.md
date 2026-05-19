# Prompt 04 — AI hỗ trợ QUYẾT ĐỊNH cách làm (Build/Buy/Boost/Partner)

> **Dùng khi**: `worksheet/02-solution/2-FINAL-solution.md` — nhóm muốn so pattern + đối chiếu cách làm trước khi chốt.
>
> **Công cụ**: ChatGPT / Claude / Gemini.

---

## TRƯỚC KHI HỎI AI (nhóm tự nghĩ)

- Team nhóm **có gì thật sự** (không phải "sẽ có")?
- Kiểu bài này đã có ai (ngành khác) giải chưa? (gần như luôn có)
- Nhóm muốn "tự build" vì **CẦN** hay vì **THÍCH**? (kiểm tra ego)

---

## PROMPT (copy, thay [ô vuông])

```
Quick Win của nhóm tôi (khóa học AI20k, track [TÊN TRACK]):
- Input: [GÌ VÀO]
- Output mong muốn: [GÌ RA]
- Người dùng: [AI DÙNG, BAO NHIÊU, TRÌNH ĐỘ]
- Ràng buộc: ngân sách pilot nhỏ, ưu tiên tool/API có sẵn, output rủi ro cao cần người review,
  trả lời theo tài liệu phải dẫn nguồn.

PHÂN TÍCH TRUNG THỰC:
1. Bỏ hết ngữ cảnh AI20k — bài này THỰC CHẤT là kiểu gì?
   (vd: "câu hỏi → trả lời từ tài liệu có nguồn", "văn bản → dữ liệu có cấu trúc")
2. Tìm 3–5 dạng giải pháp TƯƠNG TỰ ở bối cảnh khác (mô tả dạng, không cần brand thật). Họ dùng gì?
3. BUY: có loại tool/API sẵn nào làm được? Hạn chế lớn nhất?
4. BOOST (model có sẵn + dữ liệu/prompt riêng): khả thi không? Cần gì?
5. BUILD từ đầu: tốn bao lâu THẬT (nhân 2–3 lần ước lượng lạc quan)? Khi nào MỚI nên Build?
6. CẢNH BÁO: nhóm có đang muốn Build vì EGO không? (80–90% case nội bộ là Boost/Buy)
7. Nếu chọn SAI cách làm — mất gì? Bao lâu để sửa?
```

---

## SAU KHI AI TRẢ LỜI (kiểm tra)

- [ ] Pattern match — có **đúng là giống** không, hay chỉ giống bề ngoài?
- [ ] Thông tin tool/vendor có thể **đã cũ** (AI training data). Không tin tuyệt đối số liệu.
- [ ] "Build mất X tuần" — hỏi người biết code trong nhóm, đừng tin estimate của AI.
- [ ] "80–90% là Boost" — nhóm có thuộc 10–20% thật sự cần Build không? Vì sao?

---

## PHẢN BIỆN

- AI không biết **team dynamics** của nhóm. "Khả thi" theo AI ≠ khả thi với nhóm này trong lab.
- So sánh vendor từ AI có thể **lỗi thời** (giá, tính năng đổi nhanh).
- "Tự build" là quyết định **khó rút lại**. Trong pilot nhỏ, mặc định nên nghiêng Boost/Buy.
- Hỏi thẳng: *"Nếu chọn sai approach — mất gì? Bao lâu để sửa?"*

---

*Prompt 04 · Approach challenge. AI gợi ý + cảnh báo — nhóm chọn.*

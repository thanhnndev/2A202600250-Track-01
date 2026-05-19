# Prompt 01 — AI hỗ trợ BÓC TÁCH công cụ lớn

> **Dùng khi**: `worksheet/01-frame/1-intake-breakdown.md` — nhóm cần tách công cụ lớn của track thành 5–8 use case nhưng đang bí hoặc muốn kiểm danh sách của mình.
>
> **Công cụ**: ChatGPT / Claude / Gemini.

---

## TRƯỚC KHI HỎI AI (nhóm tự nghĩ)

- Nhóm đã tự liệt kê được mấy use case rồi? (chưa có dòng nào = nên brainstorm tay trước, đừng để AI mồi)
- Công cụ lớn này phục vụ ai? (học viên / coach / instructor)
- Có module nào nhóm thấy *chắc chắn* nằm trong tool này không?

> Nếu chưa tự nghĩ ra ≥3 dòng → brainstorm tay 2 phút trước khi hỏi AI. AI để **kiểm tra và bổ sung**, không để thay nhóm nghĩ.

---

## PROMPT (copy, thay [ô vuông])

```
Bối cảnh: Khóa học AI20k đang xây "AI20k Learning OS" — hệ công cụ AI hỗ trợ học và vận hành khóa.
Track của nhóm tôi: [TÊN TRACK]
Công cụ lớn stakeholder muốn (lời của nhóm): [DÁN TỪ worksheet/00-context.md]
Người dùng: [HỌC VIÊN / COACH / INSTRUCTOR]
Đây là danh sách use case nhóm tôi tự nghĩ: [DÁN DANH SÁCH — kể cả còn thiếu]

Hãy PHÂN TÍCH (không chốt thay tôi):
1. Danh sách của tôi có dòng nào thực ra là TÍNH NĂNG VỤN, không phải use case làm được riêng? Chỉ rõ.
2. Có dòng nào PHỤ THUỘC dòng khác (không làm riêng được)? Gợi ý gộp/tách lại.
3. Bổ sung tối đa 3 use case tôi CÓ THỂ đã bỏ sót — nhưng chỉ những cái hợp bối cảnh khóa học nhỏ.
4. Trong các use case, cái nào có vẻ CHỨNG MINH ĐƯỢC NHANH (≤1–2 tuần)? Vì sao?
5. CẢNH BÁO: use case nào nghe hay nhưng quá lớn để pilot trong bối cảnh 1 khóa học?
```

---

## SAU KHI AI TRẢ LỜI (kiểm tra)

- [ ] Use case AI bổ sung có **hợp bối cảnh AI20k thật** không, hay chung chung kiểu sản phẩm lớn?
- [ ] "Phụ thuộc nhau" — nhóm có **đồng ý** với phân tích của AI không? AI nhìn từ ngoài.
- [ ] AI có **gộp mất** một use case nhóm thấy thật sự quan trọng không?
- [ ] Danh sách cuối là **của nhóm** (đã chỉnh từ phán đoán riêng), không phải bê nguyên của AI.

---

## PHẢN BIỆN

- AI không biết AI20k vận hành thật thế nào (Discord/LMS/lab ra sao). Use case phải nhóm xác nhận.
- "Chứng minh nhanh" theo AI chỉ là gợi ý — Bước Quick Win nhóm sẽ tự chấm điểm lại.
- Danh sách AI dài hơn ≠ tốt hơn. 5–8 use case **rõ và độc lập** quan trọng hơn liệt kê nhiều.

---

*Prompt 01 · Tool Breakdown. AI kiểm danh sách — nhóm chốt danh sách.*

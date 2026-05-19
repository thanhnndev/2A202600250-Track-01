# Prompt 02 — AI hỗ trợ CHẤM & PHẢN BIỆN Quick Win

> **Dùng khi**: `worksheet/01-frame/2-quick-win.md` — nhóm đã có danh sách use case, cần chấm điểm gợi ý + soi bẫy trước khi chốt Quick Win.
>
> **Công cụ**: ChatGPT / Claude / Gemini.

---

## TRƯỚC KHI HỎI AI (nhóm tự nghĩ)

- Danh sách use case đã đủ rõ chưa? (thiếu info = chấm sai)
- Nhóm có **bias** không? (thích cái quen thuộc? thích cái dễ?)
- Nhắc lại: *Quick Win = cái CHỨNG MINH ĐƯỢC NHANH và CÓ NGƯỜI ỦNG HỘ — không phải cái dễ nhất.*

---

## PROMPT (copy, thay [ô vuông])

```
Đây là các use case của nhóm tôi (track [TÊN TRACK], khóa học AI20k):
[DÁN DANH SÁCH TỪ worksheet/01-frame/1-intake-breakdown.md]

Ràng buộc: ngân sách pilot nhỏ, ưu tiên tool/API có sẵn, dữ liệu trong lab là mẫu/giả định,
feedback AI là formative không phải điểm chính thức.

Giúp tôi PHÂN TÍCH (KHÔNG chọn thay — nhóm tôi sẽ chọn):
1. Chấm mỗi use case theo: Tác động(30%) · Khả thi(25%) · Bằng chứng nhanh(25%) · Rủi ro nếu sai(20%).
   Ghi rõ vì sao mỗi điểm.
2. Với MỖI use case: 1 lý do NÊN chọn + 1 lý do KHÔNG nên chọn.
3. Use case nào RỦI RO CAO NHẤT nếu fail trong bối cảnh khóa học? (mất uy tín với học viên? sai điểm?)
4. Use case nào có BẰNG CHỨNG NHANH NHẤT (chứng minh trong ≤2 tuần của 1 khóa)?
5. BẪY: use case nào "nghe hay / dễ demo" nhưng thực ra rủi ro cao hoặc tác động ảo?
6. Nếu nhóm chọn SAI — hậu quả gì trong bối cảnh khóa học? Quay lại được không?
```

---

## SAU KHI AI TRẢ LỜI (kiểm tra)

- [ ] Điểm số — nhóm có **đồng ý** không? AI chấm dựa trên *chữ*; nhóm biết bối cảnh thật.
- [ ] "Có người ủng hộ" — AI **không biết** ai trong AI20k thật sự ủng hộ. Nhóm phải tự xác định.
- [ ] "Khả thi" — AI có biết năng lực nhóm + tool có sẵn không? Thường là không.
- [ ] Phần "bẫy" — có câu nào **đúng thật** không, hay AI chỉ nói chung chung?

---

## PHẢN BIỆN

- AI **cho điểm = gợi ý**. Quyết định là của nhóm.
- Quick Win fail → ảnh hưởng uy tín nhóm. Chọn cẩn thận.
- "Tác động cao" nhưng **không ai ủng hộ = KHÔNG phải Quick Win**. Ủng hộ > Tác động.
- AI không biết "politics" của khóa học (coach bận, instructor ưu tiên gì) — nhóm tự cân.

---

*Prompt 02 · Quick Win challenge. AI chấm gợi ý — nhóm quyết.*

# Prompt 03 — AI hỗ trợ SOI khung vấn đề

> **Dùng khi**: `worksheet/01-frame/3-FINAL-problem-framing.md` — nhóm đã viết nháp khung vấn đề, muốn tìm lỗ hổng trước khi qua Mốc 2.
>
> **Công cụ**: ChatGPT / Claude / Gemini.

---

## TRƯỚC KHI HỎI AI (nhóm tự nghĩ)

- Khung vấn đề của nhóm đã chỉ rõ **một nhóm người + một khoảnh khắc** chưa, hay còn "người dùng nói chung"?
- Pain nhóm nêu có **số liệu** hay chỉ **cảm tính**?
- Nhóm đã có **baseline** chưa? Nếu chưa, định đo bằng gì?

> Viết nháp khung vấn đề **trước**, rồi đưa cho AI soi. Đừng nhờ AI viết khung hộ.

---

## PROMPT (copy, thay [ô vuông])

```
Đây là khung vấn đề nháp của nhóm tôi cho Quick Win (track [TÊN TRACK], khóa học AI20k):
[DÁN NHÁP TỪ worksheet/01-frame/3-FINAL-problem-framing.md: ai đau · đau ở đâu · baseline · chỉ số · ràng buộc]

Hãy PHẢN BIỆN khung này (không viết lại hộ tôi):
1. Phần "ai đau" đã đủ CỤ THỂ chưa, hay vẫn chung chung? Nếu chung chung, hỏi tôi đúng câu để làm rõ.
2. Pain này có SỐ LIỆU hay chỉ CẢM TÍNH? Nếu cảm tính, gợi ý cách lấy số trước pilot
   (chỉ dùng dữ liệu mẫu/giả định trong bối cảnh 1 khóa học).
3. Baseline của tôi có thật sự là baseline không, hay là kỳ vọng? Thiếu baseline thì đo "tốt hơn" kiểu gì?
4. Chỉ số thành công có ĐO ĐƯỢC + có NGƯỠNG không? Chỉ ra chỉ số nào mơ hồ.
5. Có ràng buộc nào của khóa học (privacy / human review / dẫn nguồn / formative) tôi BỎ SÓT không?
6. Một người ngoài đọc khung này có hiểu CHÍNH XÁC vấn đề không? Chỗ nào dễ hiểu sai?
```

---

## SAU KHI AI TRẢ LỜI (kiểm tra)

- [ ] Câu AI bảo "chung chung" — nhóm có **đồng ý** không? Hay nhóm có chi tiết AI chưa biết?
- [ ] Cách lấy số AI gợi ý có **khả thi trong 1 khóa học** không?
- [ ] AI có nhầm "kỳ vọng" thành "baseline" giống nhóm không? Sửa lại cho đúng.
- [ ] Ràng buộc AI nhắc — đã đối chiếu `worksheet/00-context.md` chưa?

---

## PHẢN BIỆN

- Vấn đề SAI mà Pilot Plan viết hay → vẫn FAIL. Đây là phần đáng đầu tư nhất.
- Metric không có **baseline = vô nghĩa** ("tăng 30%" — so với cái gì?).
- AI không biết học viên/coach AI20k thật sự kẹt ở đâu — nhóm phải dựa trên hiểu biết khóa học, không bịa số.
- AI giúp **tìm lỗ hổng**, không phải **lấp hộ**. Lấp bằng hiểu biết của nhóm.

---

*Prompt 03 · Problem Framing challenge. AI soi lỗ hổng — nhóm lấp.*

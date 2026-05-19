# Template — Ví dụ Demo / Mockup / Flow

> Dùng cùng `worksheet/02-solution/2-FINAL-solution.md` (phần Demo/Mockup/Flow). Chọn **1 dạng** hợp Quick Win nhất, copy khung tương ứng rồi điền nội dung của nhóm. Vẽ tay/ASCII/bảng đều được — **rõ quan trọng hơn đẹp**. Artifact trực quan là **BẮT BUỘC** (Cổng 4); demo chạy được chỉ là điểm cộng.

---

## Dạng 1 — Mockup 3 màn hình

Phác 3 màn hình người dùng đi qua. Mỗi màn ghi: user thấy gì + bấm gì.

```text
┌─ Màn 1: ……………… ─┐   ┌─ Màn 2: ……………… ─┐   ┌─ Màn 3: ……………… ─┐
│                      │   │                      │   │                      │
│ [user thấy gì]       │ → │ [AI trả gì]          │ → │ [user làm gì tiếp]   │
│                      │   │ [chỗ người review?]  │   │                      │
│ Hành động: …………       │   │ Hành động: …………       │   │ Hành động: …………       │
└──────────────────────┘   └──────────────────────┘   └──────────────────────┘
```

*Hợp khi*: Quick Win có giao diện người dùng tương tác.

---

## Dạng 2 — Luồng người dùng (before / after)

So công việc hiện tại vs sau khi có AI. Làm nổi bật chỗ AI cắt bớt bước.

```text
TRƯỚC (hiện tại):
  Bước 1 ……  →  Bước 2 ……  →  Bước 3 ……  →  Bước 4 ……   (……  phút, …… người)

SAU (có AI):
  Bước 1 ……  →  [AI làm ……]  →  [người review ……]  →  Xong   (……  phút)

Khác biệt rõ nhất: ………………………………………………
```

*Hợp khi*: giá trị chính là rút ngắn / bỏ bước trong một quy trình.

---

## Dạng 3 — Luồng prompt

Input vào → prompt/model xử lý → output ra. Ghi rõ nguồn dữ liệu nếu trả lời theo tài liệu.

```text
[INPUT: ……………]
      │
      ▼
[B1: lấy dữ liệu/nguồn …………]  ──(tài liệu khóa học → phải dẫn nguồn)
      │
      ▼
[B2: prompt + model ……………]
      │
      ▼
[OUTPUT: ……………]  ──(rủi ro cao → người review tại đây)
      │
      ▼
[Nếu thiếu nguồn → trả "không biết", không bịa]
```

*Hợp khi*: giải pháp là một chuỗi gọi model (hỏi–đáp, tóm tắt, phân loại).

---

## Dạng 4 — Luồng agent

Agent tự đi nhiều bước. Ghi rõ điểm dừng để người review.

```text
   ┌─────────── vòng lặp ───────────┐
   ▼                                │
[Quan sát ……]                       │
   │                                │
   ▼                                │
[Quyết định ……]                     │
   │                                │
   ▼                                │
[Hành động ……] ──► [Người review ……] ──► tiếp / dừng
   │                                │
   └────────────────────────────────┘
[Điều kiện dừng agent: ……………]
```

*Hợp khi*: tool tự thực hiện chuỗi hành động (triage, tự kiểm nhiều vòng).

---

## Dạng 5 — Ví dụ vào–ra (sample input/output)

Cách nhanh nhất để stakeholder hiểu tool làm gì: 1 ví dụ thật.

```text
INPUT (ví dụ thật, lấy từ bối cảnh AI20k — dùng dữ liệu mẫu):
  """
  ……………………………………
  """

OUTPUT mong muốn:
  """
  ……………………………………
  (nếu theo tài liệu: kèm trích nguồn …………)
  """

Vì sao ví dụ này thuyết phục: ……………………………………
Input nào sẽ làm tool LỘ ĐIỂM YẾU: …………………………… (chuẩn bị câu trả lời)
```

*Hợp khi*: chất lượng output là điểm bán chính (chấm bài, sinh quiz, trả lời có nguồn).

---

## Sau khi phác — kiểm qua mắt stakeholder

```text
- Nhìn 20 giây có hiểu user làm gì → nhận lại gì không?
- Thấy rõ chỗ AI tự làm vs chỗ người review chưa?
- Có gì "đẹp nhưng rỗng" (trang trí thay vì làm rõ flow) không?
```

---

*Template demo examples · D28 · liên kết handbook §A6.*

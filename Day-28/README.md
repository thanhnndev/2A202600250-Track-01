> **Repo:** https://github.com/VinUni-AI20k/Day28-Track01-AI-Pilot-Plan

# Day 28 — AI20k Learning OS: từ một bài toán mơ hồ → một AI Pilot Plan đủ để quyết

Day 28 có **1 lab lớn theo nhóm 3** (~70 phút), chạy trọn một vòng triển khai AI trên một đề bài thật trong chính khóa AI20k:

> Lãnh đạo chương trình muốn xây **AI20k Learning OS** — một hệ công cụ AI hỗ trợ học và vận hành khóa (~500 học viên): Discord, LMS, lab, quiz, chấm bài, cá nhân hóa lộ trình, hỗ trợ coach, recap lớp live. **Không build hết cùng lúc được.** Mỗi nhóm nhận 1 track (1 công cụ lớn), tách nhỏ, chọn Quick Win, viết AI Pilot Plan để xin pilot.

Đây đúng là việc một PM/PO AI làm ngoài doanh nghiệp: stakeholder giao một "công cụ AI" quá lớn — bạn phải tách nhỏ, chọn đúng phần làm trước, và bảo vệ lựa chọn bằng lập luận chứ không bằng slide đẹp.

Lab đi qua **3 phase** (mỗi phase là một vòng [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) — mở rộng rồi thu hẹp, nhắc lại từ Day 2):

- **01-frame** — Frame: nghe đúng Big Ask → tách nhỏ → chọn Quick Win → đóng khung vấn đề (Problem Framing).
- **02-solution** — Solution: tìm lời giải đã có sẵn (deep research) → chốt Build/Buy/Boost/Partner + data & người review → bản vẽ trực quan.
- **03-pilot-plan** — Pilot Plan: cam kết hai chiều (xin–hứa–đo–dừng) + adoption + exit criteria → dồn thành 5-slide pitch.

Quy tắc cốt lõi: **demo đơn giản + lập luận chặt > demo đẹp + lập luận yếu.** Bản vẽ trực quan là bắt buộc; demo chạy được chỉ là điểm cộng. Không có nguồn = giả định, không xài như fact.

> Gặp thuật ngữ chưa quen (Quick Win, Problem Framing, Build/Buy/Boost, baseline, exit criteria, data flywheel...)? Xem `glossary.md`.

---

## Nộp bài thế nào? (đọc trước khi vào lab)

### Tên kho GitHub

Cú pháp: **`Day28-MãNhóm`** (vd: `Day28-G07`). Mỗi nhóm 3 người 1 kho công khai, nộp chung.

Kho mẫu của giảng viên: <https://github.com/VinUni-AI20k/Day28-Track01-AI-Pilot-Plan>

### Cần nộp gì?

Đưa toàn bộ thư mục `worksheet/` lên GitHub theo đúng cấu trúc dưới, rồi nộp link qua LMS.

```text
Day28-MãNhóm/                                  ← kho GitHub công khai (1 kho / nhóm 3)
│
├── README.md                                  ← Mã nhóm + 3 thành viên + link bản nộp
│
└── worksheet/
    │
    ├── 00-context.md                          📌 BẮT BUỘC — context nhóm + track (điền đầu buổi)
    ├── group-members.md                       📌 BẮT BUỘC — 3 thành viên + vai
    │
    ├── 01-frame/                              Phase 1 — Frame
    │   ├── 1-intake-breakdown.md              ← Trung gian: nghe đề + tách nhỏ
    │   ├── 2-quick-win.md                     ← Trung gian: chấm điểm chọn lát cắt
    │   └── 3-FINAL-problem-framing.md         🎯 Bản nộp phase Frame
    │
    ├── 02-solution/                           Phase 2 — Solution
    │   ├── 1-find-existing-solutions.md       ← Trung gian: deep research lời giải đã có
    │   └── 2-FINAL-solution.md                🎯 Bản nộp phase Solution (+ bản vẽ trực quan)
    │
    └── 03-pilot-plan/                         Phase 3 — Pilot Plan
        ├── 1-pilot-plan.md                    ← Trung gian: AI Pilot Plan core
        └── 2-FINAL-pitch.md                   🎯 Bản nộp cuối: 5-slide pitch + AI Support Log
```

🎯 = file người chấm xem trước. Các file `1-…` là **trung gian** — vẫn phải nộp kèm để người chấm thấy nhóm đi qua đủ các bước.

Bộ nộp = **A3 Working Canvas (7 mục, nằm rải trong các file trên) + 5-slide Pitch + AI Support Log**. (A3 Working Canvas 7 mục: Track & Big Ask · Tool Breakdown · Quick Win · Problem Framing · Solution Approach *(đã gồm Data & Expert)* · Demo/Mockup/Flow · AI Pilot Plan.)

### README đầu kho phải có gì?

```markdown
# Day 28 — Nhóm [MãNhóm]

## Thành viên
- [Họ tên 1] · [Họ tên 2] · [Họ tên 3]
- Track: [số/tên track được giao]

## Bản nộp
- 🎯 [Problem Framing](./worksheet/01-frame/3-FINAL-problem-framing.md)
- 🎯 [Solution + bản vẽ](./worksheet/02-solution/2-FINAL-solution.md)
- 🎯 [5-slide Pitch + AI Support Log](./worksheet/03-pilot-plan/2-FINAL-pitch.md)
```

### Các bước nộp

1. Nhóm tạo 1 kho GitHub công khai `Day28-MãNhóm`.
2. Đưa toàn bộ `worksheet/` lên đúng cấu trúc trên.
3. Tạo `README.md` gốc kho theo mẫu (3 thành viên + track + link 3 bản nộp).
4. Trong buổi: pitch 5 phút + nhận phản biện theo bảng 5 Gate.
5. Nộp link kho qua LMS Day 28 trước **23:59 hôm nay**.

---

## Quy trình làm bài (~70 phút, nhóm 3)

```text
Điền 00-context.md + group-members.md (5')
   -> Phase 1 — Frame (~35')
      -> 1-intake-breakdown : nghe đề + tách 5-8 use case
      -> 2-quick-win        : chấm điểm chọn 1 lát cắt   ⚑ Mốc 1 (15-20')
      -> 3-FINAL-problem-framing : đóng khung vấn đề     ⚑ Mốc 2 (35-40')
   -> Phase 2 — Solution (~15')
      -> 1-find-existing-solutions : deep research ai giải rồi
      -> 2-FINAL-solution   : chốt Build/Buy/Boost + bản vẽ ⚑ Mốc 3 (50-55')
   -> Phase 3 — Pilot Plan (~15')
      -> 1-pilot-plan       : xin-hứa-đo-dừng + adoption + exit ⚑ Mốc 4 (60-65')
      -> 2-FINAL-pitch      : dồn 5 slide + AI Support Log
   -> Pitch 5' + phản biện theo 5 Gate
```

Mỗi file `worksheet/` mở ra là thấy frontmatter (mục tiêu, thời gian, input, có phải bản nộp không) + "Quy trình X phút" — đọc đầu file là biết làm gì.

---

## Phase 1 — Frame (~35 phút)

Mục tiêu: từ một Big Ask mơ hồ → một Problem Framing có người, có số, có ràng buộc, được owner (giả định) xác nhận. Sai phase này thì mọi thứ sau vô nghĩa.

- `01-frame/1-intake-breakdown.md` — phát biểu lại Big Ask bằng lời nhóm; tách công cụ lớn thành 5–8 use case độc lập.
- `01-frame/2-quick-win.md` — chấm điểm 4 trục (Impact · Feasibility · Evidence nhanh · Risk), chốt 1 Quick Win + ai ủng hộ + cái KHÔNG chọn. ⚑ Coach hỏi Mốc 1: *"Vì sao không làm full tool?"*
- `01-frame/3-FINAL-problem-framing.md` 🎯 — 9 mục: Original Ask → Reframed → Workflow → Pain (bằng SỐ) → Affected people → Constraints → Quick Win → Open questions → Validation. ⚑ Coach hỏi Mốc 2: *"Ai đau? Baseline là gì?"*

## Phase 2 — Solution (~15 phút)

Mục tiêu: đừng xây lại từ số 0. Tìm ai đã giải bài này rồi, chốt cách làm có lý do, và cho stakeholder *nhìn thấy* flow.

- `02-solution/1-find-existing-solutions.md` — gọi tên dạng bài (pattern), deep research 4 tầng (map → tiền lệ → phản chứng → thu hẹp), rút về 2–3 hướng khả thi có nguồn.
- `02-solution/2-FINAL-solution.md` 🎯 — chốt Build/Buy/Boost/Partner (decision tree + ego check) + data & ai review + **1 bản vẽ trực quan bắt buộc** (mockup / user flow / prompt flow / agent flow / cặp input–output). ⚑ Coach hỏi Mốc 3: *"Bản vẽ đâu?"*

## Phase 3 — Pilot Plan (~15 phút)

Mục tiêu: viết cam kết hai chiều đủ để stakeholder quyết approve hay dừng, rồi dồn thành pitch.

- `03-pilot-plan/1-pilot-plan.md` — scope · người · data · budget (tách hạng mục) · timeline · metrics (baseline + ngưỡng) · exit criteria (≥2 mức, ai có quyền dừng) · adoption. ⚑ Coach hỏi Mốc 4: *"Xin gì? Hứa gì? Đo gì? Dừng khi nào?"*
- `03-pilot-plan/2-FINAL-pitch.md` 🎯 — 5 slide (slide cuối = lời xin rõ ràng) + chuẩn bị 3 câu phản biện + AI Support Log.

---

## Tài liệu trong thư mục này

| File / Thư mục | Dùng để làm gì |
|---|---|
| `worksheet/00-context.md` | Context nhóm + track — điền 1 lần đầu buổi, paste vào AI mỗi lần hỏi |
| `worksheet/01-frame/` | Phase 1 — 3 file (intake-breakdown, quick-win, FINAL-problem-framing) |
| `worksheet/02-solution/` | Phase 2 — 2 file (find-existing-solutions, FINAL-solution) |
| `worksheet/03-pilot-plan/` | Phase 3 — 2 file (pilot-plan, FINAL-pitch) |
| `worksheet/group-members.md` | 3 thành viên + vai |
| `prompts/` | 7 prompt critical-thinking — để **phản biện chính output AI**, không để AI làm hộ |
| `templates/` | Quick Win scoring · AI Pilot Plan core · demo examples · 5-slide pitch · bảng 5 Gate · track cards |
| `glossary.md` | Giải nghĩa thuật ngữ |

## Bảng dùng prompt tham khảo

| Prompt | Dùng khi | Lưu kết quả vào |
|---|---|---|
| `prompts/01-breakdown.md` | Tách công cụ lớn (Phase 1) | `01-frame/1-intake-breakdown.md` |
| `prompts/02-quick-win-challenge.md` | Phản biện lựa chọn Quick Win | `01-frame/2-quick-win.md` |
| `prompts/03-problem-framing-challenge.md` | Soi lỗ hổng Problem Framing | `01-frame/3-FINAL-problem-framing.md` |
| `prompts/04-find-solutions.md` | Deep research ai giải bài này rồi | `02-solution/1-find-existing-solutions.md` |
| `prompts/05-demo-challenge.md` | Ý tưởng bản vẽ trực quan thông minh | `02-solution/2-FINAL-solution.md` |
| `prompts/06-pilot-plan-challenge.md` | Thách thức từng mục Pilot Plan | `03-pilot-plan/1-pilot-plan.md` |

## Cách dùng prompt

1. Mở Claude / ChatGPT / Gemini tuỳ bước.
2. Paste `00-context.md` vào đầu chat trước.
3. Đưa thêm các file đã làm (vd `3-FINAL-problem-framing.md` khi sang Solution).
4. Chọn prompt phù hợp, chỉnh theo track của nhóm.
5. Đọc kỹ bản nháp AI → phản biện → sửa → lưu vào đúng file.

AI chỉ dựng nháp + đặt câu hỏi ngược. Nhóm tự kiểm nguồn, tự chốt nhận định, tự quyết Quick Win — AI không gặp stakeholder thay nhóm, không tự chấm điểm.

---

## Chấm điểm — bảng 5 Gate

Chấm theo **gate, không theo checklist dài**. Chi tiết: `templates/rubric-gate-sheet.md`.

| Gate | Đạt khi |
|---|---|
| **Gate 1 — Breakdown** | Tách công cụ lớn thành use case rời, không pitch cả platform |
| **Gate 2 — Quick Win** | Có chấm điểm/lý do (impact · feasibility · evidence · risk), không "nghe hay" |
| **Gate 3 — Problem Framing** | Rõ user · workflow · pain · baseline · constraint, không chung chung |
| **Gate 4 — Solution + visual** | Build/Buy/Boost/Partner có lý do + **có bản vẽ trực quan** (chỉ nói bằng chữ = trượt) |
| **Gate 5 — Pilot Plan** | Có scope · timeline · người · budget · metric · exit criteria · lời xin |

3 câu phản biện mặc định mỗi nhóm sẽ bị hỏi: *"Số/giả định lấy ở đâu?"* · *"Giả định chính sai thì sao?"* · *"Tình huống nào khiến bạn dừng pilot?"*

---

## Lỗi hay mắc

| Đừng làm | Nên làm |
|---|---|
| Pitch "build cả AI20k Learning OS" | Tách nhỏ, chọn 1 Quick Win, nói rõ KHÔNG làm gì |
| Chọn Quick Win vì "nghe hay / dễ demo" | Chấm 4 trục + nêu ai ủng hộ pilot |
| Problem chung chung "học viên cần học tốt hơn" | 1 nhóm người + 1 khoảnh khắc + pain có số |
| Mặc định "tự build" cho oai | Đi decision tree, kiểm ego, xét Boost/Buy trước |
| Chỉ nói bằng chữ ở phần Solution | Bắt buộc có 1 bản vẽ trực quan (Gate 4) |
| Pilot Plan thiếu exit criteria | ≥2 mức exit + ghi rõ ai có quyền dừng |
| Để AI tự chốt Quick Win / tự chấm | AI phản biện, nhóm tự quyết; ghi vào AI Support Log |
| Xài số AI đưa mà không có nguồn | Không nguồn = đánh dấu 🧮 giả định, không xài như fact |
| Chỉ nộp file FINAL | Giữ cả file trung gian `1-…` để thấy quá trình |
| Kho để private | Kho GitHub phải công khai, đúng cú pháp `Day28-MãNhóm` |

---

## Liên kết với Day 26 / Day 27

Day 28 dùng lại: phán đoán sản phẩm (Day 26) để chọn Quick Win đáng làm; kinh tế sản phẩm AI (Day 27 — cost, ROI, baseline) để dựng phần budget + metric trong AI Pilot Plan. Đường dẫn cuối: D26 phân tích sản phẩm → D27 economics → **D28 AI Pilot Plan** → 6 tuần thực chiến.

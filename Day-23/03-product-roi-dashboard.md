# 03 — Product ROI Dashboard v2

**Học viên:** Nông Nguyễn Thành — 2A202600250  
**Ngày:** Day 23 — VinUni AI 20k  
**Product:** BeeTutor Marketplace — AI Smart Matching & Learning Assistant

---

## Part A — Adoption Context

### A.1 Thách Thức Nhóm Chọn

| Trường | Trả lời |
|---|---|
| Thách thức áp dụng AI | Gia sư và học viên trên BeeTutor mất nhiều thời gian tìm nhau phù hợp. Học viên phải duyệt hàng chục profile, gia sư phải chờ booking被动. Tỷ lệ match thành công (booking → hoàn thành khóa) thấp ở giai đoạn đầu platform. |
| Tình huống xuất phát từ ai / ở đâu? | Product Manager + UX Research từ data onboard: 60% learner browse >5 tutor profiles nhưng không booking; 40% tutor nhận <1 booking/tháng đầu tiên. |
| Dấu hiệu bị kẹt | Browse-to-booking conversion rate <8%. Time-to-first-booking median 14 ngày. Churn sau trial 3 buổi ~25%. |
| Vì sao thách thức này đáng giải quyết? | Match thành công là core value proposition của BeeTutor. Nếu learner không tìm được tutor phù hợp nhanh, họ sẽ rời sang kênh truyền thống (giới thiệu, trung tâm gia sư). |

### A.2 Sản Phẩm / Công Cụ AI

| Trường | Trả lời |
|---|---|
| Tên sản phẩm / công cụ AI | BeeTutor AI Smart Matching — Gợi ý tutor phù hợp cho learner và ngược lại, dựa trên profile, preference, availability, price range, location, subject, và historical match quality. |
| Người dùng chính | Learners (học viên/phụ huynh) cần tìm tutor; Tutors (gia sư) cần tìm lớp phù hợp |
| Bối cảnh sử dụng | learner nhập nhu cầu học → AI gợi ý 3-5 tutor phù hợp nhất → learner xem profile, chat, booking. Tutor nhận notification về learner phù hợp → có thể accept hoặc suggest điều chỉnh. |
| Mục tiêu kinh doanh / học tập / vận hành | Tăng browse-to-booking conversion từ 8% → 15%. Giảm time-to-first-booking từ 14 → 5 ngày. Tăng session continuation rate sau 3 buổi từ 75% → 90%. |
| Không nằm trong phạm vi | AI tạo bài giảng, AI tạo quiz, AI chấm bài — những feature này thuộc Phase 3-4 của roadmap. |

### A.3 2-4 Quy Trình Chính

| # | Tên quy trình | Vai trò AI | Điểm người kiểm tra | Khi AI sai thì xử lý thế nào? |
|---|---|---|---|---|
| 1 | **Smart Match — learner tìm tutor** | AI scoring và ranking tutor dựa trên 12+ factors (subject, level, price, location, schedule, rating, tutor type, gender preference, learning goal, past match data) | Learner xem danh sách gợi ý, tự quyết định booking. Có filter manual để override. | Learner không tìm thấy tutor phù hợp trong top 5 → "Không phải kết quả tôi cần" button → AI hỏi thêm preference → re-rank. Data này dùng để tune weights. |
| 2 | **Booking flow — xác nhận và thanh toán** | AI gợi ý gói học phù hợp (1/2/3 tháng) dựa trên learning goal và budget. Auto-calculate price với discount. | Learner chọn gói, confirm thanh toán 50% deposit. Có thể chọn gói khác với gợi ý. | Learner từ chối tất cả gói → system lưu lý do → dashboard theo dõi rejection rate. Nếu >30% → review pricing logic. |
| 3 | **Post-match quality feedback** | AI tổng hợp feedback sau mỗi buổi học (tutor rating, session notes, progress) và gợi ý điều chỉnh (đổi tutor, đổi lịch, đổi thời lượng). | Learner và tutor đều confirm feedback. Nếu không đồng ý → dispute flow → admin review. | AI gợi ý đổi tutor nhưng learner không đồng ý → system tôn trọng lựa chọn, log reason. Nếu learner đổi tutor 3 lần trong 30 ngày → alert admin. |
| 4 | **Tutor recommendation — AI gợi ý learner cho tutor** | AI gợi ý learner phù hợp cho tutor dựa trên tutor's expertise, availability, price range, và historical success rate. | Tutor review danh sách learner gợi ý, có thể accept hoặc pass. | Tutor pass >70% gợi ý trong 2 tuần → alert → review matching criteria cho tutor đó. Tutor được option điều chỉnh preference. |

### A.4 Chẩn Đoán Nhanh ADKAR

| Stage | Câu hỏi | Nhận định |
|---|---|---|
| Awareness | Người dùng có biết AI matching giúp gì không? | Nhiều learner mới không biết platform có AI matching. Họ nghĩ phải tự search. |
| Desire | Người dùng có muốn dùng không? | Learner WANT tìm tutor nhanh, nhưng sợ AI gợi ý tutor kém chất lượng. Tutor LO sợ AI chỉ gợi ý learner có ngân sách thấp. |
| Knowledge | Người dùng có biết dùng đúng không? | Interface đơn giản nhưng learner không hiểu tại sao AI gợi ý người này chứ không phải người kia (explainability gap). |
| Ability | Người dùng có đủ access, thời gian, kỹ năng không? | Không rào cản kỹ năng. Nhưng learner cần nhập đủ preference để AI hoạt động tốt — đây là friction point. |
| Reinforcement | Có cơ chế khiến họ quay lại dùng không? | Chưa có. Sau khi booking, learner không thấy được "match score" hay "tại sao match này tốt". |

**Barrier chính:** **Desire + Knowledge** — Người dùng không TIN rằng AI matching tốt hơn tự search, và không HIỂU tại sao AI đưa ra kết quả đó.

```markdown
Giải pháp:
- Explainability: Hiển thị "Match Score: 92%" với breakdown (Subject match: 100%, 
  Schedule: 85%, Price: 90%, Location: 95%)
- Social proof: "87% learner hài lòng với tutor được AI gợi ý trong tháng qua"
- Trial safety: 3 buổi trial — hoàn 100% nếu không hài lòng → giảm risk perception
- Tutorial: Onboarding flow giải thích cách AI hoạt động trong 30 giây
```

### A.5 3 Tactic Áp Dụng

| Tactic | Nhắm vào barrier nào? | Áp dụng cho quy trình nào? | Người phụ trách | Khi nào hoàn thành? |
|---|---|---|---|---|
| **Specific AI memo + Onboarding explainer** | Awareness + Knowledge | Workflow 1 (Smart Match) | Product Manager | Sprint 1 (2 tuần) |
| **Match Score transparency + "Why this tutor?" tooltip** | Desire + Knowledge | Workflow 1, 4 | UX Designer + ML Engineer | Sprint 2 (2 tuần) |
| **Track team-specific impact: Publish match quality weekly** | Reinforcement | Workflow 3 (Post-match feedback) | Data Analyst | Sprint 3 (2 tuần) |

---

## Part B — ROI Dashboard

### B.1 Chỉ Số Toàn Sản Phẩm

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
|---|---|---:|---:|---|---|---|---|
| Activation | % learner hoàn thành AI matching flow đầu tiên (nhập preference → xem gợi ý → click vào 1+ profile) | 35% | 70% trong 60 ngày | App analytics (Mixpanel) | Product Manager | "Click profile ≠ booking. Có thể chỉ tò mò." | Thêm metric "click-to-booking conversion rate" để filter noise. |
| Retention / Value | % matched pair hoàn thành ≥8 buổi (2 tháng package) | 62% | 80% trong 90 ngày | Booking system + payment log | Growth Lead | "Hoàn thành 8 buổi chưa chắc quality tốt — có thể do inertia." | Ghép với "CSAT ≥4.0" — chỉ tính là success nếu cả completion VÀ CSAT đạt. |
| Trust / Quality | AI match acceptance rate (% booking từ AI-gợi ý / tổng booking) | 28% | 50% trong 90 ngày | Booking system | ML Engineer | "Acceptance rate cao có thể do UI ép — learner không thấy option search manual." | Đảm bảo search manual luôn visible. Đo "manual search satisfaction" song song. |

### B.2 Chỉ Số Theo Từng Quy Trình

#### Workflow 1 — Smart Match (Learner tìm Tutor)

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
|---|---|---:|---:|---|---|---|---|
| Activation | % learner hoàn thành matching flow đầu tiên | 35% | 70% | App analytics | PM | "Chỉ đo completion, không đo quality của kết quả" | Đã thêm Quality metric bên dưới. |
| Engagement | % learner dùng AI matching ≥2 lần trong 30 ngày | 20% | 45% | App analytics | Growth Lead | "Dùng lại có thể vì kết quả đầu tệ, phải thử lại." | Phân biệt: "retry trong cùng session" (negative) vs "return sau 7+ ngày" (positive). |
| Productivity | Median time từ mở app → booking tutor | 14 ngày | 5 ngày | Booking system | Ops Lead | "Nhanh hơn nhưng có thể book tutor không phù hợp → churn sau." | Ghép với "session continuation rate sau 3 buổi" — nhanh + bền mới là thành công. |
| Quality | Browse-to-booking conversion rate | 8% | 15% | App analytics + booking | ML Engineer | "Conversion cao có thể do discount, không phải AI tốt." | Tách cohort: AI-matched vs manual search. So sánh conversion rate giữa 2 nhóm. |
| Trust | CSAT sau 3 buổi đầu (trial period) cho AI-matched pair | Chưa đo | ≥4.2/5.0 | Post-session survey | CX Lead | "Self-report bias — learner ngại chấm điểm thấp." | Kết hợp với behavioral signal: "continuation after trial" — nếu continue thì trust thực. |
| Value | Revenue per matched learner (GMV từ AI-matched booking) | 1.8M VNĐ/tháng | 2.5M VNĐ/tháng | Payment system | Finance BP | "Revenue cao có thể do tutor giá cao, không phải AI good at matching." | Normalize theo price tier: đo revenue lift trong cùng price bracket. |

#### Workflow 2 — Booking Flow (Gợi ý Package & Thanh Toán)

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
|---|---|---:|---:|---|---|---|---|
| Activation | % learner xem AI-gợi ý package | 40% | 80% | App analytics | PM | "Xem ≠ tương tác. Có thể scroll qua." | Thêm "click vào package detail" làm activation threshold. |
| Engagement | % learner chọn package được AI gợi ý (vs self-select) | 25% | 45% | Booking system | Growth Lead | "Có thể learner chọn vì gói rẻ nhất, không phải vì AI suggest tốt." | Đo "package satisfaction" — % không đổi gói sau 2 tuần. |
| Productivity | Median time từ xem profile → hoàn thành booking | 3 ngày | 1 ngày | Booking system | Ops Lead | "Nhanh hơn có thể do learner không đọc kỹ terms → dispute sau." | Ghép với "dispute rate trong 14 ngày sau booking." |
| Quality | Package modification rate (% learner đổi gói sau booking) | 18% | ≤10% | Booking system | CX Lead | "Sửa gói không hẳn là xấu — có thể learner cần flexibility." | Phân loại: "upgrade" (positive) vs "downgrade" (negative signal). |
| Trust | Deposit completion rate (% learner thanh toán 50% deposit sau khi chọn gói) | 72% | 85% | Payment log | Finance BP | "Completion cao nhưng refund rate sau trial cũng cao thì vô nghĩa." | Ghép với "trial refund rate" — chỉ tính success nếu deposit完成 VÀ không refund. |
| Value | Average package value (AI-gợi ý vs manual) | 2.2M VNĐ | 2.8M VNĐ | Payment system | Finance BP | "Package value cao do upselling, không phải value thật." | Đo "package completion rate" — learner có finish package đã mua không. |

#### Workflow 3 — Post-Match Quality Feedback

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
|---|---|---:|---:|---|---|---|---|
| Activation | % session có feedback từ learner | 45% | 75% | Feedback system | CX Lead | "Feedback rate cao do popup ép, quality feedback thấp." | Đo "feedback quality score" — feedback có text ≥20 ký tự được tính cao hơn. |
| Engagement | % learner dùng AI suggestion (đổi tutor/adjust schedule) khi được gợi ý | 12% | 30% | App analytics | Product Manager | "Không dùng suggestion có thể vì họ hài lòng, không phải ignore AI." | Đo satisfaction của learner KHÔNG dùng suggestion — nếu CSAT ≥4.5 thì OK. |
| Productivity | Median time từ complaint → resolution | 48 giờ | 12 giờ | Support ticket system | Ops Lead | "Nhanh resolve nhưng resolution quality thấp thì vô ích." | Ghép với "resolution satisfaction score" post-resolution. |
| Quality | Tutor switch rate trong 30 ngày đầu | 22% | ≤12% | Booking system | ML Engineer | "Switch không hẳn AI sai — learner có thể đổi do schedule conflict." | Phân loại reason: "match quality" (AI fault) vs "schedule/personal" (not AI fault). |
| Trust | Repeat booking rate (% learner book lại cùng tutor sau khóa đầu) | 58% | 75% | Booking system | Growth Lead | "Repeat cao có thể do learner lười tìm tutor mới." | Ghép với CSAT — nếu repeat + CSAT ≥4.3 thì đúng là trust. |
| Value | Revenue retained from repeat bookings | 1.2M VNĐ/learner | 1.8M VNĐ/learner | Payment system | Finance BP | "Revenue retained không tách biệt AI impact." | A/B test: cohort AI-matched vs manual — compare retention revenue delta. |

#### Workflow 4 — Tutor Recommendation (AI gợi ý Learner cho Tutor)

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
|---|---|---:|---:|---|---|---|---|
| Activation | % tutor xem AI-gợi ý learner danh sách | 30% | 65% | App analytics (tutor side) | PM | "Xem nhưng không tương tác thì chưa adopt." | Thêm "click vào learner profile" làm activation threshold. |
| Engagement | % tutor accept hoặc counter-offer ≥1 learner gợi ý/tuần | 15% | 40% | Booking system | Growth Lead | "Accept rate thấp có thể do tutor đã đủ lớp, không phải AI tệ." | Đo "tutor capacity utilization" — chỉ tính cho tutor có available slot. |
| Productivity | Median time từ tutor onboard → nhận booking đầu tiên | 14 ngày | 7 ngày | Booking system | Ops Lead | "Nhanh hơn nhưng booking đó không completion thì vô nghĩa." | Ghép với "first-booking completion rate." |
| Quality | Tutor pass rate (% gợi ý bị tutor từ chối) | 68% | ≤40% | Booking system | ML Engineer | "Pass cao có thể do tutor kén chọn, không phải AI sai." | Survey tutor lý do pass — nếu "not a good fit" >50% → AI issue. |
| Trust | % tutor rating AI suggestion ≥4/5 | Chưa đo | ≥70% | Tutor survey | CX Lead | "Survey bias — tutor rating cao để được AI gợi ý nhiều hơn." | Kết hợp behavioral: "accept rate trend over time" — nếu tăng thì trust thực. |
| Value | Tutor revenue from AI-matched learners (vs manual) | 1.5M VNĐ/tutor/tháng | 2.2M VNĐ/tutor/tháng | Payment system | Finance BP | "Revenue cao do tutor giá cao, không phải AI." | Normalize: revenue per hour taught, so sánh trong cùng tutor tier. |

---

## Part C — Dashboard Mock

```text
┌──────────────────────────────────────┐ ┌──────────────────────────────────────┐
│ TILE 1: PRODUCT HEALTH               │ │ TILE 2: SMART MATCH WORKFLOW         │
│ Metric: AI match acceptance rate     │ │ Metric: Browse-to-booking conv.      │
│ Current: 28%    Target: 50%          │ │ Current: 8%     Target: 15%          │
│ Status: 🟡 AMBER                     │ │ Status: 🔴 RED                       │
│ Action if red: Review match weights, │ │ Action if red: A/B test new ranking  │
│ run learner preference survey        │ │ algorithm, simplify preference input │
└──────────────────────────────────────┘ └──────────────────────────────────────┘

┌──────────────────────────────────────┐ ┌──────────────────────────────────────┐
│ TILE 3: BOOKING FLOW                 │ │ TILE 4: TRUST / QUALITY              │
│ Metric: Deposit completion rate      │ │ Metric: CSAT after 3-buổi trial      │
│ Current: 72%    Target: 85%          │ │ Current: N/A    Target: ≥4.2/5.0     │
│ Status: 🟡 AMBER                     │ │ Status: ⚪ NOT MEASURED YET          │
│ Action if amber: Simplify payment    │ │ Action if white: IMPLEMENT survey    │
│ flow, add MoMo/VNPay auto-redirect   │ │ immediately — đây là metric quan     │
│                                      │ │ trọng nhất cho decision              │
└──────────────────────────────────────┘ └──────────────────────────────────────┘

┌──────────────────────────────────────┐ ┌──────────────────────────────────────┐
│ TILE 5: VALUE / RETENTION            │ │ TILE 6: DECISION                     │
│ Metric: Session continuation ≥8 buổi │ │ Continue / Pivot / Kill: PIVOT       │
│ Current: 62%    Target: 80%          │ │ Metric mạnh nhất: CSAT after trial   │
│ Status: 🔴 RED                       │ │ Before scale: Implement CSAT survey  │
│ Action if red: Analyze churn reason, │ │ + match score explainability. Focus  │
│ re-match learners who dropped out    │ │ on quality signals trước khi mở rộng │
└──────────────────────────────────────┘ └──────────────────────────────────────┘
```

---

## Part D — Decision Memo

```markdown
# Memo Quyết Định Cuối — BeeTutor AI Smart Matching

1. Nhóm khuyến nghị: **PIVOT** (đổi hướng có kiểm soát).

   Lý do: AI matching có tín hiệu activation (35% learner hoàn thành flow đầu tiên) 
   nhưng chất lượng chưa được đo đầy đủ. Continuation rate 62% dưới target 80%, và 
   quan trọng nhất — CSAT sau trial period CHƯA ĐƯỢC ĐO. Không có quality signal, 
   không thể confidently continue hoặc kill.

   Pivot plan:
   - Giữ AI matching cho simple cases (môn phổ thông, price range phổ biến)
   - Tạm dừng AI cho complex cases (ôn thi chuyên, học viên đặc biệt) cho tới khi 
     có đủ quality data
   - Ưu tiên số 1: Implement CSAT survey sau 3 buổi đầu
   - Ưu tiên số 2: Add match score explainability ("tại sao AI gợi ý tutor này")

2. Chỉ số mạnh nhất để bảo vệ quyết định là:
   **CSAT sau 3 buổi đầu (trial period) cho AI-matched pair** — hiện chưa đo (N/A).
   
   Vì sao đây là evidence quan trọng nhất:
   - 3 buổi đầu là trial period — learner đã đủ trải nghiệm để đánh giá quality
   - Nếu CSAT ≥4.2 → AI matching đang hoạt động tốt → continue
   - Nếu CSAT <3.5 → AI matching đang gợi ý tutor không phù hợp → pivot hoặc kill
   - Đây là leading indicator — nếu CSAT thấp, continuation rate sẽ tụt theo 
     (lagging indicator) và revenue sẽ giảm sau 1-2 tháng
   - Không có metric này, dashboard đang blind — giống Klarna case: biết AI xử lý 
     2/3 chat nhưng không biết khách hàng có hài lòng không

3. Chỉ số hoặc giả định nhóm đã sửa sau phản biện là:
   
   V1: Dùng "browse-to-booking conversion rate" làm metric chính cho quality.
   V2: Chuyển thành "CSAT sau 3 buổi đầu + session continuation rate ≥8 buổi."
   
   Vì sao V1 yếu: Conversion rate cao có thể do discount, UI dark pattern, hoặc 
   learner desperate — không chứng minh match quality. Một learner có thể book 
   tutor không phù hợp rồi churn sau 2 buổi.
   
   Vì sao V2 tốt hơn: CSAT + continuation đo actual experience, không chỉ 
   intention. Nếu learner hài lòng VÀ tiếp tục học → match thực sự tốt.
   Đây là paired metric: productivity (conversion) + quality (CSAT) + value (continuation).

4. Trước khi scale, nhóm phải:
   1. **Implement CSAT survey sau mỗi buổi học** (tối thiểu sau 3 buổi đầu)
      — Người phụ trách: CX Lead — Deadline: 2 tuần
   2. **Add match score explainability UI** (hiển thị tại sao AI gợi ý tutor này,
      với breakdown theo subject, schedule, price, location)
      — Người phụ trách: UX Designer + ML Engineer — Deadline: 3 tuần
   3. **Thiết lập decision rule threshold** cho continue/pivot/kill dựa trên CSAT:
      - CSAT ≥4.2 + continuation ≥85% → Continue, mở rộng sang complex cases
      - CSAT 3.5-4.2 → Pivot, refine matching weights
      - CSAT <3.5 → Kill AI matching cho tier đó, revert to manual search
      — Người phụ trách: Product Manager + Data Analyst — Deadline: 1 tuần
```

---

## Red-team và Sửa v2

### Nhóm bị phản biện — 3 Rủi Ro Được Nêu

| Rủi ro được nêu | Ai nêu? | Chỉ số / giả định liên quan | Sửa ở v2 |
|---|---|---|---|
| "Acceptance rate cao có thể do UI ép — learner không thấy option search manual" | CFO | AI match acceptance rate (28% → 50%) | Đảm bảo search manual luôn visible. Đo "manual search satisfaction" song song. |
| "Conversion rate cao có thể do discount, không phải AI matching tốt" | User | Browse-to-booking conversion rate (8% → 15%) | Tách cohort: AI-matched vs manual search. So sánh conversion rate giữa 2 nhóm. |
| "CSAT chưa đo — dashboard đang blind về quality" | Risk | Tất cả quality metrics | Thêm CSAT sau 3 buổi đầu làm metric ưu tiên số 1. Decision memo khuyến nghị PIVOT cho tới khi có data. |

### Ít Nhất 2 Thay Đổi Cụ Thể Từ v1 Sang v2

| # | V1 Có Vấn Đề Gì? | V2 Sửa Thành Gì? | Vì Sao Sửa Này Tốt Hơn? |
|---|---|---|---|
| 1 | V1 dùng "browse-to-booking conversion rate" làm proxy cho match quality | V2 thay bằng "CSAT sau 3 buổi đầu + session continuation rate" | Conversion chỉ đo intent, không đo actual experience. CSAT + continuation đo result thực tế. |
| 2 | V1 không có CSAT survey — tất cả quality metrics là "chưa đo" | V2 ưu tiên implement CSAT survey trong 2 tuần, làm metric quan trọng nhất cho decision | Không có quality signal thì dashboard chỉ là vanity metrics. CSAT là leading indicator cho retention và revenue. |
| 3 | V1 không phân biệt simple vs complex match cases | V2 tách metric theo độ phức tạp và khuyến nghị pivot — chỉ keep AI cho simple cases cho tới khi có đủ data | Giống bài học từ Klarna: AI có thể good ở simple cases nhưng fail ở complex cases. Tách riêng để không che lấp signal. |

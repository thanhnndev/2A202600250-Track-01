# Marketing Claims Audit — BeeTutor Marketplace

**Ngày rà soát:** 09/05/2026  
**Người rà soát:** Nông Nguyễn Thành

**Vật liệu (Workshop 7.1 — handbook):** “trang giới thiệu” tương đương **định vị + roadmap** trong [BEETUTOR-MARKETPLACE.md](../BEETUTOR-MARKETPLACE.md); **pin social** chưa có — dùng tagline README + khối KEY METRICS làm stand-in; **slide pitch** không có trong repo — không áp dụng.

**Nguồn:** tagline README, outline sản phẩm [BEETUTOR-MARKETPLACE.md](../BEETUTOR-MARKETPLACE.md), roadmap/metrics trong cùng file.

## Bảng claim audit

| # | Câu gốc | Vị trí | Mức | Evidence hiện có | Honest version | Action |
|---|---------|--------|-----|------------------|----------------|--------|
| 1 | "Nền tảng kết nối và hỗ trợ học tập **thông minh**" | README + định vị outline | B → C nếu hiểu là AI | Chưa có benchmark “thông minh”; MVP không có AI matching | "Nền tảng kết nối học viên–gia sư, quản lý lịch và thanh toán có escrow. Giai đoạn sau có AI matching/quiz (roadmap)." | Gỡ từ “thông minh” hoặc định nghĩa rõ scope MVP vs roadmap |
| 2 | "**Smart Match**" trong sơ đồ định vị | Outline — khối ASCII branding | C (MVP) | Phase 1 ghi rõ: "**NOT in MVP: ❌ AI matching**" | "**Matching theo bộ lọc** (môn, khu vực, giá, loại gia sư). Smart Match (AI) dự kiến Phase 2." | Sửa landing/branding Phase 1; tránh “Smart Match” nếu chưa có AI |
| 3 | "**AI matching (GPT-based)**" | Phase 2 roadmap | B | Chưa có bản ghi accuracy/latency/consent | "**Đang nghiên cứu** gợi ý gia sư bằng AI; chưa cam kết độ chính xác cho đến khi có đánh giá nội bộ + nhãn AI." | Chỉ nêu khi có pilot + SLA nội bộ |
| 4 | "AI Assistant: **Tạo bài tập tự động**" | Gói PREMIUM | B/C | Chưa có thử nghiệm độ đúng/chính sách review | "Gợi ý nội dung bài tập **do AI sinh**; gia sư **bắt buộc rà soát** trước khi gửi học viên." | Bắt buộc human-in-the-loop + disclaimer |
| 5 | "→ AI generate **10 câu trong 30s**" | Quiz Premium — ví dụ UI | C | Không có log latency trung bình/P95 | "AI có thể gợi ý bộ câu hỏi; thời gian và chất lượng **phụ thuộc tải hệ thống và prompt**, đang đo trong pilot." | Bỏ số giây cố định |
| 6 | "**Match success rate: >80%**" | KEY METRICS | C | Chưa có định nghĩa “success” + mẫu | "**Mục tiêu nội bộ** sau khi có đủ dữ liệu booking hoàn thành (định nghĩa: hoàn thành ≥80% buổi trong gói)." | Chỉ công bố sau khi có báo cáo cohort |
| 7 | "**Completion rate: >90%**" | KEY METRICS | C | Chưa có baseline | "Mục tiêu vận hành; sẽ công bố khi có ≥ N khóa kết thúc." | Chuyển vào internal OKR, không hero marketing |
| 8 | "**Avg rating: >4.5/5.0**" | KEY METRICS | B | Có thể đạt nếu có reviews thật + anti-gaming | "Điểm trung bình hiển thị **trên học viên đã hoàn thành buổi có xác minh check-in**." | Chống review ảo + min sample |
| 9 | "**AI vẫn block**: SĐT → `***`; Email → `***@***`" | Chat system | A/B | Cần log kiểm thử + policy lưu trữ | Giữ mô tả nhưng thêm: "**Không cam kết chặn 100% biến thể**; báo cáo abuse qua kênh X." | Pen-test định kỳ + taxonomy bypass |
| 10 | "**Photo verify**: … (**face match với profile**)" | Check-in offline | B/C | Face = biometric; cần consent PDPL + DPIA | "Ảnh check-in để xác minh có mặt tại địa điểm; **khớp khuôn mặt chỉ khi có đồng ý riêng và mục đích rõ ràng** (hoặc dùng reviewer thủ công)." | Rà soát consent + lawful basis |
| 11 | Premium "**Email marketing**" | Subscription PREMIUM | B | Cần opt-in PDPL + unsubscribe | "Gửi email giới thiệu **theo danh sách đã đăng ký nhận tin**, có hủy đăng ký." | Sync preference center |
| 12 | "**Verification:** Giáo viên: CMND + Giấy phép hành nghề; Sinh viên: Thẻ SV + Transcript" | Outline § tutor categories | **A** | Quy trình xác minh được mô tả cụ thể trong PRD; có thể chứng minh bằng checklist onboarding + lưu file | *(Giữ nguyên — đây là mô tả quy trình, không phải promise hiệu quả.)* | Vận hành đúng checklist + audit định kỳ |
| 13 | "Phase 1 MVP: **Payment (Stripe, MoMo, VNPay)**" + "**Check-in/out (GPS + photo offline, dual-confirm online)**" | Roadmap Phase 1 Core Features | **A** | Danh mục tính năng cố định trong outline (không claim KPI); có thể demo/review code khi build | *(Giữ như mô tả phạm vi sản phẩm MVP.)* | Không đội thành “đảm bảo an toàn tuyệt đối” nếu chưa có pen-test |

## Thống kê

- Tổng số claim: **13** (≥10 — rubric Excellent handbook §9)
- Mức A: **2** (#12–13: quy trình/scope trong PRD, chứng minh được bằng tài liệu + vận hành)
- Mức B: **5** (#3, #4 — ghi **B/C** nhưng xếp **B** khi có human-in-the-loop bắt buộc; #8; #9 — **A/B** xếp **B**; #11)
- Mức C: **6** (#1 — nếu đọc “thông minh” như năng lực AI; #2, #5, #6, #7; #10 — **B/C** xếp **C** do sinh trắc/chưa DPIA)

## TOP 3 priority sửa ngay

1. **Đồng bộ messaging MVP:** branding “Smart Match” vs roadmap “NOT in MVP — AI matching” — tránh pattern **Kera** (nói năng lực không khớp thực tế).
2. **Bỏ chỉ số thời gian cố định “30s”** cho AI generate — không có evidence.
3. **Face match + metric >80%/>90%** — hoặc có phương pháp đo & nhắc nhở pháp lý (giáo dục + sinh trắc), hoặc không đưa ra cam kết công khai.

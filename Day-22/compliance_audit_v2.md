# Compliance Audit v2 — BeeTutor Marketplace

**Ngày:** 09/05/2026  
**Người thực hiện:** Nông Nguyễn Thành  
**Phạm vi:** Outline sản phẩm & roadmap [BEETUTOR-MARKETPLACE.md](../BEETUTOR-MARKETPLACE.md), positioning README.

**Mục tiêu:** Liệt kê vi phạm tiềm năng kèm **Điều luật cụ thể**, **trích dẫn nguyên văn** từ tài liệu nội bộ, **pattern vụ VN** (Kera / Pips / CIC), và **hành động khắc phục**. Output tiếng Việt — có thể chuyển tiếp luật sư.

---

## Đối chiếu với Workshop 1–3

| Loại vi phạm | Workshop | Ghi chú đối chiếu |
|--------------|----------|-------------------|
| Marketing “Smart Match” vs MVP không có AI | WS1 | Claim audit #2 — mức C |
| Metric >80% không có định nghĩa | WS1 | Claim audit #6 |
| PDPL / chuyển biên giới AI | WS2 | CTIA = YES |
| Escrow & fraud monitoring | WS3 | TOP1 nhật ký giao dịch |
| Tầng rủi ro Luật AI | WS2 | Phân loại **Cao** (giáo dục) |

---

## Danh sách vi phạm / rủi ro tuân thủ

### VI PHẠM 1: Branding “Smart Match” trong khi MVP không có AI matching

- **Luật áp dụng:** BLHS (hình sự kinh doanh)  
- **Điều:** **Điều 198** — Lừa dối khách hàng (mức độ cụ thể phụ thuộc lợi nhuận bất chính & chứng cứ “biết rõ là không biết”)  
- **Bằng chứng trong sản phẩm:** Outline có khối branding `"Smart Match"` trong sơ đồ định vị; đồng thời Phase 1 ghi `"NOT in MVP: ❌ AI matching"`.  
- **Pattern khớp:** **Kera** — giới thiệu năng lực/tính năng không đồng nhất với thực tế sản phẩm.  
- **Hành động sửa (founder làm trong 1 tuần):** Đổi wording MVP → “Match theo bộ lọc”; chỉ dùng “Smart Match” khi có module AI + nhật ký kiểm thử; rà soát lại hero README nếu public.  
- **Deadline:** Trước **public beta landing**; ân hạn hình sự không áp cho marketing nhưng rủi danh tiếng/Điều 198 là ngay khi thu phí.

---

### VI PHẠM 2: Cam kết chỉ số vận hành “Match success rate >80%” khi chưa có định nghĩa & dữ liệu

- **Luật áp dụng:** BLHS  
- **Điều:** **Điều 198** Khoản 1–2 (nếu đưa vào quảng bá thương mại làm khách hàng tin và thanh toán)  
- **Bằng chứng trong sản phẩm:** `"Match success rate: >80%"` trong mục KEY METRICS — không kèm định nghĩa “success”, độ dài cohort, hay nguồn đo.  
- **Pattern khớp:** **Kera** — claim mang tính cam kết kết quả không có evidence độc lập.  
- **Hành động sửa (founder làm trong 1 tuần):** Gỡ chỉ số khỏi mọi tài liệu bán hàng đầu mối; chuyển sang OKR nội bộ; nếu công bố sau này — đính kèm methodology + sample size.  
- **Deadline:** Trước deck nhà đầu tư / ads có chỉ số này.

---

### VI PHẠM 3: Cam kết cụ thể “AI generate 10 câu trong 30s”

- **Luật áp dụng:** BLHS  
- **Điều:** **Điều 198**  
- **Bằng chứng trong sản phẩm:** `"→ AI generate 10 câu trong 30s"` trong phần AI Auto-generate Premium.  
- **Pattern khớp:** **Kera** — con số cụ thể dễ bị chứng minh sai lệch khi không có benchmark.  
- **Hành động sửa (founder làm trong 1 tuần):** Xóa SLA “30s” khỏi outline/deck; thay bằng “thời gian phụ thuộc hệ thống” hoặc chỉ công bố P50/P95 sau đo thực tế.  
- **Deadline:** Trước enable Premium AI quiz.

---

### VI PHẠM 4: Xử lý sinh trắc (ảnh selfie + “face match”) thiếu khung PDPL/DPIA rõ ràng trong tài liệu

- **Luật áp dụng:** Luật BVDLCN **91/2025/QH15** (PDPL)  
- **Điều:** **Điều 30** — kiểm soát bảo mật từ thiết kế, **kiểm toán được**, DPIA trong **60 ngày** kể từ khi bắt đầu xử lý (đặc biệt nhóm nhạy cảm/sinh trắc tùy phân loại dữ liệu)  
- **Bằng chứng trong sản phẩm:** `"Photo verify: Chụp ảnh tự sướng (face match với profile)"` trong Check-in offline.  
- **Pattern khớp:** **CIC** — thiếu kiểm soát & đánh giá tác động → rủi ro lớn khi rò rỉ/ghi nhận sai mục đích.  
- **Hành động sửa (founder làm trong 1 tuần):** Chốt có/không dùng face-match tự động; giao PM phạm vi DPIA draft; consent riêng trên UI mock; retention policy bản nháp.  
- **Deadline:** **60 ngày** sau ngày production xử lý ảnh sinh trắc.

---

### VI PHẠM 5: Chuyển dữ liệu học tập/DLCN ra nước ngoài qua vendor AI & Stripe chưa được mô tả CTIA trong tài liệu

- **Luật áp dụng:** PDPL  
- **Điều:** **Điều 30** (khoản chuyển giao/bảo đảm kiểm soát — đồng bộ với nghĩa vụ đánh giá chuyển giao xuyên biên giới trong hệ thống pháp lý hiện hành)  
- **Bằng chứng trong sản phẩm:** `"AI matching (GPT-based)"`, `"Payment (Stripe, MoMo, VNPay)"`, upload file/link học liệu — luồng dữ liệu có thể rời VN.  
- **Pattern khớp:** **CIC** — dữ liệu nhạy cảm khi hội tụ (định danh + tài chính + học tập).  
- **Hành động sửa (founder làm trong 1 tuần):** Lập bảng subprocessors (Stripe, cloud, LLM); yêu cầu DPA mẫu; checklist minimize PII gửi LLM (phiên bản 1).  
- **Deadline:** Trước bật GPT matching/quiz trên production.

---

### VI PHẠM 6: Chưa ghi nhận đầy đủ nghĩa vụ **phân loại tầng rủi ro** và nhãn AI theo Luật AI VN

- **Luật áp dụng:** Luật AI Việt Nam **134/2025/QH15**  
- **Điều:** **Điều 9** — phân loại hệ thống AI theo mức rủi ro + nghĩa vụ tương ứng (giáo dục / gen AI / nhãn hiển thị)  
- **Bằng chứng trong sản phẩm:** Roadmap Phase 2–4 có **chatbot/matching/quiz AI** phục vụ học tập; outline không có mục “phân loại tầng & kế hoạch thông báo Bộ KH&CN”.  
- **Pattern khớp:** **CIC** — hệ thống thu thập/xử lý dữ liệu và người dùng **quy mô lớn** mà **thiếu khung kiểm soát, minh bạch và báo cáo** đầy đủ với cơ quan có thẩm quyền (tinh thần các vụ **thiếu kiểm soát dữ liệu** tại Việt Nam; đối chiếu mục handbook Day 22 §5).  
- **Hành động sửa (founder, trong 1 tuần — khởi động):** (1) Hoàn thiện **đánh giá nội bộ tầng Cao** (giáo dục); (2) Draft nhãn “đầu ra AI” + human oversight quiz; (3) Ghi nhận ngày bắt đầu xử lý để tính DPIA/ân hạn.  
- **Deadline:** Hiệu lực **1/3/2026** đã qua — thực hiện **ngay** + ân hạn lĩnh vực giáo dục theo Luật AI VN (handbook §6.3).

---

### VI PHẠM 7: Thiếu quy trình AML-lite / giám sát abuse cho escrow & payout

- **Luật áp dụng:** BLHS  
- **Điều:** **Điều 324** — Rửa tiền (khi có **biết rõ** dấu hiệu phạm tội vẫn tiếp tục hỗ trợ giao dịch — analog startup không phải chứng minh đủ yếu tố trong memo này, nhưng **gap vận hành** là hiển hiển)  
- **Bằng chứng trong sản phẩm:** Mô hình escrow hai đợt, platform fee, refund — **không** có mô tả rule anomaly detection hay escalation trong outline.  
- **Pattern khớp:** **Mr Pips / Shark Bình** — tiếp tay luồng tiền khi có dấu hiệu.  
- **Hành động sửa (founder làm trong 1 tuần):** Tạo Sheet nhật ký + 4 rule flags (theo `document_trail.md`); owner review thứ Hai; draft policy freeze payout khi flag.  
- **Deadline:** Trước GMV **>50 triệu đồng/tháng** hoặc ngay khi bật payout tự động.

---

### VI PHẠM 8: Thu thập dữ liệu học viên vị thành niên (ví dụ profile “Tuổi: 16”) thiếu khung đồng ý phụ huynh trong tài liệu

- **Luật áp dụng:** PDPL + nguyên tắc bảo vệ trẻ em trong hệ thống giáo dục  
- **Điều:** PDPL **Điều 30** (thiết kế an toàn, DPIA; kết hợp các quy định về đồng ý và xử lý đặc thù nhóm trẻ em — cần luật sư cụ thể hóa điều khoản consent theo văn bản chính thức)  
- **Bằng chứng trong sản phẩm:** Profile học viên mẫu có `"Tuổi: 16 (Lớp 10)"`; không có policy phụ huynh trong outline.  
- **Pattern khớp:** **CIC** — dữ liệu nhóm nhạy cảm (trẻ vị thành niên) + **thiếu governance** đồng ý/bảo vệ (tinh thần các vụ thiếu kiểm soát / rò rỉ dữ liệu — handbook §5).  
- **Hành động sửa (founder làm trong 1 tuần):** Wireframe luồng phụ huynh đồng ý (dưới 18); policy hiển thị profile tối thiểu; consult luật sư 1 buổi để chốt điều khoản consent.  
- **Deadline:** Trước marketing học sinh THCS/THPT quy mô.

---

## TOP 5 nghiêm trọng nhất — mỗi mục 3 hành động cụ thể

### 1. VI PHẠM 1 — Smart Match vs MVP không AI

1. Thay toàn bộ UI/copy MVP: **“Lọc & ghép nhu cầu”**, không dùng “Smart Match” cho đến khi có spec AI.  
2. Xuất bản **comparison table** nội bộ MVP vs Roadmap trên website (Transparency).  
3. Founder **ký** checklist marketing (liên kết `document_trail.md` #5) trước launch.

### 2. VI PHẠM 4 — Face match / sinh trắc

1. Hoàn thành **DPIA** luồng ảnh check-in; phân loại dữ liệu và retention.  
2. Triển khai **consent riêng** và tùy chọn fallback không dùng face-match tự động (manual review).  
3. Pen-test nhà cung cấp/SDK nhận diện (nếu có) + logging truy cập.

### 3. VI PHẠM 5 — CTIA / vendor nước ngoài

1. Lập danh sách **subprocessors** (Stripe, cloud, LLM) và lưu contract.  
2. Viết **CTIA** cho từng luồng (matching, quiz gen); minimize field-level encryption/token cho PII.  
3. Bật **toggle region** EU/US chỉ sau khi đạt checklist `territorial_scope.md`.

### 4. VI PHẠM 7 — Giám sát giao dịch (pattern Pips)

1. Triển khai **rules** TXN-01…04 trong Sheet nhật ký tuần (xem `document_trail.md`).  
2. Quy định **freeze payout** 72h khi score risk > ngưỡng.  
3. Escalation template email **Compliance** + archive ticket ID.

### 5. VI PHẠM 6 — Luật AI Điều 9 (giáo dục + gen AI)

1. Ban hành **AI Governance memo**: nhãn đầu ra, human approval workflow quiz AI.  
2. Đăng ký/thông báo theo cổng AI quốc gia khi đủ điều kiện (medium/high).  
3. Training **CSKH + tutors** về hallucination và incident playbook Day 21.

---

## Thống kê

- **Tổng vi phạm / gap liệt kê:** **8** (≥7 yêu cầu Day 22 §7.4)  
- **Tối thiểu theo prompt AI Compliance Officer (handbook §8):** Marketing kiểu **Kera** ×**3** (VP1–3); PDPL **Điều 30** ×**2** (VP4–5); Luật AI VN **Điều 9** ×**1** (VP6); Vendor/thanh toán kiểu **Pips** ×**1** (VP7). VP8 bổ sung PDPL **Điều 30** (trẻ em).  
- **Mỗi vi phạm:** có Điều luật cụ thể, trích dẫn nguyên văn từ [BEETUTOR-MARKETPLACE.md](../BEETUTOR-MARKETPLACE.md) hoặc README, pattern **Kera / Pips / CIC**.  
- **TOP 5 nghiêm trọng nhất:** mỗi mục **3 hành động** (mục trên).

---

## Checklist đối chiếu rubric nộp bài (Handbook §7.4 & §9)

| Tiêu chí | Đáp ứng |
|----------|---------|
| ≥7 vi phạm | Có **8** |
| Đủ 4 nhóm (marketing Kera, PDPL §30, Luật AI §9, vendor Pips) | Có |
| Mỗi vi phạm có Điều luật cụ thể (không chung chung) | Có |
| Trích nguyên văn bằng chứng từ tài liệu dự án | Có |
| Mỗi vi phạm map pattern vụ VN (Kera / Pips / CIC) | Có |
| TOP 5 × 3 hành động sửa cụ thể | Có |
| Toàn bộ tiếng Việt, có thể gửi luật sư | Có |

---

*Tài liệu mang tính chất phân tích rủi ro cho founder; không thay thế tư vấn luật sư được đăng ký hành nghề.*

# Territorial Scope — BeeTutor Marketplace

**Date:** 09/05/2026  
**Người thực hiện / Founder:** Nông Nguyễn Thành

## Câu hỏi 1: User EU?

- Có user EU hiện tại: **0** (giả định giai đoạn MVP tập trung Việt Nam)
- Kế hoạch mở rộng EU 12 tháng: **NO** (roadmap có “International expansion — English tutors” ở Phase 4, chưa cam kết EU cụ thể trong 12 tháng)
- **Kết luận:** EU AI Act áp dụng đầy đủ = **NO** hiện tại; **theo dõi** nếu marketing quốc tế hoặc tutor/learners đăng ký EU → khi đó cần đại diện pháp lý EU + DPIA/GDPR.

## Câu hỏi 2: Dữ liệu Việt Nam?

### Loại dữ liệu cá nhân đang xử lý (theo thiết kế outline):

1. **Danh tính:** họ tên, tuổi/lớp, giới tính  
2. **Liên hệ:** SĐT, email (chat có mask nhưng vẫn có trong hệ thống sau booking)  
3. **Định vị:** địa chỉ học, GPS check-in offline  
4. **Tài chính:** giao dịch escrow, MoMo/VNPay/Stripe, lịch sử hoàn tiền  
5. **Hành vi:** chat trước booking, lịch học, đánh giá, click/booking  
6. **Sinh trắc học (tiềm ẩn):** ảnh selfie check-in + “face match với profile” nếu triển khai đúng như mô tả  
7. **Nội dung học tập:** file upload, link Drive/YouTube, quiz  

### Có chuyển ra nước ngoài?

- **CÓ**, khi:  
  - **Stripe** (thẻ quốc tế), cloud/hosting nếu region US/EU  
  - **AI GPT-based matching / quiz generator** (Phase 2–4): vendor LLM nước ngoài  
- → **CTIA** (Đánh giá tác động chuyển giao xuyên biên giới) **= YES** khi bật các luồng trên production.

### Kết luận

- **PDPL áp dụng = YES** (xử lý DLCN của người trong Việt Nam).  
- **CTIA = YES** khi có chuyển biên giới thực tế (thanh toán quốc tế + AI vendor nước ngoài).

## Câu hỏi 3: Tầng rủi ro Luật AI VN?

- **Phân loại:** **Cao** (ưu tiên đánh giá “giáo dục / định hướng học tập” và có AI sau này)

- **Lập luận:** BeeTutor **trực tiếp phục vụ hoạt động học**, ghép cặp gia sư–học viên theo mục tiêu điểm số, có quiz và **AI sinh nội dung** trong roadmap. Theo khung handbook Day 22 (Điều 9 Luật AI VN), lĩnh vực **giáo dục** và các hệ thống có thể ảnh hưởng đến quyết định/người dùng trẻ em → biện pháp **đánh giá phù hợp, đăng ký/thông báo cổng quốc gia khi đủ điều kiện, giám sát con người đối với đầu ra AI, logging**.

- **Nghĩa vụ tương ứng (định hướng):** nhãn “đầu ra AI”, human review trước khi gửi học viên, chính sách an toàn trẻ em/phụ huynh, báo cáo sự cố/hallucination, lưu vết phê duyệt nội dung AI.

## 4 deadlines đã note vào Notion / lịch cá nhân

*(Workshop 7.2 bước 4 — handbook §7.2)*

- [x] **1/1/2026** — PDPL hiệu lực (đã qua) — rà soát Privacy Policy, consent, DSR  
- [x] **1/3/2026** — Luật AI VN hiệu lực (đã qua) — phân loại tầng + thông báo KH&CN khi medium/high  
- [ ] **2/8/2026** — EU AI Act high-risk full — chỉ kích hoạt checklist nếu có thị trường EU  
- [ ] **1/3/2027** — Hết ân hạn (startup — đối chiếu lại lĩnh vực giáo dục / ân hạn Luật AI handbook §6.3)  

Chi tiết lịch xem [`compliance_calendar.xlsx`](./compliance_calendar.xlsx).

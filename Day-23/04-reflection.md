# 04 — Reflection Cá Nhân

**Học viên:** Nông Nguyễn Thành — 2A202600250  
**Ngày:** Day 23 — VinUni AI 20k

---

## 150-200 từ: 1 metric hoặc 1 giả định sẽ sửa

Metric tôi sẽ sửa ngay sau buổi học này là **"browse-to-booking conversion rate"** — chỉ số tôi ban đầu dùng làm proxy cho chất lượng AI matching.

Giả định sai lầm của tôi là: nếu learner booking nhanh hơn sau khi xem AI gợi ý, tức là match tốt. Nhưng conversion rate chỉ đo intent tại một thời điểm, không đo experience thực tế sau đó. Một learner có thể book tutor vì UI đẹp, vì discount hấp dẫn, hoặc vì desperate — rồi churn sau 2 buổi vì tutor không phù hợp.

Bài học từ Klarna case — AI xử lý 2/3 chat nhưng đến năm 2025 phải bổ sung lại human element — cho thấy vanity metric có thể che lấp vấn đề quality nghiêm trọng.

Tôi sẽ thay thế bằng **CSAT sau 3 buổi đầu (trial period)** kết hợp với **session continuation rate ≥8 buổi**. Đây là paired metric: CSAT đo perception, continuation đo behavior. Nếu cả hai đều positive → match thực sự tốt. Nếu CSAT thấp nhưng continuation cao → có thể learner bị lock-in (đã trả deposit, ngại đổi) — cũng là signal quan trọng.

Thay đổi này khiến dashboard chậm hơn về data (phải đợi 3 buổi), nhưng trung thực hơn nhiều.

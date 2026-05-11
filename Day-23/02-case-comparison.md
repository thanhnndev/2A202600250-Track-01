# 02 — Case Comparison (Nhóm → Cá nhân)

**Học viên:** Nông Nguyễn Thành — 2A202600250  
**Ngày:** Day 23 — VinUni AI 20k  
**Product:** BeeTutor Marketplace — AI Smart Matching & Learning Assistant

---

## So sánh Case thành công / Case cảnh báo

| Trường | Case thành công: Morgan Stanley | Case cảnh báo: Klarna |
|---|---|---|
| Case | AI Assistant for Wealth Management Advisors | AI Customer Support Assistant |
| Workflow có AI | Truy cập tri thức nội bộ, tóm tắt research, gợi ý tài liệu cho advisors | Phân loại chat, trả lời FAQ, tóm tắt case, escalate case phức tạp |
| Metric chính | Adoption rate, query accuracy, time-to-information, compliance pass rate | ~2/3 chat AI xử lý, resolution time 11min→<2min, ~700 FTE equivalent |
| Metric đó chứng minh được gì? | AI có thể adopt trong môi trường regulated khi trust architecture vững | AI xử lý được volume lớn, nhanh hơn, tiết kiệm chi phí đáng kể |
| Metric đó chưa chứng minh được gì? | Client outcomes cuối cùng (retention, AUM, NPS) chưa được đo đầy đủ | Quality cho case phức tạp, CSAT by complexity, repeat inquiry, complaint rate |
| Thiếu metric nào? | Revenue per advisor, error rate trong advice, client retention | CSAT theo tier complexity, repeat inquiry 7-day, human handoff success |
| Bài học cho dashboard nhóm | Trust architecture phải có TRƯỚC scale. Eval + expert feedback + compliance là điều kiện cần | Productivity phải LUÔN đi kèm Quality. Tách metric theo độ phức tạp. Có cảnh báo khi quality tụt |

---

## Bài học nhóm sẽ áp dụng vào dashboard

```markdown
Từ Morgan Stanley:
1. Trust architecture phải là foundation, không phải add-on sau. Với BeeTutor, điều này nghĩa là:
   - AI matching phải có accuracy measurement trước khi mở rộng
   - Tutor phải có cơ chế override/feedback khi match không phù hợp
   - Compliance kiểm tra output AI (đặc biệt với học viên dưới 18 tuổi)

2. Expert feedback loop: Tutor và learner phải có cách report match quality
   sau mỗi buổi học → data này dùng để refine matching algorithm.

Từ Klarna:
3. KHÔNG chỉ đo "số lần AI được dùng" hoặc "số match thành công". Phải đo:
   - Booking completion rate sau AI match (productivity)
   - Session continuation rate sau 3 buổi đầu (quality)
   - Learner satisfaction sau 1 tháng (trust)
   - Revenue retained per matched pair (value)

4. Tách metric theo độ phức tạp:
   - Simple match: môn phổ thông (Toán, Lý, Hóa lớp 10-12)
   - Medium match: môn chuyên, ôn thi đại học, IELTS
   - Complex match: học viên đặc biệt (cần gia sư có chuyên môn tâm lý, 
     học viên khuyết tật, chương trình quốc tế)
   
5. Cảnh báo red flag: Nếu repeat inquiry (học viên đổi tutor liên tục) 
   >15% trong 30 ngày → trigger review và có thể pivot matching criteria.

6. Quy tắc decision rõ ràng:
   - Continue: Match accuracy ≥80%, continuation rate ≥85%, CSAT ≥4.2
   - Pivot: Activation cao nhưng continuation thấp → cải thiện matching criteria
   - Kill: CSAT complex case <3.5 hoặc complaint rate >10% → dừng AI cho tier đó
```

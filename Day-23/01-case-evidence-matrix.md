# 01 — Case Evidence Matrix (Cá nhân)

**Học viên:** Nông Nguyễn Thành — 2A202600250  
**Ngày:** Day 23 — VinUni AI 20k

---

## A. Case Evidence Matrix — Morgan Stanley (Case thành công)

| Trường | Trả lời |
|---|---|
| Case | Morgan Stanley — AI Assistant for Wealth Management Advisors |
| AI được dùng trong workflow nào? | Truy cập tri thức nội bộ, tóm tắt research, gợi ý tài liệu cho advisors khi tư vấn khách hàng |
| Người dùng chính là ai? | Wealth management advisors (môi trường rủi ro cao, regulated industry) |
| Họ đo metric gì? | Adoption rate, query accuracy, time-to-information, advisor satisfaction, compliance pass rate |
| Metric đó thuộc layer nào? | Activation (adoption), Productivity (time-to-information), Quality (accuracy, compliance pass), Trust (advisor satisfaction) |
| Metric đó chứng minh được gì? | AI có thể được adopt thành công trong môi trường regulated khi trust architecture được xây trước khi scale |
| Metric đó chưa chứng minh được gì? | Tác động cuối cùng lên client outcomes (retention, AUM growth, NPS) chưa được công bố đầy đủ |
| Thiếu metric nào? | Client retention rate, revenue per advisor, error rate trong advice, escalation rate khi AI không chắc chắn |
| Rủi ro lớn nhất | Nếu accuracy giảm khi scale sang advisor mới hoặc query phức tạp hơn, trust có thể sụp đổ nhanh |
| Bài học cho dashboard nhóm | Trust architecture (eval + expert feedback + compliance) phải có TRƯỚC khi scale. Không đo adoption mà không đo accuracy và compliance |

---

## B. Case Evidence Matrix — Klarna (Case cảnh báo)

| Trường | Trả lời |
|---|---|
| Case | Klarna — AI Customer Support Assistant |
| AI được dùng trong workflow nào? | Xử lý chat hỗ trợ khách hàng: phân loại intent, trả lời FAQ, tóm tắt case, escalate case phức tạp |
| Người dùng chính là ai? | Khách hàng cần hỗ trợ + support agents |
| Họ đo metric gì? | ~2.3M cuộc trò chuyện AI xử lý (~2/3 total chat), resolution time giảm từ 11 phút → dưới 2 phút, tương đương ~700 FTE |
| Metric đó thuộc layer nào? | Activation (coverage ~2/3), Productivity (resolution time <2min), Value (FTE-equivalent savings) |
| Metric đó chứng minh được gì? | AI có thể xử lý volume lớn, nhanh hơn đáng kể, tiết kiệm chi phí vận hành |
| Metric đó chưa chứng minh được gì? | Chất lượng xử lý case phức tạp, CSAT theo độ phức tạp, complaint rate, repeat inquiry rate, escalation success rate |
| Thiếu metric nào? | CSAT by case complexity, repeat inquiry rate trong 7 ngày, complaint rate, human handoff success rate |
| Rủi ro lớn nhất | Khi mở rộng sang case phức tạp, quality tụt → customer dissatisfaction → phải bổ sung lại human element (như Reuters 2025 đưa tin) |
| Bài học cho dashboard nhóm | Productivity metric LUÔN phải đi kèm Quality và Trust. Containment rate cao chưa đủ — phải đo CSAT theo tier complexity và repeat inquiry |

---

## Câu chốt

```markdown
Case thành công (Morgan Stanley) dạy nhóm tôi rằng:
→ Trust architecture (eval + expert feedback + compliance controls) phải được xây trước khi scale. 
  Trong môi trường rủi ro cao, người dùng chỉ adopt AI khi họ tin output đủ an toàn.

Case cảnh báo (Klarna) dạy nhóm tôi rằng:
→ Volume và speed là tín hiệu tốt nhưng chưa đủ. Khi AI xử lý case phức tạp, quality phải được đo 
  riêng theo độ phức tạp. Nếu không, CSAT tụt và phải rollback.

Vì vậy dashboard nhóm tôi phải:
→ Tách metric theo độ phức tạp của task (simple/medium/complex)
→ Ghép mỗi productivity metric với quality metric tương ứng
→ Có cảnh báo khi repeat inquiry hoặc complaint rate vượt ngưỡng
→ Có quy tắc kill/pivot rõ ràng dựa trên trust signal
```

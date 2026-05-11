# Mẫu 05 — Phản Biện Vai (Red-Team)

Mục tiêu: giúp nhóm khác tìm điểm yếu trong dashboard và roadmap trước khi nộp bản v2.

## Vai Phản Biện

| Vai | Câu hỏi chính |
|---|---|
| CFO | Chỉ số này chứng minh tiền, chi phí, ROI hoặc giá trị thật ở đâu? |
| Người dùng | Giải pháp này có làm việc của tôi dễ hơn không, hay chỉ ép tôi dùng AI? |
| Rủi ro | AI sai thì ai chịu trách nhiệm? Có audit, quality check, escalation không? |
| Chủ quy trình | Data lấy từ đâu? Ai pull report? Ai xử lý khi chỉ số đỏ? |

## Worksheet Cho Nhóm Đi Phản Biện

| Trường | Trả lời |
|---|---|
| Nhóm mình | |
| Vai được giao | CFO / Người dùng / Rủi ro / Chủ quy trình |
| Nhóm bị phản biện | |
| Sản phẩm của nhóm đó | |

### 3 Câu Hỏi / Rủi Ro Nhóm Mình Nêu

| # | Chỉ số / giả định bị chất vấn | Câu hỏi phản biện | Rủi ro nhóm kia cần ghi vào v2 |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

## Gợi Ý Theo Vai

### CFO

- Active users / prompt count chứng minh value ở đâu?
- Cost saved hoặc revenue lift tính bằng gì?
- Nếu Value không tăng sau 8 tuần thì tiếp tục hay dừng?

### Người dùng

- Chỉ số này có tạo áp lực dùng AI sai cách không?
- Workflow mới có thêm bước review/edit/report làm mất thời gian không?
- Nếu tôi không tin output, dashboard có thấy được không?

### Rủi ro

- AI sai thì có log để truy lại không?
- Có đo error rate, rework rate, escalation rate không?
- Dữ liệu có PII / privacy / compliance issue không?

### Chủ quy trình

- Nguồn dữ liệu cụ thể là gì?
- Ai pull report hằng tuần?
- Khi chỉ số đỏ, ai làm gì trong bao lâu?

## Nhóm Bị Phản Biện Ghi Lại

| Rủi ro được nêu | Ai nêu? | Chỉ số / giả định liên quan | Sửa ở v2 |
|---|---|---|---|
| | | | |
| | | | |
| | | | |

## Tự kiểm tra

- [ ] Câu hỏi nhắm vào chỉ số hoặc giả định cụ thể.
- [ ] Câu hỏi đúng vai được giao.
- [ ] Có ít nhất 1 rủi ro về chỉ số.
- [ ] Có ít nhất 1 rủi ro về triển khai / người phụ trách / dữ liệu.
- [ ] Nhóm bị phản biện có ghi được rủi ro và phần sửa v2.

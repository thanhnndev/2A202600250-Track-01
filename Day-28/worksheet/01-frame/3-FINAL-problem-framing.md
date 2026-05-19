---
artifact: 4 — Problem Framing (bản nộp phase Frame)
bai-tap: Frame — đóng khung vấn đề thật
phase: Double Diamond vòng 1 · ◆ output
input: 2-quick-win.md · BEETUTOR-MARKETPLACE.md
nop-cuoi: Có
---

# 3 — FINAL: Problem Framing

## 9 mục Problem Framing

1. **Original Ask**: "Từ outline BEETUTOR Marketplace, xây một AI Pilot Plan cho công cụ AI giúp kết nối học viên với gia sư phù hợp, nhưng không build toàn bộ marketplace cùng lúc."

2. **Reframed problem**: Phụ huynh/học viên cần tìm gia sư Toán THPT phải xử lý quá nhiều biến trước booking (môn/lớp, mục tiêu, lịch, khu vực, hình thức, ngân sách, loại gia sư, verification, rating). Ops cũng phải lọc thủ công nhiều hồ sơ để tạo shortlist, nên thời gian tư vấn dài và lý do đề xuất không nhất quán.

3. **Current workflow**: Phụ huynh gửi nhu cầu qua form/chat. Ops đọc nhu cầu, hỏi thêm nếu thiếu thông tin, lọc danh sách gia sư theo môn/khu vực/lịch/giá, đọc từng hồ sơ, chọn 2-5 người phù hợp, rồi viết tin nhắn giải thích cho phụ huynh. Nếu phụ huynh không đồng ý, ops lặp lại bước lọc.

4. **Pain evidence — bằng SỐ**:

```text
Giả định pilot để đo baseline (chưa có số thật):
- 50 yêu cầu tìm gia sư Toán THPT/tháng trong giai đoạn đầu.
- Ops mất trung bình 20 phút để đọc nhu cầu, lọc hồ sơ và viết shortlist 3 gia sư cho 1 yêu cầu.
- Tổng thời gian: 50 x 20 phút = 1.000 phút = 16,7 giờ/tháng chỉ cho shortlist Toán THPT.
- 30% yêu cầu bị hỏi lại ít nhất 1 lần vì thiếu lịch/ngân sách/khu vực, làm chậm phản hồi 0,5-1 ngày.
- Nếu shortlist không có lý do rõ, phụ huynh khó tin và có thể yêu cầu thêm lựa chọn, tăng vòng tư vấn.
Nguồn: số giả định cho lab, cần thay bằng log tư vấn/CRM thật trong tuần 0 của pilot.
```

5. **Affected people**: Người dùng chính là phụ huynh/học viên lớp 10-12 cần gia sư Toán tại TP.HCM. Người review là ops/CS BEETUTOR. Người quyết approve/dừng pilot là product owner/ops lead. Gia sư bị ảnh hưởng vì hồ sơ của họ được đưa vào hoặc loại khỏi shortlist.

6. **Constraints**: Privacy với hồ sơ học viên và giấy tờ gia sư; AI không được bịa chứng chỉ/rating/lịch; output shortlist phải có nguồn từ hồ sơ; gia sư liên quan học sinh vị thành niên nên ops phải review trước khi gửi; budget nhỏ, dùng data mẫu và model/API sẵn; pilot chỉ là hỗ trợ matching, không tự xác nhận booking.

7. **Quick Win đã chọn**: AI tạo top 3 shortlist gia sư Toán THPT cho một yêu cầu học viên/phụ huynh, kèm lý do phù hợp và flag dữ liệu thiếu/rủi ro để ops review.

8. **Open questions**:

- Baseline thật về thời gian ops tạo shortlist là bao nhiêu phút/yêu cầu?
- Có bao nhiêu hồ sơ gia sư đủ dữ liệu bắt buộc: môn/lớp, giá, lịch, khu vực, hình thức học, verification?
- Phụ huynh coi yếu tố nào là bắt buộc: giới tính, loại gia sư, khoảng cách, rating, ngân sách, hay lịch?
- Ngưỡng "vượt ngân sách" chấp nhận được là bao nhiêu: 0%, 10%, hay 20%?
- Khi AI không tìm đủ 3 gia sư phù hợp, ops muốn nhận thông báo như thế nào?

9. **Validation**:

```text
Owner giả định xác nhận: Có, đây là vấn đề đáng giải trước vì nó nằm ngay trước booking và ảnh hưởng trực tiếp đến conversion. Tuy nhiên owner yêu cầu pilot phải đo baseline thật ở tuần 0, không dùng số giả định làm evidence cuối. Owner cũng yêu cầu mọi shortlist do AI tạo đều có ops review và hiển thị lý do + nguồn từ hồ sơ.
```

## Tự phản biện

- Khung này tránh câu chung chung "matching tốt hơn" bằng cách tập trung vào một workflow: tạo shortlist 3 gia sư Toán THPT trước booking.
- Nếu bị hỏi "số lấy ở đâu", câu trả lời là: số hiện tại là giả định lab để tính quy mô pain; pilot tuần 0 phải lấy số thật từ log tư vấn/CRM trong 1 tuần.
- Nếu giả định chính sai (ops không mất 20 phút mà chỉ mất 5 phút), pilot vẫn có thể đo giá trị ở conversion/consistency; nếu cả thời gian và conversion đều không cải thiện thì dừng.

## Tổng kiểm tra trước khi sang `02-solution/`

| Hạng mục | Xong? |
|---|---|
| Chỉ rõ 1 nhóm người + 1 khoảnh khắc cụ thể | Xong |
| Pain có số và nói rõ số từ đâu | Xong |
| Có baseline hoặc cách đo baseline + chỉ số có ngưỡng | Xong |
| Owner giả định xác nhận đúng vấn đề | Xong |

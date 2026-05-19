---
artifact: 7 — AI Pilot Plan core
bai-tap: Pilot Plan — cam kết hai chiều: xin – hứa – đo – dừng
phase: Double Diamond vòng 2 · ◇ giãn → ◆ siết
input: 02-solution/2-FINAL-solution.md · 00-context.md
nop-cuoi: Không — file trung gian
---

# 1 — AI Pilot Plan core

## 10 mục core

1. **Tóm vấn đề**: Ops BEETUTOR mất nhiều thời gian và thiếu nhất quán khi tạo shortlist gia sư Toán THPT cho phụ huynh vì phải lọc nhiều biến trước booking.

2. **Cách làm + lý do**: Boost workflow hiện tại bằng hard filter + weighted score + LLM explanation có nguồn + ops review, vì pilot cần nhanh, rẻ, kiểm soát rủi ro và chưa đủ dữ liệu để build recommender riêng.

3. **Scope pilot**: Pilot 6 tuần cho 50 yêu cầu tìm gia sư Toán lớp 10-12 tại TP.HCM; dùng 30-100 hồ sơ gia sư đã verify sơ bộ; chỉ tạo shortlist 3 gia sư trước booking, không xử lý thanh toán, hợp đồng, điểm học tập dài hạn.

4. **Người**: Người làm pilot: product/ops cá nhân + 1 ops lead review. Người review output rủi ro cao: ops lead duyệt 100% shortlist trong 2 tuần đầu. Người có quyền approve/dừng: BEETUTOR product owner hoặc ops lead.

5. **Data**: Dùng hồ sơ gia sư (môn, lớp, giá, lịch, khu vực, hình thức, verification, rating), intake học viên/phụ huynh (môn, lớp, mục tiêu, lịch, ngân sách, khu vực), log ops review và kết quả đặt học thử. Privacy: dùng data tối thiểu, ẩn giấy tờ nhạy cảm khỏi prompt, lưu audit log, citation từ field hồ sơ, thiếu nguồn thì nói chưa đủ dữ liệu.

6. **Budget**:

- API/tool: 20-50 USD/tháng cho LLM usage; 0-30 USD/tháng cho form/database nhẹ.
- Thời gian người: 2-3 giờ/tuần ops review; 1-2 giờ/tuần product chỉnh rule và xem metric.
- Hạng mục ẩn: 2 giờ training ops đầu pilot; 1 giờ/tuần maintenance prompt/rule; 1 giờ/tuần audit lỗi và bias.

7. **Timeline + cổng giữa phase**:

- Tuần 0: đo baseline thật từ 10-20 yêu cầu gần nhất; chuẩn hóa 30+ hồ sơ gia sư; chốt hard filters và trọng số. Cổng: đủ >=30 hồ sơ và >=10 baseline samples.
- Tuần 1-2: chạy shadow mode, AI tạo shortlist nhưng ops không gửi nếu chưa duyệt; đo lỗi hard filter và chất lượng lý do. Cổng: >=90% shortlist không sai hard filter.
- Tuần 3-4: gửi shortlist AI-assisted cho một nhóm nhỏ phụ huynh; đo thời gian ops và tỷ lệ đặt học thử. Cổng: giảm >=30% thời gian shortlist so với baseline.
- Tuần 5-6: mở rộng lên toàn bộ yêu cầu Toán THPT trong pilot; quyết định continue/iterate/stop.

8. **Metrics**:

| Metric | Đo bằng gì · ai đo | Baseline | Ngưỡng đạt |
|---|---|---|---|
| Thời gian tạo shortlist | Timestamp từ lúc intake đủ thông tin đến lúc ops approve; ops/product đo | Giả định 20 phút/yêu cầu, đo thật tuần 0 | Giảm >=30% sau tuần 4 |
| Lỗi hard filter | Audit 100% shortlist: sai môn/lịch/khu vực/ngân sách/verification | 0 là mục tiêu vì hard filter bắt buộc | <=5% shortlist có lỗi, lỗi nghiêm trọng = 0 |
| Tỷ lệ phụ huynh đặt học thử | Số shortlist dẫn đến booking thử / số shortlist gửi | Baseline đo tuần 0 | Tăng >=10 điểm % hoặc không giảm trong khi thời gian ops giảm |
| Trust của ops | Ops chấm 1-5: có dùng được không, lý do có kiểm được không | Chưa có, đo tuần 1 | Trung bình >=4/5 trong tuần 4 |

Leading indicator: trong 1-2 tuần đầu, >=90% shortlist shadow mode không sai hard filter và ops sửa dưới 30% lý do.

9. **Exit criteria**:

| Mức | Điều kiện | Hành động | Ai có quyền dừng |
|---|---|---|---|
| Cảnh báo | Lỗi hard filter 5-10%, ops trust <4/5, hoặc thiếu nguồn trong >10% lý do | Tạm giới hạn pilot, sửa rule/prompt, tăng review 100% | Ops lead |
| Nghiêm trọng | AI bịa chứng chỉ/rating/lịch; đề xuất gia sư không verify cho học viên vị thành niên; lỗi hard filter >10%; phụ huynh khiếu nại về đề xuất sai | Dừng gửi shortlist AI-assisted, quay về thủ công, audit toàn bộ log | Product owner/ops lead |

Exit criteria chặn 2 Red Flag: matching sai mất niềm tin và AI bịa thông tin hồ sơ.

10. **Adoption**: Người dùng đầu tiên là ops/CS, không phải toàn bộ marketplace. Workflow đổi ở bước tạo shortlist: ops bấm tạo shortlist, review/edit/approve, rồi gửi phụ huynh. Training: 1 buổi 60 phút cho ops về cách đọc score, nguồn, flag thiếu dữ liệu. Nếu ops không dùng sau 2 tuần hoặc sửa quá nhiều, quay về intake validation-only thay vì tiếp tục shortlist.

## Tự phản biện

- Budget đã tách tool/API, thời gian người, training và maintenance; chưa tính chi phí pháp lý nếu mở rộng verification thật.
- Exit criteria có người dừng rõ ràng: ops lead/product owner, không chỉ "theo dõi".
- Giả định quan trọng nhất là hồ sơ gia sư đủ sạch. Nếu sai, pilot phải lùi về bước chuẩn hóa hồ sơ và intake validation.

## Tổng kiểm tra trước khi sang `2-FINAL-pitch.md`

| Hạng mục | Xong? |
|---|---|
| Tóm vấn đề trong 1 câu | Xong |
| Budget tách hạng mục, không miscellaneous | Xong |
| Metric có baseline + ngưỡng + ai đo | Xong |
| Exit criteria có người có quyền thực thi | Xong |
| Adoption chỉ rõ ai dùng đầu tiên | Xong |

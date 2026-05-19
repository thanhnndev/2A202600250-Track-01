---
artifact: 5 — Solution Approach + 6 — Demo/Mockup/Flow (bản nộp phase Solution)
bai-tap: Solution — chốt cách làm + cho stakeholder nhìn thấy
phase: Double Diamond vòng 2 · ◆ siết
input: 1-find-existing-solutions.md · 00-context.md
nop-cuoi: Có
---

# 2 — FINAL: Solution Approach + Demo/Mockup/Flow

## Phần A — Chốt cách làm

- **Cách làm chốt**: Boost.
- **Lý do CẦN (không phải thích)**: Matching gia sư không phải lợi thế cạnh tranh cốt lõi ở mức thuật toán phức tạp trong pilot đầu; giá trị nằm ở dữ liệu hồ sơ BEETUTOR, rule phù hợp và workflow ops. Vì vậy nên boost quy trình hiện tại bằng model/API sẵn có: hard filter + weighted score + LLM explanation có nguồn + ops review.
- **Vì sao KHÔNG "Build từ số 0"**: Build full recommender cần nhiều booking/feedback thật để train và kiểm bias; hiện pilot chỉ có dữ liệu nhỏ. Build từ số 0 cũng kéo theo UI, data pipeline, audit, security và maintenance vượt phạm vi 6 tuần.
- **Tool / API / vendor cần + ước lượng chi phí thô**: Spreadsheet/Airtable hoặc database nhẹ cho 30-100 hồ sơ; Google Form/Typeform cho intake; LLM API để tạo explanation và flag thiếu dữ liệu; Zapier/Make hoặc script nhỏ để nối workflow. Ước lượng pilot: API 20-50 USD/tháng, tool form/database 0-30 USD/tháng, thời gian ops review 2-3 giờ/tuần.

## Phần B — Data & ai review

| Cần gì | Có sẵn trong BEETUTOR? | Trong lab dùng (mẫu/giả định) | Privacy? |
|---|---|---|---|
| Data: hồ sơ gia sư | Có trong outline: tuổi, giới tính, khu vực, online/offline, loại, môn, giá, thời lượng, rating, verification | 30 hồ sơ gia sư Toán THPT giả định | Có, ẩn giấy tờ và thông tin định danh nhạy cảm |
| Data: nhu cầu học viên | Có trong outline: lớp, môn, mục tiêu, lịch, thời lượng, ngân sách, khu vực | 50 yêu cầu Toán 10-12 giả định | Có, học viên vị thành niên nên cần consent/phụ huynh |
| Data: rule matching | Có trong outline: subject, format, area, tutor type, gender, price, duration, schedule | Bảng trọng số do ops lead duyệt | Không nhạy cảm nếu chỉ là rule |
| Data: feedback sau shortlist | Cần thu trong pilot | Đặt học thử/không đặt + lý do | Có, chỉ lưu mức cần thiết |

- **Output rủi ro cao**: Đề xuất gia sư cho học sinh vị thành niên; lý do nói về năng lực/verification của gia sư; loại gia sư khỏi shortlist vì thiếu fit.
- **Ai review + bao nhiêu mẫu + pass/fail theo gì**: Ops lead review 100% shortlist trong 2 tuần đầu, sau đó review ngẫu nhiên 30% nếu pass >=90%. Pass khi: không sai hard filter, lý do có nguồn từ hồ sơ, không bịa chứng chỉ/rating/lịch, không vượt ngân sách quá ngưỡng đã duyệt.
- **Có cần citation / nói "không biết" khi thiếu nguồn không**: Có. Mỗi lý do phải trỏ về field hồ sơ như "Dạy Toán 10-12", "Online + Offline", "Quận 1/3/Bình Thạnh", "250-350K/giờ", "Verified certificate + video". Thiếu nguồn thì ghi "chưa đủ dữ liệu, cần ops hỏi thêm".

## Phần C — Bản vẽ trực quan (BẮT BUỘC)

```text
BEETUTOR AI Shortlist Flow — pilot Toán THPT

[1] Phụ huynh nhập nhu cầu
    - Lớp: 10
    - Môn: Toán
    - Mục tiêu: đạt 8+ điểm
    - Khu vực: Quận 1, TP.HCM
    - Hình thức: online hoặc offline
    - Lịch: T2/T4/T6 19:00
    - Ngân sách: 200-300K/buổi
          |
          v
[2] Hard filters (không qua là loại)
    Môn/lớp đúng?  Khu vực/online đúng?  Lịch khớp?  Có verify tối thiểu?
          |
          v
[3] Weighted score
    + mục tiêu học     + lịch khớp      + ngân sách
    + kinh nghiệm      + rating/review  + loại gia sư ưu tiên
          |
          v
[4] LLM tạo shortlist có nguồn

    #1 Thầy Hoàng — 86/100
    Vì sao: dạy Toán 10-12; khu vực Q1/Q3/Bình Thạnh;
    online + offline; giá 250-350K/giờ; verified certificate + video.
    Cần ops check: giá 90 phút có vượt ngân sách 300K/buổi không?

    #2 Cô Linh — 80/100
    Vì sao: sinh viên sư phạm; nhận Toán 10; lịch tối T2/T4;
    giá 220K/giờ; online.
    Cần ops check: chưa có rating đủ 5 review.

    #3 Anh Minh — 74/100
    Vì sao: kỹ sư 5 năm, dạy Toán nâng cao; online;
    phù hợp mục tiêu 8+.
    Cần ops check: không dạy offline Q1.
          |
          v
[5] OPS REVIEW — bắt buộc trước khi gửi phụ huynh
    Approve / Edit reason / Remove tutor / Ask missing info
          |
          v
[6] Gửi phụ huynh shortlist 3 lựa chọn + lý do + nút đặt học thử
```

Chỗ con người review (output rủi ro cao) nằm ở: bước [5] OPS REVIEW. AI không gửi trực tiếp shortlist cho phụ huynh và không xác nhận booking.

## Tổng kiểm tra trước khi sang `../03-pilot-plan/`

| Hạng mục | Xong? |
|---|---|
| Cách làm có lý do CẦN, không mặc định tự build | Xong |
| Nói rõ data cần + ai review output rủi ro cao | Xong |
| Có bản vẽ trực quan, người ngoài hiểu trong ~20 giây | Xong |
| Có đánh dấu chỗ con người review | Xong |

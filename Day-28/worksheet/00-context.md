---
title: 00 — Context (bối cảnh cá nhân + track)
section: Day 28 — điền 1 lần đầu buổi, dùng lại cho mọi lần hỏi AI
format: Làm cá nhân
time: Điền ~5 phút đầu buổi
---

# 00-context.md — Context cá nhân + track

## 1. Bối cảnh AI20k (đọc, không sửa)

Khóa **AI Thực Chiến** có ~500 học viên, nhưng bài này được làm cá nhân theo yêu cầu: không nhóm, không thảo luận nhóm. Lab Day 28 vẫn dùng logic PM/PO AI: nhận một yêu cầu công cụ AI lớn, tách nhỏ, chọn Quick Win, rồi viết AI Pilot Plan đủ để stakeholder quyết định pilot.

## 2. Track của tôi

- **Track số / tên**: Track tự chọn cho BEETUTOR Marketplace — Bộ máy matching + onboarding gia sư/học viên.
- **Big Ask — chép nguyên văn câu yêu cầu trong track card / đề bài tự chọn**:

```text
Từ outline BEETUTOR Marketplace, xây một AI Pilot Plan cho công cụ AI giúp kết nối học viên với gia sư phù hợp, nhưng không build toàn bộ marketplace cùng lúc.
```

- **Công cụ lớn này phục vụ ai**: Học viên/phụ huynh cần tìm gia sư, gia sư, đội vận hành BEETUTOR.
- **2 Red Flag đáng lo nhất**: 1. Matching sai làm mất niềm tin hoặc gây rủi ro an toàn/riêng tư.  2. AI bịa năng lực, chứng chỉ, giá, lịch hoặc đưa đề xuất không giải thích được.

## 3. Ràng buộc mọi track phải tôn trọng

- **Privacy** — hồ sơ học viên, khu vực, tuổi, lịch học, ngân sách và giấy tờ gia sư là dữ liệu nhạy cảm; trong lab chỉ dùng data mẫu/giả định.
- **Human review** — output rủi ro cao như xác minh gia sư, khuyến nghị phù hợp cho trẻ vị thành niên, hoặc quyết định khóa tài khoản phải có người review.
- **Citation** — nếu dựa trên hồ sơ, chứng chỉ, review hoặc chính sách nền tảng thì phải dẫn nguồn nội bộ; thiếu nguồn thì nói "không đủ dữ liệu".
- **Budget nhỏ** — ưu tiên prototype bằng model/API sẵn có + dữ liệu riêng, không xây full marketplace.
- **Formative ≠ summative** — điểm phù hợp do AI gợi ý chỉ là hỗ trợ quyết định, chưa thay thế duyệt của phụ huynh/học viên và đội vận hành.
- **Adoption** — nếu học viên/ops không dùng trong workflow tìm gia sư thật thì pilot không có giá trị.
- **Pilot đủ nhỏ** — chạy được với một lát cắt: Toán THPT online/offline tại TP.HCM.

## 4. Ghi chú thêm

- Làm cá nhân, không có thành viên nhóm.
- Nguồn sản phẩm chính: `BEETUTOR-MARKETPLACE.md`.
- Data giả định cho pilot: 30 hồ sơ gia sư đã verify sơ bộ, 50 yêu cầu học Toán 10-12 ở TP.HCM, 20 lịch booking/thử học.
- Mục tiêu pilot: giảm thời gian shortlist gia sư phù hợp và tăng tỷ lệ học viên đặt buổi học thử.

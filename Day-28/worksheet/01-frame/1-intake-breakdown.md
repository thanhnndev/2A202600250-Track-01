---
artifact: 1 — Track & Big Ask + 2 — Tool Breakdown
bai-tap: Frame — nghe đúng đề rồi tách nhỏ
phase: Double Diamond vòng 1 · ◇ giãn
input: 00-context.md · BEETUTOR-MARKETPLACE.md
nop-cuoi: Không — file trung gian
---

# 1 — Intake & Breakdown: nghe đúng đề, tách nhỏ

## Phần A — Phát biểu lại Big Ask bằng lời cá nhân

- **Big Ask, viết lại bằng lời tôi**: BEETUTOR Marketplace muốn dùng AI để hỗ trợ kết nối học viên/phụ huynh với gia sư phù hợp dựa trên môn học, mục tiêu, khu vực, lịch, ngân sách, hình thức học và độ tin cậy của gia sư. Không nên build toàn bộ marketplace ngay; cần chọn một lát cắt đủ nhỏ để chứng minh AI làm giảm công sức tìm kiếm và tăng chất lượng shortlist.
- **Tại sao bây giờ**: Outline BEETUTOR có rất nhiều biến matching trước booking: hồ sơ học viên, loại gia sư, giá, thời lượng, lịch, khu vực, verification, rating. Nếu xử lý thủ công hoặc filter cứng, học viên dễ bị quá tải lựa chọn, còn ops phải hỏi lại nhiều lần trước khi có shortlist.
- **Người dùng đầu tiên cụ thể**: Phụ huynh/học viên lớp 10-12 tại TP.HCM đang cần tìm gia sư Toán trong 7 ngày tới; ops BEETUTOR là người review shortlist trước khi gợi ý.

## Phần B — Tách công cụ lớn thành 5-8 use case

| # | Use case (AI làm gì · cho ai · để họ làm được gì) | Người dùng | Làm được độc lập? |
|---|---|---|---|
| 1 | AI đọc nhu cầu học viên/phụ huynh và chuẩn hóa thành intake có cấu trúc: môn, lớp, mục tiêu, lịch, ngân sách, khu vực, hình thức học | Học viên/phụ huynh, ops | Có |
| 2 | AI chấm mức phù hợp giữa 1 yêu cầu học và danh sách gia sư đã verify để tạo top 3 shortlist có lý do | Học viên/phụ huynh, ops | Có |
| 3 | AI phát hiện thông tin thiếu/mâu thuẫn trong hồ sơ học viên trước khi matching | Học viên/phụ huynh, ops | Có |
| 4 | AI tóm tắt hồ sơ gia sư thành card dễ hiểu trước booking, kèm điểm mạnh/yếu và nguồn từ hồ sơ | Học viên/phụ huynh | Có |
| 5 | AI gợi ý mức giá/thời lượng phù hợp với ngân sách và mục tiêu học, không tự quyết giá cuối | Học viên/phụ huynh, gia sư | Có, phụ thuộc bảng giá |
| 6 | AI hỗ trợ ops kiểm tra hồ sơ gia sư có đủ giấy tờ, chứng chỉ, video giới thiệu trước khi public | Ops, gia sư | Có |
| 7 | AI tạo tin nhắn giới thiệu gia sư cá nhân hóa để phụ huynh dễ chọn buổi học thử | Ops, học viên/phụ huynh | Có, phụ thuộc shortlist |
| 8 | AI theo dõi sau buổi học thử và gợi ý tiếp tục/đổi gia sư dựa trên feedback | Học viên/phụ huynh, ops | Có, sau booking |

## Phát hiện ban đầu

- Phần rủi ro nhất không phải tạo UI marketplace mà là quyết định shortlist: sai matching sẽ làm mất niềm tin ngay từ lần đầu dùng.
- Có thể pilot nhỏ với dữ liệu giả định: Toán THPT tại TP.HCM, 30 gia sư verify sơ bộ, 50 yêu cầu học viên.
- AI nên đóng vai "shortlist assistant" cho ops/phụ huynh, không tự động duyệt gia sư hoặc xác nhận booking.

## Câu hỏi mở (mang sang bước chọn Quick Win)

- Baseline hiện tại: ops mất bao lâu để tạo shortlist 3 gia sư cho một yêu cầu?
- Học viên/phụ huynh cần bao nhiêu lý do để tin một đề xuất gia sư?
- Tiêu chí nào bắt buộc loại trừ ngay: thiếu verification, lệch khu vực, lệch lịch, vượt ngân sách bao nhiêu?

## Tổng kiểm tra trước khi sang `2-quick-win.md`

| Hạng mục | Xong? |
|---|---|
| Phát biểu lại Big Ask rõ, không cần nhìn outline | Xong |
| Có 5-8 use case dạng "AI làm X cho ai để Y" | Xong |
| Có >=4 use case thật sự độc lập | Xong |
| Không pitch "build cả marketplace" | Xong |

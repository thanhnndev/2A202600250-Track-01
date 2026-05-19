# Glossary — Day 28

> Tra nhanh khi gặp từ lạ, không cần học thuộc. Thuật ngữ giữ tên tiếng Anh vì đó là tên dân trong nghề dùng — giải nghĩa bằng tiếng Việt ở đây.

---

## Hành trình & cách làm việc

**Hành trình triển khai AI · Ý tưởng → Production**
Đường đi của một sản phẩm AI từ lúc có ý tưởng đến lúc chạy thật. Day 28 học 3 phase ở giữa: Frame → Solution → Pilot Plan. Hai đầu (Ý tưởng đầu vào; chạy thật/Production về sau) không học hôm nay.

**[Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process)**
Lăng kính tư duy nhắc lại từ Day 2: mỗi phase đều có pha **giãn ra** (◇ — mở rộng nhiều khả năng) rồi **siết lại** (◆ — chốt một hướng). Đây là *cách soi* công việc, không phải các bước phải làm.

**Frame / Solution / Pilot Plan**
3 phase của lab, mỗi phase là một vòng Double Diamond.
- **Frame** — hiểu đúng vấn đề: nghe đề → tách nhỏ → chọn Quick Win → Problem Framing. Sai ở đây thì mọi thứ sau vô nghĩa.
- **Solution** — chọn cách làm (Build/Buy/Boost/Partner) + bản vẽ trực quan. Trực quan là bắt buộc, demo chạy được chỉ là điểm cộng.
- **Pilot Plan** — cam kết hai chiều: xin – hứa – đo – dừng, rồi pitch xin approve.

**Quick Win**
Lát cắt nhỏ đầu tiên của một công cụ AI lớn, chọn để pilot trước. Quan trọng: Quick Win = phần *chứng minh được giá trị nhanh và có người ủng hộ*, **không phải** phần dễ nhất hay nghe hay nhất. Chọn sai → mất uy tín, khó xin pilot tiếp.

**Problem Framing**
Đóng khung vấn đề trước khi nghĩ giải pháp: ai đau · đau ở đâu trong công việc · pain có số hay cảm tính · baseline · success metric · constraint. "Học viên cần học tốt hơn" chưa phải Problem Framing thật.

**AI Pilot Plan**
Bản kế hoạch xin chạy thử một lát cắt AI có giới hạn, đủ để stakeholder quyết approve hay dừng. Là **cam kết hai chiều** (xin nguồn lực ↔ hứa giao evidence + chấp nhận dừng nếu metric fail), không phải proposal xin tiền. Gồm: scope · người · data · budget · timeline · metric (kèm baseline + ngưỡng) · exit criteria · adoption · lời hứa · lời xin.

**A3 Working Canvas**
Bộ nộp chính — 7 mục nằm rải trong các file `worksheet/`: Track & Big Ask · Tool Breakdown · Quick Win · Problem Framing · Solution Approach *(đã gồm Data & Expert)* · Demo/Mockup/Flow · AI Pilot Plan.

**AI Support Log**
Ghi ngắn cuối buổi: AI giúp gì · AI đưa output nào nghe hợp lý nhưng nhóm phải sửa · phần nào nhóm tự lập luận không copy AI. Bằng chứng nhóm dùng AI như công cụ, không phụ thuộc AI.

**File FINAL vs file trung gian**
File `…-FINAL-…` là bản nộp người chấm xem. File đánh số (`1-…`, `2-…`) là trung gian — vẫn phải nộp kèm để thấy nhóm đi qua đủ các bước (`nop-cuoi:` trong frontmatter ghi rõ).

---

## Chọn cách làm

**Build / Buy / Boost / Partner**
4 hướng triển khai một use case AI:
- **Build** — tự xây từ đầu. Tốn nhất, khó rút lại, chỉ chọn khi thật sự là lợi thế cốt lõi.
- **Buy** — mua tool/API có sẵn dùng ngay. Nhanh, phụ thuộc vendor.
- **Boost** — model có sẵn + ghép data/prompt riêng. Cân bằng; 80–90% use case nội bộ thuộc nhóm này.
- **Partner** — hợp tác bên đã có sẵn năng lực/data thay vì tự làm.

**Tool Breakdown**
Tách một "công cụ AI lớn" thành 5–8 use case nhỏ, độc lập, mỗi cái làm được riêng. Buộc nhóm thấy: không thể xây hết → phải chọn lát cắt.

**Pattern / deep research**
Trước khi tự xây, gọi tên *dạng bài* (pattern) — bỏ context đi, bài này thực ra là dạng gì (Q&A có citation, extraction, rubric grading...). Rồi deep research 4 tầng (map → tiền lệ → phản chứng → thu hẹp) xem ai đã giải dạng bài đó rồi để "đi từ 5 lên", không từ 0.

**Quick Win Scoring**
Bảng chấm nhanh chọn lát cắt, 4 trục: Impact · Feasibility · Evidence nhanh · Risk (điểm Risk cao = rủi ro thấp). Điểm chỉ là gợi ý; quyết định vẫn của nhóm. "Có người ủng hộ" thường quan trọng hơn "impact cao".

**baseline**
Số liệu hiện tại *trước khi* có AI, làm mốc so sánh. Không có baseline thì "cải thiện 30%" vô nghĩa (so với cái gì?). Chưa có thì phải đo *trước khi* pilot.

**success metric**
Thước đo pilot có hiệu quả không. Phải: đo được · có baseline · có ngưỡng pass/fail · stakeholder đồng ý ngưỡng.

**exit criteria**
Điều kiện định trước khiến pilot phải dừng (vd accuracy < 80% trong 1 tuần, lộ data 1 lần). Chỉ có giá trị nếu **người có quyền dám thực thi**, không chỉ trên giấy.

**adoption**
Kế hoạch để tool được dùng thật: ai dùng đầu tiên, workflow đổi thế nào, ai train. Tool không ai dùng = $0 dù accuracy 99%.

---

## Bản vẽ trực quan

**Demo / Mockup / Flow**
Artifact để stakeholder *nhìn* được ý tưởng thay vì nghe kể. Bắt buộc ≥1 dạng; demo chạy được chỉ là điểm cộng.
- **Mockup** — phác 2–3 màn hình: user thấy gì, bấm gì, nhận gì.
- **User flow** — các bước user đi qua; hay kèm so sánh before/after.
- **Prompt flow** — input → prompt/model → output.
- **Agent flow** — agent tự đi nhiều bước + điểm con người review.
- **Sample input/output** — 1 cặp ví dụ thật: input X → output Y. Nhanh nhất để stakeholder hiểu.

---

## Trình bày & phản biện

**5-slide Pitch**
5 slide / 5 phút: (1) Problem & user · (2) Breakdown & Quick Win · (3) Solution + bản vẽ · (4) AI Pilot Plan · (5) Metric, exit criteria & **lời xin**. Slide cuối là lời xin rõ ràng.

**5-Gate (bảng chấm)**
Chấm theo gate: qua mới đi tiếp, không cộng điểm checklist. Gate 4 yêu cầu bản vẽ trực quan — bắt buộc. Xem `templates/rubric-gate-sheet.md`.

**Phản biện (challenge)**
Câu hỏi khó business owner/instructor hỏi để kiểm độ chắc của lập luận. 3 câu mặc định: *số/giả định lấy ở đâu · giả định chính sai thì sao · tình huống nào khiến dừng pilot*. Trả lời được = sẵn sàng.

**00-context (shared context)**
File context dùng chung: bối cảnh AI20k, người dùng, ràng buộc. Điền 1 lần đầu buổi, paste vào AI mỗi lần hỏi.

**Track card**
Thẻ mô tả 1 track (1 công cụ lớn): big ask, người dùng, workflow hiện tại, big vision modules, vài Quick Win gợi ý, data sẵn có, red flags. Mỗi nhóm nhận 1 card. Xem `templates/track-cards.md`.

---

## Ràng buộc lab (nhắc nhanh)

- **Formative ≠ summative** — feedback/chấm bằng AI trong lab là formative (để học), chưa phải điểm chính thức nếu chưa có người calibrate.
- **Human review** — output rủi ro cao phải có người review.
- **Citation** — trả lời dựa trên tài liệu khóa phải dẫn nguồn; thiếu thì nói "không biết".
- **Privacy** — data học viên/submission/Discord nhạy cảm; lab dùng data mẫu/giả định.
- **Budget nhỏ** — ưu tiên tool/API sẵn có, prototype nhanh, không xây platform lớn.

---

*Glossary D28 · gặp từ chưa có trong list → hỏi giảng viên hoặc TA.*

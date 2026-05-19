# Ngày 28 — Triển khai AI trong doanh nghiệp: Từ yêu cầu mơ hồ đến AI Pilot Plan
## Sổ tay học viên — Hành trình triển khai AI · Ý tưởng → Production

**Chương trình:** VinUni A20 — AI Thực Chiến (track Sản phẩm AI)
**Mục đích:** Trang bị một *cách làm việc* để biến một yêu cầu AI mơ hồ từ doanh nghiệp thành một bản kế hoạch đủ bằng chứng để người có quyền *phê duyệt hoặc dừng*. Sổ tay này là bản mở rộng của bài giảng — học viên giữ lại để dùng khi đi làm.
**Câu hỏi dẫn dắt (Driving question):** *"Biến yêu cầu AI mơ hồ thành một bản kế hoạch — có đủ bằng chứng để duyệt không?"*

> **Cách đọc tài liệu này.** Đọc Phần 1–3 (định vị + mô hình quy chiếu + lý thuyết nền) để có lăng kính. Phần 4 là chi tiết từng Bước 1–8 — tra cứu khi làm tới bước đó. Phần 5 là mẫu đầu ra (§A1–A9) — xem khi cần hình dung "xong thì trông thế nào". Phần 6 là bộ câu hỏi dùng cho AI. Phần 7 là kho case + nguồn. Phần 8 là phần Lab. Phần 9 là bảng tổng mang về.

---

## 1. Định Vị Buổi Học

### 1.1 Đầu ra của một PM/PO AI không phải slide đẹp

Đây là buổi cuối của track Sản phẩm AI. Buổi này không thêm một khung lý thuyết rời rạc nào nữa — nó dạy **một cách làm việc duy nhất**: nhìn mình đang ở đâu trên hành trình triển khai, biết phải hỏi gì, gặp ai, tạo ra cái gì, và mốc nào cho phép đi tiếp.

```
KHÔNG PHẢI: "Học thêm một khung lý thuyết"
MÀ LÀ:      "Một cách làm việc: biết mình ở đâu, hỏi gì, tạo gì, dừng khi nào"
```

Ý tưởng lớn của buổi:

> Biến yêu cầu AI mơ hồ thành một bản kế hoạch có thể ra quyết định.
> Đầu ra không phải một slide thuyết phục — mà là **bằng chứng đủ mạnh để duyệt hoặc dừng**.

Hai nguyên tắc chất lượng đi kèm, đúng cho cả buổi và phần Lab:

```
"Bản demo đơn giản + lập luận chặt  >  bản demo đẹp + lập luận yếu."
"Một bản kế hoạch cho vấn đề SAI — dù viết hay — vẫn là sai."
```

### 1.2 Vài thuật ngữ lõi (giải nghĩa lần đầu)

Sổ tay viết bằng tiếng Việt thoát nghĩa. Chỉ năm cụm dưới đây được giữ nguyên tên tiếng Anh vì đã thành thuật ngữ nghề; mọi khái niệm khác đều được dịch.

| Thuật ngữ | Nghĩa dùng trong tài liệu này |
|---|---|
| **AI Pilot Plan** | Bản kế hoạch xin chạy thử một giải pháp AI ở quy mô nhỏ. Bản thân "Pilot Plan" là phần *kế hoạch* (xin gì – hứa gì – đo gì – dừng khi nào) nằm bên trong; gói nộp đầy đủ ở Lab = A3 Working Canvas + 5-slide Pitch + Nhật ký AI hỗ trợ. |
| **Quick Win** | Lát cắt nhỏ được chọn để làm trước, nhằm chứng minh giá trị sớm với rủi ro thấp. Không phải bài "dễ nhất", cũng không phải bài "lớn nhất". |
| **Problem Framing** | Bản khung lại vấn đề thật — tài liệu xác nhận "tôi đã hiểu đúng vấn đề chưa?" trước khi thiết kế giải pháp. |
| **Build / Buy / Boost / Partner** | Bốn hướng làm: **Build** = tự xây mô hình riêng; **Buy** = mua công cụ có sẵn; **Boost** = tăng cường công cụ/mô hình có sẵn bằng dữ liệu riêng (ví dụ RAG); **Partner** = hợp tác với đội đã giải bài tương tự. |
| **[Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process)** | Hai "viên kim cương" tư duy của thiết kế (mở rộng rồi thu hẹp), nhắc lại từ Ngày 2. Ở Ngày 28 nó là **lăng kính tư duy**, KHÔNG phải xương sống của buổi. |

Các cụm khác được dịch nhất quán: *baseline* → mốc nền; *exit criteria* → tiêu chí dừng; *deliverable* → đầu ra phải nộp; *stakeholder* → người giao đề / người duyệt; *constraint* → ràng buộc; *adoption* → mức độ được sử dụng thật; *leading indicator* → chỉ báo sớm; *RACI* → bảng phân vai (làm / chịu trách nhiệm / tư vấn / cần biết).

### 1.3 Quy ước ghi nguồn (giữ nguyên cạnh mọi số liệu)

Mọi số liệu trong tài liệu này đều mang một dấu nguồn. Học viên phải giữ thói quen này khi đi làm — vì câu hỏi phản biện đầu tiên ở mọi cuộc duyệt là *"số liệu này lấy ở đâu?"*

| Dấu | Nghĩa |
|---|---|
| ✅ | Nguồn gốc — đúng nguyên văn, có link sơ cấp kiểm chứng được |
| 🧮 | Ước tính để giảng — con số dựng cho lớp học, không phải doanh nghiệp công bố |
| 🗣️ | Người trong cuộc kể — case thực hành trực tiếp (của giảng viên) |
| ⚠️ | Nguồn thứ cấp — báo chí / phân tích, chưa kiểm chứng tài chính sơ cấp |
| 📖 | Cần mua mới đọc — nguồn học thuật / sau tường phí |

Khi một ví dụ chỉ là phép loại suy để minh họa cách nghĩ, tài liệu ghi rõ "phép loại suy ghép, không phải dự án có thật" — không gắn tên thương hiệu thật cho ví dụ chưa có nguồn.

### 1.4 Buổi này nối tiếp gì

| Đã học | Mang sang Ngày 28 |
|---|---|
| Ngày 2 — Tư duy thiết kế (Design Thinking) để **tìm đúng vấn đề** | Double Diamond quay lại làm lăng kính, lần này cho *triển khai* |
| Ngày 26 — Phán đoán sản phẩm AI | Biết bài nào đáng làm, bài nào không |
| Ngày 27 — Kinh tế sản phẩm AI (chi phí, định giá, ROI, kiểm tra áp lực) | Dùng để dựng phần ngân sách + mốc nền + ngưỡng trong AI Pilot Plan |

---

## 2. Mô Hình Quy Chiếu — Khóa Cứng

Cả buổi chỉ dùng **một** hệ quy chiếu. Mọi bản đồ tổng quan, mọi mục mở phase, mọi bản tóm tắt đều bám đúng hệ này.

### 2.1 Xương sống: Hành trình triển khai AI · Ý tưởng → Production

```
Ý TƯỞNG →[  HIỂU VẤN ĐỀ  ·  CHỌN CÁCH LÀM  ·  KẾ HOẠCH THỬ NGHIỆM  ]→ CHẠY THỬ → PRODUCTION
          └────────────────── Ngày 28 học sâu ──────────────────┘
```

- Gọi tên ba phase theo nội dung: **FRAME** (Hiểu vấn đề) · **SOLUTION** (Chọn cách làm) · **PILOT PLAN** (Kế hoạch thử nghiệm).
- "Ý tưởng" = đề bài mơ hồ đầu vào, có trước Ngày 28.
- "Chạy thử / Production" = về sau, KHÔNG học hôm nay (bản đồ chỉ vẽ mờ ở cuối đường).

| Giai đoạn | Tương ứng ở Ngày 28 | Khi nào |
|---|---|---|
| Ý tưởng | Đề bài mơ hồ đầu vào | Trước Ngày 28 |
| **HIỂU VẤN ĐỀ** | Bước 1–3 + ◆ Problem Framing | Ngày 28 hôm nay |
| **CHỌN CÁCH LÀM** | Bước 4–5 (Approach + Demo/Mockup/Flow) | Ngày 28 hôm nay |
| **KẾ HOẠCH THỬ NGHIỆM** | Bước 6–8 (Pilot Plan + Đo lường + Trình bày) | Ngày 28 hôm nay |
| Chạy thử | Chạy pilot thực tế | Sau Ngày 28 |
| Production | Mở rộng, vận hành, chuyển giao | Về sau |

### 2.2 Quy tắc dùng từ (chống trôi nghĩa)

Đây là phần quan trọng nhất của mô hình quy chiếu — đọc kỹ:

- **KHÔNG dùng** các cụm "lifecycle / vòng đời / Tầng 0-1-2 / Phase 1-2-3-4". Chỉ có **3 phase** (FRAME / SOLUTION / PILOT PLAN) gom **8 bước**. "Vòng đời" hàm ý nhiều hơn những gì buổi này dạy (vận hành, quản trị, ngừng sản phẩm) nên không dùng.
- *Double Diamond* là **lăng kính tư duy** nhắc lại từ Ngày 2 — viên kim cương thứ nhất phủ phase FRAME, viên thứ hai phủ phase SOLUTION và đầu phase PILOT PLAN. Nó là *lens*, KHÔNG phải xương sống, KHÔNG phải "một tầng".
- Tên đầu ra nhất quán: **AI Pilot Plan**. Gói nộp ở Lab = A3 Working Canvas (7 mục) + 5-slide Pitch + Nhật ký AI hỗ trợ.

### 2.3 Tám câu hỏi tự kiểm — mỏ neo cả buổi

Hết buổi, học viên phải tự trả lời được tám câu này cho *bất kỳ* dự án AI nào. Mỗi bước trong buổi học chính là học cách trả lời một câu.

| Phase | # | Câu hỏi tự kiểm |
|---|---|---|
| **FRAME** | 1 | Đã hỏi "tại sao bây giờ" chưa? |
|  | 2 | Đã đi đủ một vòng, thấy được pattern chưa? |
|  | 3 | Quick Win có bằng chứng nhanh + người bảo trợ chưa? |
|  | ◆ | Người giao đề đã xác nhận đúng vấn đề chưa? |
| **SOLUTION** | 4 | Build/Buy/Boost/Partner — có lý do, không phải vì cái tôi? |
|  | 5 | Đã có mockup/flow để người duyệt hình dung **và** chuyên gia soi đầu ra chưa? |
| **PILOT PLAN** | 6 | Xin gì / hứa gì / đo gì / dừng khi nào — rõ chưa? |
|  | 7 | Chỉ số có mốc nền + ngưỡng + người đo chưa? |
|  | 8 | Đủ bằng chứng để xin phê duyệt chưa? |

> Câu 5 đặc biệt: trực quan hóa (mockup/flow) là **bắt buộc**, không chỉ "kể bằng miệng". Một bản demo chạy được chỉ là điểm cộng.

### 2.4 Bản đồ xương sống (thẻ 3 cột)

Mọi bước trong buổi là MỘT thẻ trong bản đồ này phóng to lên:

```
HÀNH TRÌNH TRIỂN KHAI AI · Ý TƯỞNG → PRODUCTION
Lối vào:  ⓐ "AI đi đâu" (rất mơ hồ)  ·  ⓑ "Build công cụ X" (cụ thể)  ·  ⓒ "Tích hợp AI vào sản phẩm" (vừa)
          — cả ba cùng đi một đường, chỉ khác điểm bắt đầu và độ sâu phase FRAME

┌ HIỂU VẤN ĐỀ ───────┐┌ CHỌN CÁCH LÀM ─────┐┌ KẾ HOẠCH THỬ NGHIỆM ──┐
│ 1 Nhận đề           ││ 4 Approach          ││ 6 Pilot Plan           │
│ 2 Bóc tách & khảo   ││ 5 Demo/Mockup/Flow  ││ 7 Đo lường & gate      │
│ 3 Chọn Quick Win    ││   (artifact trực     ││ 8 Trình bày & duyệt    │
│ ◆ Problem Framing   ││    quan BẮT BUỘC;    ││                        │
│   (người giao xác    ││    demo chạy = cộng) ││                        │
│    nhận ✓)          ││                      ││                        │
└─ ╲ Kim cương 1 ╱ ───┘└─── ╲ Kim cương 2 ╱ ─┘└────────────────────────┘
 Đầu ra: Hồ sơ Vấn đề   Approach + Demo          AI Pilot Plan + Pitch
 (Phần A)               (Phần B + C)             (Phần D + E)
Double Diamond = lăng kính tư duy (từ Ngày 2), không phải xương sống.
```

---

## 3. Lý Thuyết Nền

### 3.1 Double Diamond — lăng kính, không phải xương sống

Ngày 2 dạy Tư duy thiết kế để *tìm đúng vấn đề*. Ngày 28 dùng lại chính Tư duy thiết kế nhưng cho *triển khai đúng cách*.

```
  KIM CƯƠNG 1                         KIM CƯƠNG 2
  "Hiểu đúng vấn đề"                   "Thiết kế đúng cách triển khai"

   mở rộng: khảo sát tổ chức,          mở rộng: tìm các phương án,
   phòng ban, workflow, pain,          Build/Buy/Boost/Partner,
   dữ liệu                             nhà cung cấp, đối chiếu pattern
        ↓ thu hẹp:                          ↓ thu hẹp:
   chọn 1 bài cụ thể                    chọn 1 cách làm + kế hoạch
        ↓                                    ↓
   ┌──────────────┐                    ┌──────────────┐
   │ PROBLEM      │                    │ AI PILOT     │
   │ FRAMING      │                    │ PLAN         │
   └──────────────┘                    └──────────────┘
   "Tôi đã hiểu đúng                   "Tôi xin gì, hứa gì,
    vấn đề chưa?"                       đo gì, dừng khi nào?"
```

Bốn bước của thiết kế lấy người dùng làm trung tâm, đọc lại cho ngữ cảnh triển khai:

| Bước | Ngày 2 (tìm vấn đề) | Ngày 28 (thiết kế triển khai) |
|---|---|---|
| Quan sát | Quan sát workflow người dùng | Khảo sát tổ chức: phòng ban, leader, dữ liệu, ràng buộc |
| Lên ý tưởng | Tạo nhiều ý tưởng giải pháp | Build/Buy/Boost/Partner? Nhà cung cấp nào? Quick Win nào? |
| Tạo bản thử | Mockup nhanh: phác thảo, người đóng vai AI | Demo nhanh: phác thảo → sinh mockup → đưa người duyệt xem |
| Kiểm chứng | Test với ~5 người dùng, cải thiện, lặp | Chuyên gia soi đầu ra. Pilot nhỏ với 5–10 người |

### 3.2 Bảy lối tư duy nền tảng

Đây không phải checklist phải nhớ thuộc. Đây là *tư duy chạy ngầm* dưới mỗi bước — học viên cần biết **lúc nào dùng cái nào**.

| # | Lối tư duy | Nguyên lý một câu | Câu hỏi tự kiểm |
|---|---|---|---|
| L1 | **Decompose** (Bóc tách) | Đề bài mơ hồ = triệu chứng. Đào đến ràng buộc thật. | "Tôi đã hỏi đủ 'tại sao' chưa?" |
| L2 | **Quick Win** | Đừng giải bài lớn nhất. Giải bài *chứng minh được* nhanh nhất. | "Bài này có thể cho thấy kết quả trong 2 tuần không?" |
| L3 | **Domain Expert** (Chuyên gia nghiệp vụ) | Công cụ AI mà không có chuyên gia nghiệp vụ = xây trong chân không. | "Ai hiểu nghiệp vụ sẽ ngồi cùng tôi?" |
| L4 | **Show → Validate** (Cho xem rồi mới kiểm chứng) | Cho xem trước, xây sau. Bản thử là công cụ để hiểu đề. | "Tôi đã đưa bản thử cho người duyệt xem chưa?" |
| L5 | **Pattern Match** (Đối chiếu pattern) | Hầu hết bài toán AI đã có người giải ở lĩnh vực khác. | "Bài này giống bài nào ở ngành khác?" |
| L6 | **Measure → Decide** (Đo để quyết) | Pilot sinh ra bằng chứng cho quyết định, không phải "thử xem sao". | "Tôi đang đo cái gì? Ngưỡng bao nhiêu?" |
| L7 | **Adopt to Operate** (Phải được dùng thật mới có giá trị) | AI chỉ có giá trị khi đi vào workflow thật của người thật. | "Ai sẽ dùng hằng ngày? Họ có *muốn* dùng không?" |

**L7 — chi tiết.** Một pilot AI thường KHÔNG chết vì mô hình sai. Nó chết vì: (1) không ai dùng, (2) không ai sở hữu, (3) không khớp workflow, (4) không có người vận hành. Sáu câu hỏi bắt buộc của L7:

1. Ai dùng **đầu tiên**? (không phải "toàn công ty")
2. Workflow đổi ở **bước nào**? (vẽ trước/sau)
3. Ai huấn luyện người dùng? Ai hỗ trợ khi lỗi?
4. **Động lực** nào khiến họ dùng? (hoặc: đau gì nếu *không* dùng?)
5. Nếu chuyên gia nghiệp vụ nghỉ — pilot có chết không?
6. (gộp với 5) Ai vận hành tiếp khi người khởi xướng rời đi?

> L7 quan trọng nhất nhưng ít người nghĩ tới: một công cụ chính xác 99% mà 0 người dùng < một công cụ chính xác 85% mà 500 người dùng hằng ngày.

### 3.3 Ba dạng đề bài doanh nghiệp

| Dạng | Mức độ mơ hồ | Ví dụ | Cách tiếp cận |
|---|---|---|---|
| **ⓐ "AI đi đâu?"** | Rất mơ hồ | Lãnh đạo: "đưa AI vào công ty" | Khảo sát toàn tổ chức → lập bảng use case → chọn Quick Win |
| **ⓑ "Build công cụ X"** | Cụ thể | "Cần AI sàng lọc CV" | Đã có đề + người phụ trách → bóc tách → bản thử → pilot |
| **ⓒ "Tích hợp AI vào sản phẩm A"** | Vừa | "Thêm AI vào app hiện tại" | Đã có người dùng → tìm điểm tích hợp → kiểm chứng |

Cả ba dạng đều đi qua **cùng một** hành trình 8 bước — chỉ khác điểm bắt đầu và độ sâu của phase FRAME. Dạng ⓐ nguy hiểm nhất: không có phạm vi → dễ lan man, nên phase FRAME phải làm kỹ nhất.

---

## 4. Tám Bước — Chi Tiết Từng Bước

> Mỗi bước đọc theo cùng một khung: **Câu hỏi định hướng → Nhiệm vụ trọng tâm → Kết quả đầu ra → Điều kiện chuyển bước → ⚠ Lỗi thường gặp** (kèm vai trò, lối tư duy chủ đạo, mốc thời gian tham khảo, ánh xạ đầu ra). Câu hỏi định hướng của mỗi bước chính là một trong tám câu tự kiểm.

### FRAME: Hiểu vấn đề — Bước 1–3 + Problem Framing

Phase này trả lời: *Họ thực sự muốn gì? Ai đau, đau ở đâu, đau bao nhiêu? Bài nào chứng minh giá trị nhanh nhất? Tôi hiểu đúng vấn đề chưa?*

Ai vào phòng (swimlane phase FRAME):

| Vai | Ai |
|---|---|
| Chủ trì | PM/PO |
| Tham gia | Người giao đề (chủ doanh nghiệp) · các leader phòng ban · người dùng chính · chuyên gia nghiệp vụ |
| Làm với ai | Chủ doanh nghiệp cho mục tiêu/ràng buộc · leader cho workflow/KPI · người dùng cho nỗi đau thật · chuyên gia kiểm nghiệp vụ đúng/sai |
| Dữ liệu cần | Workflow · khối lượng · thời gian/chi phí/lỗi · KPI · vài mẫu thật |
| AI hỗ trợ | Tóm tắt phỏng vấn · tra cứu bài tương tự · soạn nháp khung vấn đề |
| Đầu ra | Problem Framing (Phần A) |
| Mốc qua phase | Người giao đề nói: "Đúng, đây là vấn đề đáng giải." |
| Lỗi thường gặp | Khung sai vấn đề; chọn bài mình thích thay vì bài doanh nghiệp cần |

---

#### Bước 1 — Nhận Đề Bài

| Trường | Nội dung |
|---|---|
| **Câu hỏi định hướng** (= câu tự kiểm 1) | "Họ THỰC SỰ muốn gì?" |
| **Nhiệm vụ trọng tâm** | • NGHE — ghi nguyên văn, KHÔNG diễn giải • Hỏi: "Tại sao BÂY GIỜ?" (chuyện gì vừa xảy ra?) • Hỏi: "Thành công là gì?" (3 tháng sau muốn thấy gì?) • Xác định dạng đề ⓐ/ⓑ/ⓒ + ghi ràng buộc ban đầu (ngân sách, thời gian, đội ngũ, tuân thủ) |
| **Kết quả đầu ra** | Đề bài thô (nguyên văn) + dạng đề + ràng buộc → nuôi Phần A, mục "Đề bài gốc" |
| **Điều kiện chuyển bước** | Trả lời được "tại sao bây giờ" + "thành công là gì". ✗ Chưa rõ → ở lại Bước 1, KHÔNG nhảy sang giải pháp |
| **⚠ Lỗi thường gặp** | Nhận "giải pháp bề nổi" làm đề bài. Ví dụ: Khách hàng yêu cầu "làm chatbot CSKH", nhưng đó chỉ là giải pháp tự nghĩ ra để trị triệu chứng ẩn sâu (như luồng xử lý chậm, tài liệu cũ). Nhận đề y nguyên mà không hỏi lại là sai lầm. Lối tư duy chủ đạo: **L1 Decompose**. Mốc thời gian tham khảo: 1–2 buổi họp (1–3 ngày). |

Bảng "họ nói vs vấn đề thật có thể là":

| Họ nói | Vấn đề thật có thể là |
|---|---|
| "Làm chatbot CSKH" | Định tuyến ticket chậm, FAQ lỗi thời, huấn luyện agent kém |
| "Đưa AI vào marketing" | Quy trình nội dung chậm, cá nhân hóa yếu, báo cáo mất 3 ngày |
| "Tự động hóa HR" | Sàng lọc CV mất 40h/tháng, onboarding không nhất quán |
| "Cần AI cho sales" | Dự báo không chính xác, dữ liệu CRM bẩn, follow-up bị rớt |

---

#### Bước 2 — Bóc Tách & Khảo Sát

| Trường | Nội dung |
|---|---|
| **Câu hỏi định hướng** (= câu tự kiểm 2) | "Toàn cảnh tổ chức: ai đau ở đâu, đau bao nhiêu?" |
| **Nhiệm vụ trọng tâm** | • ĐI MỘT VÒNG: gặp nhiều leader, không chỉ một phòng • Quan sát workflow thật; ghi khối lượng/thời gian/chi phí/lỗi • Kẻ bảng pain × tác động × dữ liệu × khả thi • Dùng AI tra cứu sâu các bài tương tự trên thế giới |
| **Kết quả đầu ra** | **Bảng kê use case AI** (phòng ban × pain × tác động × dữ liệu × khả thi) → nuôi Phần A |
| **Điều kiện chuyển bước** | Đã gặp đủ người để thấy pattern, không chỉ một phía. ✗ Chưa đủ → gặp thêm leader / quan sát người dùng |
| **⚠ Lỗi thường gặp** | Chỉ ngồi phòng họp, không ra workflow thật; chỉ nghe một phòng ban. Lối tư duy chủ đạo: **L1 Decompose**. Mốc thời gian tham khảo: 1–2 tuần (startup) / 2–4 tuần (tập đoàn). |

> "Đi một vòng" nghĩa đen — ngồi với từng leader, không gửi khảo sát, không đọc báo cáo. Hỏi: "Đội anh đau ở đâu? Bao lâu một lần? Tốn bao nhiêu?" Kẻ thành bảng — đó là Bảng kê use case AI.

---

#### Bước 3 — Chọn Quick Win

| Trường | Nội dung |
|---|---|
| **Câu hỏi định hướng** (= câu tự kiểm 3) | "Bài nào chứng minh giá trị NHANH NHẤT?" |
| **Nhiệm vụ trọng tâm** | • Chấm theo 4 tiêu chí: Tác động × Khả thi × Ủng hộ × Tốc độ • Kiểm tra người bảo trợ: leader có *cam kết thời gian* không? • Kiểm tra chuyên gia/dữ liệu: có người soi + dữ liệu để thử không? • Chọn 1 bài — KHÔNG giải hết cùng lúc |
| **Kết quả đầu ra** | Bản chọn Quick Win: 1 bài + điểm + lý do + người bảo trợ + chuyên gia → nuôi Phần A |
| **Điều kiện chuyển bước** | Bài chọn có bằng chứng nhanh + có leader + có chuyên gia + có dữ liệu. ✗ Chưa → quay lại Bảng kê, chọn bài khác |
| **⚠ Lỗi thường gặp** | Chọn bài lớn nhất thay vì bài học được nhanh nhất. Ví dụ neo: Zillow chọn phạm vi/rủi ro quá cao cho lần đầu [Zillow Q3/2021 ✅]. Lối tư duy chủ đạo: **L2 Quick Win**. Mốc thời gian tham khảo: 1–2 ngày để ra quyết định. |

Khung chấm điểm 4 tiêu chí:

| Tiêu chí | Trọng số | 1 (Thấp) | 3 (Trung bình) | 5 (Cao) |
|---|---|---|---|---|
| Tác động | 30% | Ảnh hưởng < 5 người | 5–20 người | > 20 người hoặc > $5K/tháng |
| Khả thi | 25% | Không có dữ liệu, xây từ đầu | Có dữ liệu, cần tích hợp | Dữ liệu sẵn, có công cụ/API |
| Ủng hộ (của người giao/leader) | 25% | Không ai ủng hộ | Có người quan tâm | Leader cam kết thời gian + chuyên gia sẵn sàng |
| Tốc độ | 20% | > 2 tháng mới có demo | 2–4 tuần | < 2 tuần có demo |

> Quick Win không phải bài *dễ* — là bài sau 2–4 tuần có thể cho thấy một thứ chứng minh được. Bài cần 6 tháng mới ra kết quả thì không phải Quick Win, dù tác động lớn.

---

#### ◆ Problem Framing (đầu ra Kim cương 1)

Đây KHÔNG phải đề xuất giải pháp. Đây là tài liệu xác nhận: *"Tôi đã hiểu ĐÚNG vấn đề chưa?"* — đưa cho người giao đề để họ **nói "đúng" hoặc "sai, chưa đúng"**, không phải để đọc cho có.

**Chín mục bắt buộc:**

| # | Mục | Nội dung |
|---|---|---|
| 1 | Đề bài gốc | Họ nói gì nguyên văn — ai giao, lúc nào |
| 2 | Vấn đề khung lại | Vấn đề THẬT sau khi bóc tách (khác đề bài gốc thế nào?) |
| 3 | Workflow hiện tại | Quy trình đang chạy thế nào (vẽ sơ đồ, đánh dấu nút thắt) |
| 4 | Bằng chứng nỗi đau | SỐ LIỆU, không phải cảm tính |
| 5 | Người bị ảnh hưởng | Ai dùng, ai quyết, ai là chuyên gia |
| 6 | Ràng buộc | Dữ liệu, ngân sách, pháp lý, đội ngũ, thời gian |
| 7 | Quick Win đã chọn | Bài đã chọn + lý do |
| 8 | Câu hỏi còn ngỏ | Còn chưa biết gì? |
| 9 | Xác nhận | Người giao đề XÁC NHẬN |

> **Mốc (gate):** Người giao đề nói "Đúng, đây là vấn đề" → mới sang phase SOLUTION (Chọn cách làm). Chưa xác nhận → quay lại Bước 1–3. KHÔNG được đi tiếp.
>
> Mục 4 quan trọng nhất — "Nhiều người phàn nàn" không phải bằng chứng. "200 câu hỏi/tuần × 20 phút = 67 giờ/tuần" — *đó* là bằng chứng. Mục 8 cũng quan trọng: không có câu hỏi còn ngỏ = nguy hiểm (chứng tỏ chưa suy nghĩ đủ). Cách kiểm tra xác nhận thật: hỏi ngược "Anh/chị tóm tắt lại giúp em?" — xem họ nói có đúng không.

---

### SOLUTION: Chọn cách làm — Bước 4–5

Phase này trả lời: *Build, Boost, Buy hay Partner? Cần công cụ/API gì, nhà cung cấp nào, chi phí bao nhiêu? Bản thử cho thấy gì? Chuyên gia soi đầu ra có nghĩa không?*

Ai vào phòng (swimlane phase SOLUTION):

| Vai | Ai |
|---|---|
| Chủ trì | PM/PO + Tech Lead |
| Tham gia | Chuyên gia nghiệp vụ · kỹ sư · nhà cung cấp/công cụ · tài chính |
| Làm với ai | Chuyên gia: đầu ra đúng không · Kỹ sư: khả thi không · Nhà cung cấp: API/SLA/giới hạn · Tài chính: chi phí/khoảng ngân sách |
| Dữ liệu cần | Bảng giá · giới hạn API · dữ liệu có sẵn · bảo mật |
| AI hỗ trợ | Sinh mockup/bản thử API · so sánh nhà cung cấp · tạo bộ ca kiểm thử |
| Đầu ra | Solution Approach + Demo (Phần B + C) |
| Mốc qua phase | Người duyệt thấy đúng hướng; chuyên gia thấy đầu ra có nghĩa |
| Lỗi thường gặp | Xây trước khi hỏi mua; demo không có chuyên gia soi |

---

#### Bước 4 — Quyết Định Approach (Build/Buy/Boost/Partner)

| Trường | Nội dung |
|---|---|
| **Câu hỏi định hướng** (= câu tự kiểm 4) | "Build, Boost, Buy hay Partner?" |
| **Nhiệm vụ trọng tâm** | Đi theo cây quyết định (bên dưới) • Đối chiếu pattern: ai đã giải bài tương tự ở ngành khác? • Lập danh sách nguồn lực: công cụ/dữ liệu/chuyên gia/chi phí ước tính |
| **Kết quả đầu ra** | Solution Approach: quyết định + lý do + công cụ/nhà cung cấp/API + chi phí ước tính → nuôi Phần B |
| **Điều kiện chuyển bước** | Approach khả thi trong ngân sách/đội ngũ/thời gian. ✗ Chưa → nghiên cứu nhà cung cấp/công cụ hoặc đổi approach |
| **⚠ Lỗi thường gặp** | Muốn Build vì cái tôi. Phần lớn đội chỉ cần BOOST; rất ít cần Build. Ví dụ neo: GrabGPT dùng GPT API, không build mô hình ✅. Lối tư duy chủ đạo: **L5 Pattern Match**. Mốc thời gian tham khảo: 3–5 ngày nghiên cứu + 1–2 ngày quyết. |

Cây quyết định:

```
Bài toán này có phải LỢI THẾ CẠNH TRANH CỐT LÕI không?
    │
    ├── CÓ → Đội có kỹ sư AI mạnh?
    │        ├── CÓ → BUILD (mô hình riêng)
    │        └── KHÔNG → BOOST (tăng cường mô hình sẵn + dữ liệu riêng)
    │
    └── KHÔNG → AI chỉ là lớp tăng năng suất
             → Có công cụ/API sẵn phù hợp?
                  ├── CÓ → BUY (mua công cụ có sẵn)
                  └── KHÔNG → BOOST (mô hình sẵn + dữ liệu riêng)
    + Lựa chọn mở rộng: PARTNER — hợp tác với đội đã giải bài tương tự ("đi từ 5 lên, không từ 0")
```

> Phần lớn đội đang ở BOOST (80–90%). Buy để bắt đầu nhanh; Boost khi có dữ liệu riêng; Build chỉ khi AI là *lý do tồn tại* của sản phẩm. Khung "Build / Buy / Boost" lấy từ MIT Sloan Management Review (2024) — *"Buy, boost, or build? Choose your path to generative AI"*. "Partner" là lựa chọn mở rộng của AI20k.

**Đối chiếu pattern — cách làm:**

1. Bỏ hết phần nghiệp vụ → bài toán thực chất là gì? (lõi trừu tượng)
2. Tìm ai đã giải đúng lõi đó ở ngành khác?
3. Kết nối đội đó → "đi từ 5 lên, không từ 0"

---

#### Bước 5 — Demo / Mockup / Flow

| Trường | Nội dung |
|---|---|
| **Câu hỏi định hướng** (= câu tự kiểm 5) | "Người duyệt nhìn vào đâu để hình dung flow?" |
| **Nhiệm vụ trọng tâm** | • Chọn artifact nhẹ nhất: mockup / user flow / prompt flow / agent flow / mẫu input-output • Đưa người duyệt xem: "Đúng hướng này không?" • Chuyên gia soi đầu ra: sai ở đâu, thiếu gì? • Ghi: đã kiểm chứng được gì, chưa kiểm chứng gì |
| **Kết quả đầu ra** | **Artifact trực quan (BẮT BUỘC)** + Ghi chú kiểm chứng → nuôi Phần C. Demo chạy được = **điểm cộng**, không bắt buộc |
| **Điều kiện chuyển bước** | Người duyệt nhìn được flow & thấy đúng hướng; chuyên gia thấy đầu ra có nghĩa. ✗ Chưa → sửa artifact / quay Bước 4 |
| **⚠ Lỗi thường gặp** | Chỉ kể bằng miệng, không có gì để nhìn; hỏi "hay không?" thay vì "sai ở đâu?". Lối tư duy chủ đạo: **L4 Show → Validate**. Mốc thời gian tham khảo: vài ngày (startup) / dưới 1 tháng (tập đoàn). |

Các dạng bản thử theo mức độ:

| Dạng | Mất bao lâu | Phù hợp khi |
|---|---|---|
| Phác thảo + sơ đồ flow | 15–30 phút | Giải thích ý tưởng cho lãnh đạo |
| Mockup sinh bằng AI | 30–60 phút | Cần hình ảnh để chuyên gia soi |
| Người đóng vai AI (Wizard of Oz) | 1–2 ngày | Cần test với người dùng thật khi chưa có mô hình |
| Demo chạy được (code nhanh + API) | 2–5 ngày | Cần đầu ra thật để đánh giá chất lượng |

> Bản thử không phải sản phẩm — là công cụ để học và để người duyệt *nhìn thấy*. Điểm cốt lõi: đầu ra **bắt buộc** là một artifact trực quan; demo chạy được chỉ là *điểm cộng*. Khi đưa xem, hỏi "sai ở đâu / thiếu gì", không hỏi "hay không" — cả "đúng" lẫn "sai rõ ràng" đều là kết quả tốt vì học được.

---

### PILOT PLAN: Kế hoạch thử nghiệm — Bước 6–8

> **AI Pilot Plan là một cam kết hai chiều: tôi xin gì, tôi hứa gì, tôi đo gì, tôi dừng khi nào.** Đây là định nghĩa cốt lõi của cả phase.

Phase này trả lời: *Xin gì, hứa gì, bao lâu? Đo gì, ngưỡng bao nhiêu, dừng khi nào? Ai dùng, workflow nào đổi? Đủ bằng chứng để duyệt không?*

Ai vào phòng (swimlane phase PILOT PLAN):

| Vai | Ai |
|---|---|
| Chủ trì | PM/PO |
| Người duyệt | Cấp C / người nắm ngân sách |
| Tham gia | Tài chính · pháp lý · vận hành/adoption · người đo lường |
| Làm với ai | Tài chính: ngân sách/ROI · Pháp lý: rủi ro/hợp đồng nhà cung cấp · Vận hành: workflow/adoption · Người đo: mốc nền/ngưỡng |
| Dữ liệu cần | Khoảng ngân sách · ràng buộc pháp lý · mốc nền · SLA |
| AI hỗ trợ | Soạn nháp cam kết · ước tính ngân sách · liệt kê kịch bản rủi ro |
| Đầu ra | AI Pilot Plan + Trình bày (Phần D + E) |
| Mốc | Duyệt / Duyệt có điều kiện / Thiết kế lại / Tạm dừng / Dừng hẳn |
| Lỗi thường gặp | Xin quá nhiều, không có tiêu chí dừng, chỉ số không đo được |

---

#### Bước 6 — Pilot Plan (Lõi)

| Trường | Nội dung |
|---|---|
| **Câu hỏi định hướng** (= câu tự kiểm 6) | "Xin gì, hứa gì, bao lâu, ai tham gia?" |
| **Nhiệm vụ trọng tâm** | • Phạm vi pilot: ai dùng, bao lâu, workflow nào • Ngân sách: công cụ/API/nhà cung cấp + người + dữ liệu/gán nhãn • Bảng phân vai (RACI): PM, chuyên gia, kỹ sư, người sở hữu, người duyệt • Lịch: chuẩn bị → chạy → đánh giá (mỗi giai đoạn có mốc) • Adoption: ai dùng đầu, huấn luyện/hỗ trợ ra sao |
| **Kết quả đầu ra** | Bản nháp Pilot Plan: kế hoạch + ngân sách + người + dữ liệu + adoption + lời hứa → nuôi Phần D |
| **Điều kiện chuyển bước** | Kế hoạch thực tế; khoảng ngân sách ổn; chuyên gia/người giao đề đã xác nhận. ✗ Chưa → giảm phạm vi / quay Bước 5 |
| **⚠ Lỗi thường gặp** | Xin quá nhiều, không nói rõ đầu ra sau pilot. Ví dụ neo: GrabGPT xin nhỏ — API + 20% kỹ sư + tuyến riêng ✅. Lối tư duy chủ đạo: **L7 Adopt to Operate**. Mốc thời gian tham khảo: 3–5 ngày viết kế hoạch. |

> Ngân sách KHÔNG gộp một cục — tách từng hạng mục. Adoption là phần nhiều đội bỏ quên: công cụ AI không ai dùng = giá trị 0. Phân biệt với *project plan* thông thường: Pilot Plan là cam kết hai chiều — tôi xin gì *và* tôi hứa gì đổi lại.

---

#### Bước 7 — Đo Lường & Gate

| Trường | Nội dung |
|---|---|
| **Câu hỏi định hướng** (= câu tự kiểm 7) | "Đo gì, ngưỡng bao nhiêu, dừng khi nào?" |
| **Nhiệm vụ trọng tâm** | • Định nghĩa chỉ số SMART + mốc nền + ngưỡng • Chọn chỉ báo sớm để biết sớm • Viết tiêu chí dừng: nhẹ / vừa / nghiêm / nguy cấp • Chốt thu dữ liệu: ai đo, bằng gì, bao lâu/lần • Chốt điểm quyết định: tuần nào rà soát, ai quyết |
| **Kết quả đầu ra** | Khung đánh giá: chỉ số × mốc nền × ngưỡng × người đo × kích hoạt dừng → nuôi Phần D |
| **Điều kiện chuyển bước** | Chỉ số đo được thật; kích hoạt dừng cụ thể; người đo rõ. ✗ Chưa → định nghĩa lại chỉ số / giảm phạm vi pilot |
| **⚠ Lỗi thường gặp** | "Cải thiện chất lượng" mà không có mốc nền/ngưỡng → AI hỏng âm thầm. Ví dụ neo: Zillow thiếu mốc dừng ✅. Lối tư duy chủ đạo: **L6 Measure → Decide**. Mốc thời gian tham khảo: 1–2 ngày (song song Bước 6). |

Ví dụ tiêu chí dừng 4 cấp:

| Cấp | Tín hiệu | Ngưỡng | Hành động | Ai quyết |
|---|---|---|---|---|
| Nhẹ | Độ chính xác giảm | < 80% trong 1 tuần | Rà soát prompt/tài liệu | PM + Chuyên gia |
| Vừa | Adoption giảm | < 50 người dùng/ngày sau 4 tuần | Điều tra + thiết kế lại trải nghiệm | PM |
| Nghiêm | Rò rỉ dữ liệu / PII | 1 lần | DỪNG NGAY + rà soát | PM + Bảo mật |
| Nguy cấp | Vượt ngân sách | > $3K/tháng | Tạm dừng + tối ưu | PM + Tài chính |

> AI khác phần mềm truyền thống một điểm: nó *hỏng âm thầm*. Phần mềm sập → biết ngay; AI cho đầu ra sai → người dùng có thể không biết. Vì vậy cần chỉ báo sớm + giám sát chủ động — chỉ số không có mốc nền thì câu "tăng 30%" vô nghĩa (so với cái gì?).

---

#### Bước 8 — Trình Bày & Phê Duyệt

| Trường | Nội dung |
|---|---|
| **Câu hỏi định hướng** (= câu tự kiểm 8) | "Có đủ bằng chứng để duyệt, ràng buộc hay dừng?" |
| **Nhiệm vụ trọng tâm** | • Trình bày: Vấn đề → Approach → Demo → Kế hoạch → Lời xin • Nói rõ ngân sách, lịch, chỉ số, tiêu chí dừng • Chuẩn bị trả lời 3 câu phản biện: nguồn / giả định / điểm mù • Xin một quyết định cụ thể: duyệt / có điều kiện / thiết kế lại / dừng |
| **Kết quả đầu ra** | 5-slide Pitch + Nhật ký AI hỗ trợ → nuôi Phần E |
| **Điều kiện chuyển bước** | Người ra quyết định ra được quyết định sau buổi. ✗ Chưa → thiếu bằng chứng, quay Bước 6/7 |
| **⚠ Lỗi thường gặp** | Slide đẹp nhưng không trả lời được nguồn số liệu. Neo: McDonald's demo đẹp ROI mờ ⚠️ vs JPMorgan COiN bằng chứng rõ (360K giờ/năm ✅). Lối tư duy chủ đạo: **L3 Domain Expert + L6**. Mốc thời gian tham khảo: 1 buổi họp (30–60 phút). |

Ba câu phản biện mọi nhóm sẽ bị hỏi (chuẩn bị trước khi đứng lên):

1. "Số liệu / giả định này lấy ở đâu?"
2. "Nếu giả định quan trọng nhất sai thì sao?"
3. "Tình huống nào sẽ khiến bạn dừng pilot?"

> Nguyên lý: trình bày để người duyệt *có đủ thông tin ra quyết định*, không phải để họ *khen hay*. Không bao giờ nói "không có rủi ro" — hãy nói "rủi ro là X, cách giảm là Y".

---

## 5. Mẫu Đầu Ra — §A1 đến §A9 (dựa trên case GrabGPT)

> Đây là bộ mẫu đã điền đầy đủ trên một case thật (GrabGPT, Grab, Singapore, 2023 — ✅ Grab Engineering Blog) để học viên hình dung "xong thì trông thế nào". Các con số 67h/tuần và $15K/tháng là 🧮 ước tính để giảng, KHÔNG phải Grab công bố.

### Ánh xạ ba cách gọi (một bộ duy nhất)

Khung phương pháp A–E (để dạy) ↔ A3 Working Canvas (bản nộp ở Lab) ↔ §A1–A9 (mẫu trong sổ tay):

| Phần (phương pháp) | A3 Working Canvas (nộp) | §A1–A9 (mẫu) | Phase |
|---|---|---|---|
| **A. Hồ sơ Vấn đề** | Track & Big Ask · Tool Breakdown · Quick Win · Problem Framing | §A1+A2+A3+A4 | FRAME |
| **B. Cách làm** | Solution Approach (đã gồm Data & Expert) | §A5 | SOLUTION |
| **C. Demo/Mockup/Flow** (artifact trực quan BẮT BUỘC) | Demo/Mockup/Flow | §A6 | SOLUTION |
| **D. AI Pilot Plan** | AI Pilot Plan | §A7 + §A8 | PILOT PLAN |
| **E. 5-slide Pitch** | 5-slide Pitch (+ Nhật ký AI hỗ trợ) | §A9 | PILOT PLAN |

### §A1 — Đề Bài Thô (đầu ra Bước 1)

**Mục đích, người nhận, câu hỏi nó trả lời:**

| | |
|---|---|
| **Mục tiêu** | Ghi lại CHÍNH XÁC những gì người giao đề nói — chưa diễn giải, chưa giải. Tạo mốc đối chiếu sau này: "họ muốn gì" vs "vấn đề thật". |
| **Đưa cho ai** | Chính mình (PM/PO) + đội nội bộ. CHƯA đưa người giao đề (đây là ghi chú thô). |
| **Trả lời câu gì** | (1) Họ nói gì nguyên văn? (2) Ai giao đề? (3) Họ kỳ vọng gì? (4) Ràng buộc gì đã biết? (5) Dạng đề nào (ⓐ/ⓑ/ⓒ)? |
| **Dùng để làm gì** | Input cho Bước 2 (bóc tách). Xong hành trình thì quay lại đối chiếu: "đề bài ban đầu vs vấn đề thật — khác thế nào?" |

**Quy trình tạo ra (từng bước + phản biện):**

| Bước | Làm gì | Câu hỏi phải trả lời | Phản biện |
|---|---|---|---|
| 1 | Nghe — ghi nguyên văn | "Họ nói CHÍNH XÁC là gì?" | Mình có đang diễn giải theo ý mình không? |
| 2 | Hỏi lại: "Tại sao bây giờ?" | "Chuyện gì vừa xảy ra khiến họ muốn làm việc này?" | Họ muốn AI vì THỰC SỰ cần, hay vì trend/CEO đọc báo? |
| 3 | Hỏi: "Thành công là gì?" | "3 tháng sau nếu đạt, họ muốn thấy gì?" | Họ trả lời được cụ thể không? Nếu không → đề bài còn mơ. |
| 4 | Xác định dạng (ⓐ/ⓑ/ⓒ) | "Đề bài có sẵn hay phải tìm?" | Nếu dạng ⓐ — KHÔNG vội nhảy vào giải pháp. Phải khảo sát trước. |
| 5 | Ghi ràng buộc | "Không được làm gì? Không có gì?" | Ràng buộc này có phải "tưởng tượng" không? Ai nói? Đã kiểm chưa? |

Mẫu đã điền (GrabGPT):

```
ĐỀ BÀI THÔ — Grab Internal AI, 3/2023
─────────────────────────────────────────
Người giao:      Lãnh đạo (mandate cấp CEO)
Nguyên văn:      "Explore LLMs — tìm cách ứng dụng Large Language Models
                  vào vận hành nội bộ Grab."
Kỳ vọng:         Không rõ. "Tìm ra cách ứng dụng" — không chỉ rõ chỉ số.
Dạng đề:         ⓐ — "AI đi đâu?" (rất mơ hồ)
Ràng buộc:       - Dữ liệu không ra ngoài (Grab cận lĩnh vực tài chính)
                 - Chưa có ngân sách riêng
                 - Không có đội AI riêng cho công cụ nội bộ
                 - Muốn thấy kết quả "sớm"
Đúng người?      Có — mandate từ trên; đội ML Platform là chủ tự nhiên.
Tại sao bây giờ? ChatGPT vừa ra (11/2022). Lãnh đạo thấy tiềm năng.
                 CẢNH BÁO: có thể là "FOMO" hơn là "nỗi đau thật".
```

Tư duy phản biện sau Bước 1:
- "Explore LLMs" không phải đề bài — đây là *hướng đi*, chưa có vấn đề cụ thể.
- Dạng ⓐ nguy hiểm nhất: không có phạm vi → dễ lan man.
- FOMO vs Nỗi đau thật: phải kiểm chứng bằng Bước 2 — đi khảo sát xem có pain thật không.

### §A2 — Bảng Kê Use Case AI (đầu ra Bước 2)

**Mục đích, người nhận, câu hỏi nó trả lời:**

| | |
|---|---|
| **Mục tiêu** | Nhìn TOÀN CẢNH tổ chức: phòng nào đau gì, tần suất bao nhiêu, tác động thật bao nhiêu, dữ liệu có sẵn không, leader có ủng hộ không. |
| **Đưa cho ai** | PM/PO ra quyết định Bước 3. Có thể đưa lãnh đạo để đồng thuận. |
| **Trả lời câu gì** | (1) Toàn công ty có pain gì? (2) Pain nào lớn nhất (số liệu)? (3) Dữ liệu ở đâu? (4) Ai ủng hộ, ai không? (5) Pattern gì nổi lên? |
| **Dùng để làm gì** | So sánh các option để chọn Quick Win. Không phải "chọn cái hay nhất" mà "chọn cái CHỨNG MINH ĐƯỢC nhanh nhất". |

**Quy trình tạo ra (từng bước + phản biện):**

| Bước | Làm gì | Câu hỏi phải trả lời | Phản biện |
|---|---|---|---|
| 1 | Gặp TỪNG leader (không chỉ 1) | "Phòng ban họ đau THẬT SỰ ở đâu?" | Mình có chỉ nghe 1 phía không? Leader nói có khớp user thật? |
| 2 | Quan sát (không chỉ phỏng vấn) | "Workflow thực tế diễn ra thế nào?" | Người ta nói đau ≠ đau thật. Đi ngồi cùng họ 1 buổi xem. |
| 3 | Đo lường (không chỉ cảm tính) | "Pain này lớn BAO NHIÊU? Tính bằng gì?" | "Nhiều" là bao nhiêu? Có số liệu chưa? Ai đo? |
| 4 | Kẻ bảng | "Ma trận này CÓ THIẾU phòng ban nào không?" | Mình có bị bias chọn phòng ban quen thuộc? |
| 5 | Tìm pattern | "Phòng ban nào có pain GIỐNG NHAU?" | Trùng pain = cơ hội làm 1 tool phục vụ nhiều đội? |

Mẫu đã điền (GrabGPT):

| Phòng ban | Số người | Pain chính | Tần suất | Tác động | Dữ liệu | Leader | Khả thi |
|---|---|---|---|---|---|---|---|
| ML Platform | 50 | Trả lời Slack lặp lại (60% lặp) | Hằng ngày, 30–40 Q/ngày | 🧮 67h/tuần = 3–4h/ngày [ước tính để giảng] | Docs+Slack (lỗi thời) | CÓ | CAO |
| Data Platform | 30 | Yêu cầu dữ liệu ad-hoc | Hằng tuần | 2–3 ngày/yêu cầu | Query logs (hạn chế) | Vừa | TB |
| Engineering (toàn bộ) | 500+ | Tìm docs, setup, cấu hình (bị block đợi support) | Hằng ngày | 2–4h block/lần | Rải rác | — (là người dùng) | CAO |
| Ops (toàn Grab) | 200+ | Xử lý phản hồi tài xế | Hằng ngày | Lớn (lõi kinh doanh) | Có | Chưa rõ | TB |

> **Pattern:** Pain chung = "tìm thông tin đã có nhưng không ai tìm thấy" (truy xuất tri thức — knowledge retrieval) → có thể giải bằng MỘT kiến trúc (RAG) cho nhiều use case.

Tư duy phản biện sau Bước 2:
- Mình đã gặp ĐỦ người chưa? Hay chỉ ngồi trong phòng họp?
- Số liệu "67h/tuần" — ai đo? Chính xác không? Hay chỉ ước lượng?
- "Leader ủng hộ" — ủng hộ bằng LỜI hay bằng THỜI GIAN (cam kết tham gia pilot)?
- Có phòng ban nào mình CHƯA gặp mà có thể đau lớn hơn?

### §A3 — Bản Chọn Quick Win (đầu ra Bước 3)

**Mục đích, người nhận, câu hỏi nó trả lời:**

| | |
|---|---|
| **Mục tiêu** | Chọn ĐÚNG 1 bài làm trước — không phải bài "hay nhất" mà bài "chứng minh giá trị nhanh nhất với rủi ro thấp nhất". |
| **Đưa cho ai** | Lãnh đạo (đồng thuận), Đội (tập trung), Chuyên gia nghiệp vụ (cam kết thời gian). |
| **Trả lời câu gì** | (1) Làm bài nào TRƯỚC? (2) TẠI SAO bài này mà không phải bài khác? (3) Ai giúp triển khai? (4) Cho thấy gì trong bao lâu? |
| **Dùng để làm gì** | Khóa phạm vi — từ "10 bài toán" còn 1. Bắt đầu Kim cương 1 hội tụ. Mở khóa bước tiếp (Problem Framing). |

**Quy trình tạo ra (từng bước + phản biện):**

| Bước | Làm gì | Câu hỏi phải trả lời | Phản biện |
|---|---|---|---|
| 1 | Chấm điểm từng option (4 tiêu chí) | "Điểm có CÔNG BẰNG không? Hay mình bias?" | Mình có đang cho điểm cao bài mình THÍCH thay vì bài ĐÚNG? |
| 2 | Kiểm: leader cam kết? | "Leader NÓI 'OK' hay ĐÃ XÁC NHẬN thời gian?" | "Ủng hộ" miệng ≠ cam kết. Chưa có cam kết thời gian = rủi ro. |
| 3 | Kiểm: chuyên gia có rảnh? | "Ai sẽ soi đầu ra? Họ có THỜI GIAN không?" | Không có chuyên gia → build trong chân không → rủi ro cao. |
| 4 | Kiểm: dữ liệu có? | "Dữ liệu CÓ THẬT không? Chất lượng thế nào?" | "Có dữ liệu" thường nghĩa là "có nhưng bẩn, lỗi thời, hạn chế". |
| 5 | Giải thích: tại sao KHÔNG chọn bài khác | "Bài bị loại — lý do gì?" | Nếu không giải thích được tại sao KHÔNG → chưa đủ chắc để CHỌN. |

Mẫu đã điền (GrabGPT):

```
CHẤM ĐIỂM:
| Bài toán              | Tác động | Khả thi | Leader | Tốc độ | TỔNG | Hạng |
|                       | (30%)    | (25%)   | (25%)  | (20%)  |      |      |
| Q&A bot ML Platform   |   4      |   5     |   5    |   5    | 4.7  |  1   |
| Data: NL → SQL        |   3      |   3     |   3    |   3    | 3.0  |  3   |
| Ops: định tuyến phản  |   5      |   3     |   2    |   2    | 3.2  |  2   |
| hồi                   |          |         |        |        |      |      |

CHỌN: Q&A bot ML Platform
TẠI SAO BÀI NÀY:
  ✓ Người dùng sẵn: 500 kỹ sư quen công cụ, không cần huấn luyện
  ✓ Dữ liệu có: docs + lịch sử Slack (dù lỗi thời — vẫn dùng được cho v1)
  ✓ Leader cam kết: Platform Lead muốn giảm 40% tải support
  ✓ Demo nhanh: RAG + giao diện chat = bản thử < 1 tuần
  ✓ Rủi ro thấp: công cụ nội bộ, sai thì kỹ sư biết → không mất khách
TẠI SAO KHÔNG CHỌN BÀI KHÁC:
  ✗ NL→SQL: dữ liệu hạn chế, lo bảo mật, chưa có leader đẩy
  ✗ Ops phản hồi: tác động lớn nhưng KHÔNG có leader ủng hộ + rủi ro cao (chạm khách)
NGƯỜI BẢO TRỢ: Platform Team Lead (đã xác nhận dự rà soát hằng tuần)
CHUYÊN GIA: 3 kỹ sư platform cấp cao (đã xác nhận 2h/tuần)
```

Tư duy phản biện sau Bước 3:
- "Quick Win" có phải "bài dễ" không? KHÔNG — là bài có bằng chứng nhanh nhất.
- Mình chọn bài này vì nó ĐÚNG hay vì nó QUEN THUỘC với mình?
- Nếu bài này hỏng — hậu quả gì? Có mất uy tín để chọn bài tiếp không?
- Leader "xác nhận" — bằng email/biên bản hay chỉ nói miệng? Ghi lại.

### §A4 — Problem Framing (đầu ra Kim cương 1)

**Mục đích, người nhận, câu hỏi nó trả lời:**

| | |
|---|---|
| **Mục tiêu** | Xác nhận "tôi đã hiểu ĐÚNG vấn đề chưa?" TRƯỚC khi thiết kế giải pháp. Đây là mốc — không qua thì không đi tiếp. |
| **Đưa cho ai** | Người giao đề — để họ XÁC NHẬN. Không phải để họ đọc — mà để họ NÓI "đúng" hoặc "sai, chưa đúng". |
| **Trả lời câu gì** | (1) Vấn đề THẬT là gì (không phải đề bài ban đầu)? (2) Ai bị ảnh hưởng? (3) Đau bao nhiêu? (4) Ràng buộc gì? (5) Đã chọn bài nào? |
| **Dùng để làm gì** | INPUT cho Kim cương 2. Mọi quyết định sau này (approach, ngân sách, chỉ số) đều DỰA TRÊN tài liệu này. Nếu sai → toàn bộ plan sai. |

**Quy trình tạo ra (từng bước + phản biện):**

| Bước | Làm gì | Câu hỏi phải trả lời | Phản biện |
|---|---|---|---|
| 1 | Đối chiếu Đề bài gốc vs Khung lại | "Họ nói gì vs vấn đề thật — KHÁC thế nào?" | Nếu giống hệt → mình chưa đào đủ sâu. |
| 2 | Vẽ workflow hiện tại | "Mình có THỰC SỰ hiểu quy trình hiện tại?" | Vẽ được sơ đồ không? Nếu không → chưa hiểu đủ. |
| 3 | Ghi bằng chứng nỗi đau | "Có SỐ LIỆU không? Hay chỉ cảm tính?" | "Nhiều người phàn nàn" ≠ bằng chứng. Cần con số. |
| 4 | Liệt kê câu hỏi còn ngỏ | "Còn gì CHƯA BIẾT mà cần biết trước khi làm?" | Không có câu hỏi còn ngỏ = nguy hiểm (chưa suy nghĩ đủ). |
| 5 | Trình cho người giao đề | "Họ THỰC SỰ hiểu và đồng ý? Hay chỉ gật cho xong?" | Hỏi ngược: "Anh/chị tóm tắt lại giúp em?" — xem họ nói đúng không. |

Mẫu đã điền (GrabGPT):

```
1. ĐỀ BÀI GỐC (nguyên văn): "Explore LLMs — tìm cách ứng dụng vào vận hành
   nội bộ Grab." Người giao: Lãnh đạo. Thời điểm: 3/2023.
2. VẤN ĐỀ KHUNG LẠI (sau khi khảo sát): Đội ML Platform (50+ kỹ sư) mất
   ~40% thời gian trả lời câu hỏi lặp lại trên Slack. 500+ kỹ sư bị block
   2–4h mỗi lần cần support. Vấn đề KHÔNG PHẢI "cần AI" — mà là "tri thức
   không tra cứu được".
3. WORKFLOW HIỆN TẠI (sơ đồ): Kỹ sư gặp vấn đề → tìm docs (thất bại — lỗi
   thời, rải rác) → post Slack #ml-platform-support → đợi 10–30 phút (đơn
   giản) hoặc 1–4h (phức tạp) → kỹ sư platform trả lời (mất thời gian build).
   NÚT THẮT: bước "tìm docs" hỏng → mọi thứ dồn lên Slack.
4. BẰNG CHỨNG NỖI ĐAU (số liệu):
   • 200 câu hỏi/tuần (đo từ Slack analytics) ✅
   • 60% lặp lại (phân loại thủ công 1 tuần) ✅
   • 🧮 67h/tuần đội mất cho support (8 người × ~8h/tuần) [ước tính để giảng]
   • Kỹ sư bị block trung bình 2–4h/lần (khảo sát 50 người) ✅
   • 🧮 Chi phí ~$15K/tháng (chi phí cơ hội của thời gian kỹ sư)
     [ước tính để giảng — không phải Grab công bố]
5. NGƯỜI BỊ ẢNH HƯỞNG: 500+ kỹ sư (hằng ngày bị block) · 8 kỹ sư platform
   (40% thời gian bị ẩn) · toàn org engineering (giao tính năng chậm) ·
   Platform Team Lead (người quyết) · 3 kỹ sư cấp cao (chuyên gia)
6. RÀNG BUỘC: tuyến riêng bắt buộc (cận tài chính) · ngân sách chưa chính
   thức — mức side project · "nhanh" — không chờ 6 tháng · không có đội AI
   riêng · cần audit trail mọi interaction
7. QUICK WIN ĐÃ CHỌN: Chatbot Q&A cho kỹ sư ML Platform. Lý do: người dùng
   sẵn + dữ liệu có + leader cam kết + demo nhanh + rủi ro thấp.
8. CÂU HỎI CÒN NGỎ:
   • LLM nào? (GPT-3.5 vs 4 vs self-hosted)
   • RAG + docs lỗi thời → độ chính xác bao nhiêu?
   • Kỹ sư có tin bot không?
   • "Chất lượng trả lời" đo bằng gì?
9. XÁC NHẬN: Platform Team Lead: "Đúng, đây là vấn đề lớn nhất của đội tôi."
   Phương pháp: trình bày 15 phút + hỏi ngược "Anh tóm tắt lại?"
   Kết quả: Đã xác nhận ✓ — hiểu đúng.
```

Tư duy phản biện sau Problem Framing:
- "Vấn đề thật" mình viết — có THẬT là vấn đề không? Hay là TRIỆU CHỨNG?
- Bằng chứng đủ MẠNH để thuyết phục người khác chưa? Tài chính sẽ hỏi "$15K/tháng — tính thế nào?".
- Câu hỏi còn ngỏ — mình có THÀNH THẬT không? Hay giấu những thứ chưa biết?
- Người giao đề "xác nhận" vì HIỂU hay vì MUỐN mình đi làm cho nhanh?

### §A5 — Solution Approach (đầu ra Bước 4)

**Mục đích, người nhận, câu hỏi nó trả lời:**

| | |
|---|---|
| **Mục tiêu** | Quyết định CÁCH TIẾP CẬN (Build/Buy/Boost/Partner) và xác định nguồn lực cần thiết. Không phải chọn công cụ — mà chọn CHIẾN LƯỢC. |
| **Đưa cho ai** | Đội (biết hướng làm), Tech Lead (kiểm khả thi), Tài chính (biết khoảng chi phí). |
| **Trả lời câu gì** | (1) Build/Buy/Boost/Partner? TẠI SAO? (2) Đối chiếu pattern: ai đã giải bài này? (3) Cần gì để bắt đầu (công cụ, dữ liệu, chuyên gia, ngân sách)? (4) Rủi ro gì? |
| **Dùng để làm gì** | Định hướng cho bản thử (Bước 5). Nếu approach sai từ đầu → bản thử sai → toàn bộ sai. |

**Quy trình tạo ra (từng bước + phản biện):**

| Bước | Làm gì | Câu hỏi phải trả lời | Phản biện |
|---|---|---|---|
| 1 | Trả lời: AI là lợi thế cạnh tranh hay lớp tăng năng suất? | "Bỏ AI ra — sản phẩm còn TỒN TẠI không?" | Hầu hết đội nghĩ mình cần Build — thực tế 80–90% là Boost/Buy. |
| 2 | Đối chiếu pattern | "Bài này GIỐNG bài gì đã có người giải?" | Nếu không tìm được pattern → bài có thể CHƯA RÕ, quay lại Kim cương 1. |
| 3 | Nghiên cứu nhà cung cấp/công cụ | "Có gì SẴN dùng được? Chi phí bao nhiêu?" | "Tự build" khi có công cụ $20/người/tháng = phí thời gian engineering. |
| 4 | Lập danh sách nguồn lực | "Đội có gì? THIẾU gì?" | Trung thực: đội có kỹ sư AI không? Dữ liệu có sạch không? |
| 5 | Ước tính chi phí + thời gian | "Mất bao lâu? Bao nhiêu tiền?" | Nhân ×2–3 cho mọi ước tính. Kỹ sư luôn lạc quan quá. |

Mẫu đã điền (GrabGPT):

```
QUYẾT ĐỊNH: BOOST
  Dùng LLM API có sẵn (OpenAI GPT) + docs nội bộ làm cơ sở tri thức (RAG).
  Không build mô hình riêng. Không mua công cụ có sẵn.
TẠI SAO BOOST (không phải Build/Buy):
  ├─ AI có phải lợi thế cạnh tranh cốt lõi của Grab?
  │   KHÔNG — lõi của Grab là logistics + payments.
  │   → Không cần Build mô hình riêng.
  ├─ Đội có kỹ sư nghiên cứu AI?
  │   KHÔNG cho công cụ nội bộ — có infra (Catwalk) nhưng không có research.
  │   → Xác nhận: KHÔNG Build.
  ├─ Có công cụ có sẵn phù hợp?
  │   2023: chưa có công cụ enterprise search tốt (Glean mới, chưa chín).
  │   Chi phí Buy ~$15–25/người × 500 = $7,500–12,500/tháng vs API ~$500–1K.
  │   → Buy quá đắt cho giai đoạn pilot. BOOST rẻ hơn và linh hoạt hơn.
  └─ BOOST: mô hình có sẵn + dữ liệu riêng (docs nội bộ).
      "Đi từ 5 lên": Catwalk (hạ tầng phục vụ mô hình) đã có → chỉ cần
      thêm lớp RAG.
ĐỐI CHIẾU PATTERN:
  Bài toán: Q&A tri thức nội bộ (chữ vào → câu trả lời ra)
  Giống: Stripe LLM Explorer, Shopify Sidekick, Notion AI Q&A
  Lõi: LLM + RAG + phân quyền truy cập + giao diện chat
  Khác biệt: Grab cần tuyến riêng (tuân thủ)
NGUỒN LỰC CẦN:
  | Mục      | Có sẵn                    | Cần thêm              |
  | Hạ tầng  | Catwalk (phục vụ mô hình) | Pipeline RAG          |
  | Dữ liệu  | Docs, Confluence, Slack   | Làm sạch + index      |
  | Đội      | 1 kỹ sư platform          | Không cần thêm        |
  | Ngân sách| Mức side project          | ~$1K/tháng API        |
  | Chuyên gia| 3 kỹ sư cấp cao          | 2h/tuần soi           |
  | Đăng nhập| Google login (có sẵn)     | Không cần thêm        |
RỦI RO:
  • Docs lỗi thời 30% → RAG trả lời sai → mất niềm tin
  • Tuyến riêng chưa test với LLM API → có thể trễ
  • "Side project" = không có ưu tiên chính thức → có thể bị hạ ưu tiên
```

Tư duy phản biện sau Bước 4:
- Mình chọn Boost vì ĐÚNG hay vì DỄ (ít việc hơn)?
- "Đi từ 5 lên" — hạ tầng có sẵn có THỰC SỰ fit không? Hay phải hack?
- Rủi ro "docs lỗi thời" — ai sẽ cập nhật? Không ai → không phải rủi ro mà là CHẮC CHẮN XẢY RA.
- Nếu pilot thành công và mở rộng 10×, approach này còn vững không?

### §A6 — Demo Concept (đầu ra Bước 5)

**Mục đích, người nhận, câu hỏi nó trả lời:**

| | |
|---|---|
| **Mục tiêu** | CHO XEM được gì đó — dù thô — để người duyệt và chuyên gia nói "đúng hướng" HOẶC "sai, đổi đi". Bản thử là công cụ HIỂU ĐỀ, không phải sản phẩm. |
| **Đưa cho ai** | Người duyệt (xác nhận hướng), Chuyên gia nghiệp vụ (soi chất lượng đầu ra), Đội (thống nhất kỹ thuật). |
| **Trả lời câu gì** | (1) Người dùng có HIỂU cách dùng không? (2) Đầu ra có ĐÚNG đủ để dùng không? (3) Hướng có ĐÚNG không (trước khi đầu tư thêm)? |
| **Dùng để làm gì** | Mốc trước khi viết AI Pilot Plan. Demo hỏng → đổi approach (quay Bước 4). Demo qua → có đủ tự tin để xin nguồn lực. |

**Quy trình tạo ra (từng bước + phản biện):**

| Bước | Làm gì | Câu hỏi phải trả lời | Phản biện |
|---|---|---|---|
| 1 | Làm bản thử (30' – 1 ngày) | "Cái này CHẠY ĐƯỢC chưa? Đủ để show?" | Không cần đẹp — cần CHẠY. Đẹp mà không kiểm chứng = phí. |
| 2 | Đưa người duyệt xem | "Họ nói 'đúng cái này' hay 'hmm thú vị'?" | "Thú vị" ≠ duyệt. Cần phản ứng CỤ THỂ. |
| 3 | Chuyên gia soi đầu ra | "Đầu ra có ĐÚNG về mặt nghiệp vụ?" | PM không đủ chuyên môn để phán — PHẢI có chuyên gia. |
| 4 | Sửa theo phản hồi | "Phản hồi là gì? Sửa gì?" | Sửa ≠ làm đẹp. Sửa = sửa SAI. |
| 5 | Ghi: gì đã kiểm chứng, gì chưa | "Phần nào ĐÃ CHẮC, phần nào CÒN NGỎ?" | Không phải "bản thử thành công" mà là "học được gì từ bản thử". |

Mẫu đã điền (GrabGPT):

```
BẢN THỬ (2 ngày cuối tuần):
  • Backend: Catwalk (hạ tầng phục vụ mô hình có sẵn) → OpenAI GPT API (tuyến riêng)
  • Tri thức: index docs nội bộ (Confluence + markdown) vào vector store
  • Đăng nhập: Google login (có sẵn) · Giao diện: chat đơn giản (web)
  • Triển khai: URL nội bộ, mọi kỹ sư có email Grab truy cập được
ĐƯA NGƯỜI DUYỆT XEM:
  • Không "launch" — chỉ share link Slack: "Thử cái này đi"
  • Kết quả: 300 người dùng ngày 1, 600 ngày 2 (TỰ NHIÊN — không marketing) ✅
  • Phản ứng: "Đây là thứ tôi cần!" (nhiều kỹ sư)
  • Kiểm chứng: Hướng ĐÚNG — người ta MUỐN dùng.
CHUYÊN GIA SOI:
  • 3 kỹ sư cấp cao soi 50 mẫu đầu ra
  • Kết quả: 🧮 ~70% dùng được, 20% một phần, 10% sai [ước tính để giảng]
  • Nhận xét: sai nhiều ở docs lỗi thời (không phải mô hình sai)
  • Hành động: cần cập nhật docs trước, không phải đổi mô hình
ĐÃ KIỂM CHỨNG:
  ✓ Hướng đúng (người ta muốn dùng, adoption tự nhiên)
  ✓ Kỹ thuật khả thi (Catwalk + RAG chạy được)
  ✓ Người dùng không cần huấn luyện (giao diện chat quen thuộc)
CHƯA KIỂM CHỨNG:
  ? Độ chính xác khi mở rộng (50 mẫu chưa đủ)
  ? Dùng dài hạn (2 ngày ≠ 2 tháng)
  ? Docs lỗi thời → maintain ra sao?
  ? Chi phí khi 500+ người dùng hằng ngày
QUYẾT ĐỊNH: Hướng đã xác nhận → sang AI Pilot Plan.
```

Tư duy phản biện sau Bước 5:
- 300 người dùng ngày 1 — họ dùng vì CẦN hay vì MỚI LẠ (hiệu ứng tò mò)?
- 🧮 70% dùng được [ước tính để giảng] — đủ tốt để DÙNG LÂU DÀI chưa? Hay chỉ OK cho thử?
- "Adoption tự nhiên" có phải bằng chứng không? Hay chỉ là sự tò mò?
- Demo đẹp → người ta khen → mình tự tin quá → không thấy rủi ro?

### §A7 — AI Pilot Plan (đầu ra Bước 6 — Kim cương 2)

> **AI Pilot Plan là cam kết hai chiều: tôi xin gì, tôi hứa gì, tôi đo gì, tôi dừng khi nào.**

**Mục đích, người nhận, câu hỏi nó trả lời:**

| | |
|---|---|
| **Mục tiêu** | "Hợp đồng hai chiều": tôi XIN gì (ngân sách, người, thời gian) — tôi HỨA gì (đầu ra, bằng chứng) — tôi ĐO gì (chỉ số) — tôi DỪNG khi nào (exit criteria). Không phải đề xuất xin tiền — mà là CAM KẾT có trách nhiệm giải trình. |
| **Đưa cho ai** | Người ra quyết định (CEO/VP/Tài chính) — để DUYỆT hoặc TỪ CHỐI. Không phải "trình bày cho đẹp" mà là "đủ thông tin để ra quyết định". |
| **Trả lời câu gì** | (1) Xin gì? (2) Hứa gì đổi lại? (3) Bao lâu? (4) Bao nhiêu tiền? (5) Biết thành/bại thế nào? (6) Dừng khi nào? (7) Ai làm gì? |
| **Dùng để làm gì** | Phê duyệt để bắt đầu pilot. Sau pilot: đối chiếu KẾT QUẢ vs PLAN — bằng chứng cho quyết định Mở rộng/Đổi hướng/Dừng. |

**Quy trình tạo ra (từng bước + phản biện):**

| Bước | Làm gì | Câu hỏi phải trả lời | Phản biện |
|---|---|---|---|
| 1 | Tóm tắt vấn đề (từ Problem Framing) | "1 câu: vấn đề là gì?" | Nếu không tóm tắt được 1 câu → chưa hiểu đủ. |
| 2 | Ghi approach + lý do | "TẠI SAO cách này mà không phải cách khác?" | Có plan B không? Nếu approach này hỏng? |
| 3 | Bóc tách ngân sách | "TỪNG HẠNG MỤC mất bao nhiêu?" | Mình có đang che giấu chi phí (thời gian kỹ sư, chi phí cơ hội)? |
| 4 | Chỉ số + ngưỡng | "THÀNH CÔNG là gì — CỤ THỂ con số?" | Chỉ số có ĐO ĐƯỢC không? Ai đo? Bao lâu/lần? Mốc nền là gì? |
| 5 | Tiêu chí dừng | "DỪNG khi nào? Tín hiệu gì?" | Không có exit criteria = không bao giờ biết lúc nào nên dừng. |
| 6 | Kế hoạch adoption | "AI DÙNG? Workflow đổi gì? Ai huấn luyện?" | Công cụ không ai dùng = giá trị 0. Adoption QUAN TRỌNG HƠN độ chính xác. |
| 7 | Lời hứa đầu ra | "SAU PILOT giao gì? Bằng chứng gì?" | Hứa THỰC TẾ — không hứa quá để được duyệt. |

Mẫu đã điền (GrabGPT):

```
1. TÓM TẮT VẤN ĐỀ (1 câu): 500+ kỹ sư bị block 2–4h/lần vì tri thức không
   tra cứu được; đội Platform mất 🧮 67h/tuần [ước tính để giảng] trả lời
   Slack thay vì làm tính năng.
2. CÁCH LÀM: BOOST — LLM API (OpenAI GPT) + RAG (docs nội bộ) + tuyến riêng.
   Lý do: không cần Build (AI không phải core), Buy quá đắt cho pilot.
   Pattern: giống công cụ tri thức nội bộ của Stripe/Shopify.
3. KẾT QUẢ DEMO: weekend hack → 300 người ngày 1 (organic) ✅. Chuyên gia
   soi: 🧮 70% dùng được [ước tính để giảng]. Người duyệt: "Đây là thứ tôi
   cần." Hướng đã xác nhận.
4. KẾ HOẠCH CHUYÊN GIA SOI:
   | Ai            | Soi gì             | Bao nhiêu | Tiêu chí        | Khi nào   |
   | 3 kỹ sư cao   | 50 mẫu/tuần        | 30 phút   | ≥85% "dùng được"| Thứ 6     |
   | Platform Lead | Hướng tổng         | 15 phút   | Khớp nhu cầu đội| Mỗi 2 tuần|
5. PHẠM VI PILOT:
   Giai đoạn 1 (tuần 1–2): 100 kỹ sư từ 3 đội dùng ML platform nhiều nhất
   Giai đoạn 2 (tuần 3–6): mở rộng 500+ kỹ sư
   Giai đoạn 3 (tuần 7–8): đánh giá + quyết định
6. PHÂN VAI (RACI):
   | Vai trò       | Người               | R | A | C | I |
   | PM/chủ        | Kỹ sư khởi xướng    | ✓ |   |   |   |
   | Backend       | 1 kỹ sư platform 20%|   | ✓ |   |   |
   | Chuyên gia    | 3 kỹ sư cao 2h/tuần |   |   | ✓ |   |
   | Người giao đề | Platform Team Lead  |   |   |   | ✓ |
7. NGÂN SÁCH:
   | Hạng mục      | $/tháng | Ghi chú                   |
   | OpenAI API    | $500–1K | Tuyến riêng, theo lượng dùng|
   | Hạ tầng       | $0      | Catwalk đã có             |
   | Thời gian kỹ sư| $0 thêm| 20% người đã có           |
   | TỔNG          | ~$1K/mo | Ngân sách side project    |
8. LỊCH:
   | Giai đoạn | Tuần | Đầu ra                | Mốc            |
   | Setup     | 1–2  | Deploy + index docs   | Công cụ chạy?  |
   | Chạy      | 3–6  | Dữ liệu dùng + sửa lặp| DAU > 100?     |
   | Đánh giá  | 7–8  | Báo cáo bằng chứng    | Chỉ số đạt?    |
9. CHỈ SỐ THÀNH CÔNG:
   | Chỉ số          | Mốc nền   | Mục tiêu      | Cách đo      | Ai đo     |
   | Người dùng/ngày | 0         | ≥100 (tuần 4) | Analytics    | Tự động   |
   | Giảm support    | 200 Q/tuần| ≤140 (−30%)   | Đếm Slack    | Hằng tuần |
   | Độ chính xác    | N/A       | ≥85% dùng được| Soi mẫu      | 3 kỹ sư   |
   | Hài lòng        | N/A       | ≥4.0/5.0      | Rating in-app| Tự động   |
10. TIÊU CHÍ DỪNG:
    | Cấp     | Tín hiệu        | Ngưỡng           | Hành động         |
    | Nhẹ     | Chính xác giảm  | <80% trong 1 tuần| Rà prompt/docs    |
    | Vừa     | Adoption giảm   | <50 DAU sau 4 tuần| Điều tra + đổi UX|
    | Nghiêm  | Rò rỉ dữ liệu/PII| 1 lần           | DỪNG NGAY + audit |
    | Nguy cấp| Vượt ngân sách  | >$3K/tháng       | Tạm dừng + tối ưu |
11. KẾ HOẠCH ADOPTION (L7):
    • Ai dùng đầu: 100 kỹ sư từ 3 đội (đã chọn)
    • Workflow đổi: hỏi bot TRƯỚC → không trả lời được → Slack như cũ
    • Huấn luyện: tự phục vụ (email giới thiệu + video 5 phút). Không cần lớp.
    • Hỗ trợ: kênh #grabgpt-feedback. Chủ trả lời trong 24h.
    • Động lực: trả lời 30s vs 2–4h. Tự nguyện (không bắt buộc).
    • Rủi ro: 3 kỹ sư soi nghỉ → ai soi? → kế hoạch: huấn luyện 2 người dự phòng.
12. LỜI HỨA ĐẦU RA: sau 8 tuần giao:
    • Báo cáo bằng chứng (người dùng, chính xác, giảm support, phản hồi)
    • Khuyến nghị cụ thể: Mở rộng / Đổi hướng / Dừng (kèm dữ liệu)
    • Nếu Mở rộng: kế hoạch mở rộng + đề xuất ngân sách chính thức
13. LỜI XIN: XIN $1K/tháng (2 tháng) + 20% thời gian 1 kỹ sư + quyền truy
    cập tuyến riêng. HỨA: báo cáo bằng chứng trong 8 tuần. RỦI RO: thấp
    (ngân sách nhỏ, đội có sẵn, không ảnh hưởng production).
```

Tư duy phản biện sau Pilot Plan:
- Ngân sách $1K/tháng — QUÁ RẺ không? Có gì CHƯA TÍNH (chi phí ẩn)?
- "Tự nguyện" — nếu không ai dùng thì sao? Động lực có đủ?
- Tiêu chí dừng — có ĐỦ MẠNH để thực sự DỪNG không? Hay sẽ bị bỏ qua vì "chờ thêm"?
- Chỉ số — đo ĐÚNG thứ không? DAU ≠ giá trị. Người dùng hằng ngày nhưng không thấy hữu ích = sao?
- 8 tuần — đủ để có bằng chứng? Hay quá ngắn để thấy mẫu thất bại?

### §A8 — Khung Đánh Giá (đầu ra Bước 7)

**Mục đích, người nhận, câu hỏi nó trả lời:**

| | |
|---|---|
| **Mục tiêu** | Thiết kế CÁCH ĐO để biết pilot thành/bại — TRƯỚC khi bắt đầu. Không phải "chạy xong mới nghĩ đo gì" — mà "biết trước NHỮNG GÌ cần THẤY để ra quyết định". |
| **Đưa cho ai** | Đội (biết thu dữ liệu gì), Người giao đề (đồng thuận "thành công là gì"), Tài chính (biết khi nào dừng chi tiền). |
| **Trả lời câu gì** | (1) Thành công = con số gì? (2) Biết SỚM (chỉ báo sớm) trước khi quá muộn? (3) Khi nào DỪNG? (4) Thu dữ liệu bằng gì, ai thu, bao lâu/lần? |
| **Dùng để làm gì** | Sau pilot: đối chiếu KẾT QUẢ vs PLAN. Không có khung này → "pilot xong rồi — tốt hay không? Ai biết?" — không ra được quyết định. |

**Quy trình tạo ra (từng bước + phản biện):**

| Bước | Làm gì | Câu hỏi phải trả lời | Phản biện |
|---|---|---|---|
| 1 | Định nghĩa chỉ số (SMART) | "Chỉ số này ĐO ĐƯỢC không? Bằng gì?" | Chỉ số không đo được = chỉ số giả. Nghe hay nhưng vô nghĩa. |
| 2 | Đặt mốc nền (baseline) | "HIỆN TẠI con số là bao nhiêu?" | Không có baseline → không biết "tốt hơn" hay "xấu hơn". |
| 3 | Đặt ngưỡng | "BAO NHIÊU là đủ? Ai đồng ý con số này?" | Ngưỡng phải KHỚP với người giao đề TRƯỚC — không đổi sau. |
| 4 | Định nghĩa chỉ báo sớm | "Biết SỚM thế nào trước khi quá muộn?" | Chỉ số trễ (doanh thu) biết quá muộn. Chỉ báo sớm (lượng dùng) biết sớm. |
| 5 | Định nghĩa tiêu chí dừng | "DỪNG khi nào? Ai có quyền dừng?" | Không có tiêu chí dừng = dự án zombie (không chết, không sống). |
| 6 | Kế hoạch thu dữ liệu | "AI thu? Bằng gì? Bao lâu/lần?" | Thủ công → sẽ quên. Tự động → phải setup. |

Mẫu đã điền (GrabGPT):

```
CHỈ SỐ THÀNH CÔNG (SMART):
| Chỉ số           | Mốc nền  | Mục tiêu | Cách đo          | Ai đo     | Tần suất |
| Người dùng/ngày  | 0        | ≥100     | Analytics (tự)   | Hệ thống  | Hằng ngày|
| Giảm support     | 200 Q/wk | ≤140     | Đếm Slack        | PM        | Hằng tuần|
| Độ chính xác     | N/A      | ≥85%     | Soi 50 mẫu       | 3 chuyên  | Hằng tuần|
| Hài lòng         | N/A      | ≥4.0/5   | Rating trong app | Hệ thống  | Liên tục |
| Thời gian phản hồi| 2–4h    | <30s     | Log hệ thống     | Hệ thống  | Tự động  |

CHỈ BÁO SỚM (biết sớm):
  • Tuần 1: có người dùng không? (>30/ngày = khỏe)
  • Tuần 2: họ QUAY LẠI không? (giữ chân > 50%)
  • Tuần 3: support Slack có GIẢM chưa? (xu hướng)
  • Cờ đỏ: người dùng cao nhưng hài lòng thấp = dùng thử rồi bỏ

TIÊU CHÍ DỪNG:
  | Tín hiệu              | Ngưỡng        | Thời gian   | Hành động         | Ai quyết       |
  | Chính xác giảm        | <80% (1 tuần) | Bất kỳ lúc  | Rà docs/prompt    | PM + Chuyên gia|
  | Adoption giảm         | <50 DAU       | Sau tuần 4  | User research + sửa| PM            |
  | Rò rỉ dữ liệu/PII     | 1 lần         | Bất kỳ lúc  | DỪNG NGAY. Audit. | PM + Bảo mật   |
  | Vượt ngân sách        | >$3K/tháng    | Bất kỳ lúc  | Tạm dừng + tối ưu | PM + Tài chính |
  | Chuyên gia không rảnh | 2 tuần liền   | Bất kỳ lúc  | Tìm dự phòng/dừng | PM + Lead      |

KẾ HOẠCH THU DỮ LIỆU:
  | Dữ liệu          | Công cụ        | Tự/Thủ công | Cần setup       |
  | Lượng dùng (DAU) | Analytics SDK  | Tự động     | 1 ngày tích hợp |
  | Hài lòng         | Widget in-app  | Tự động     | 2h build        |
  | Độ chính xác     | Bảng soi mẫu   | Thủ công    | Template sẵn    |
  | Tải support      | Slack export   | Bán tự động | Script 30 phút  |
  | Chi phí          | API dashboard  | Tự động     | Đã có           |

ĐIỂM QUYẾT ĐỊNH:
  | Tuần | Rà gì            | Ai họp           | Quyết định gì                  |
  | 2    | Setup xong?      | PM + Backend     | Tiếp/Dừng Giai đoạn 2          |
  | 4    | Chỉ số đúng hướng?| PM + Lead + CG  | Tiếp / Điều chỉnh / Lo ngại    |
  | 6    | Phân tích xu hướng| PM + Lead       | Tín hiệu sớm: mở rộng hay đổi? |
  | 8    | Đánh giá cuối    | PM + Lead + TC   | QUYẾT: Mở rộng / Đổi / Dừng    |
```

Tư duy phản biện sau Bước 7:
- ≥85% chính xác — CON SỐ NÀY TỪ ĐÂU? Có mốc đối chiếu ngành không? Hay "nghe hợp lý"?
- "DỪNG NGAY" khi rò rỉ dữ liệu — ai THỰC SỰ thực thi? Hay chỉ trên giấy?
- Cỡ mẫu 50/tuần — đủ để kết luận không? (thống kê: độ tin cậy bao nhiêu?)
- Người dùng nhiều ≠ hài lòng ≠ giá trị. Người dùng nhiều nhưng sai nhiều = tệ hơn không có.
- Ai THẬT SỰ có quyền dừng dự án? PM? Lead? Hay không ai dám dừng?

### §A9 — Hướng Dẫn Slide Trình Bày (đầu ra Bước 8)

**Mục đích, người nhận, câu hỏi nó trả lời:**

| | |
|---|---|
| **Mục tiêu** | Trình bày để người ra quyết định ra được quyết định (Duyệt/Có điều kiện/Thiết kế lại/Tạm dừng/Dừng). Không phải để "khen hay" — mà để họ có ĐỦ THÔNG TIN nói Có/Không/Có điều kiện. |
| **Đưa cho ai** | Người ra quyết định (CEO/VP/Tài chính). Họ không đọc 5 trang — họ cần 5–7 slide + 3 câu trả lời. |
| **Trả lời câu gì** | (1) Vấn đề gì? (2) Làm gì? (3) Tốn bao nhiêu? (4) Biết thành/bại thế nào? (5) Xin gì? |
| **Dùng để làm gì** | Lấy phê duyệt (hoặc quyết định dừng). Sau trình bày: có QUYẾT ĐỊNH RÕ RÀNG — không phải "để anh suy nghĩ". |

**Quy trình tạo ra (từng bước + phản biện):**

| Bước | Làm gì | Câu hỏi phải trả lời | Phản biện |
|---|---|---|---|
| 1 | Soạn deck (5–7 slide) | "Mỗi slide 1 THÔNG ĐIỆP CHÍNH — là gì?" | Hơn 7 slide = quá nhiều. Người ra quyết định không có thời gian. |
| 2 | Lường trước 5 câu hỏi khó | "Họ sẽ CHALLENGE gì?" | Nếu không nghĩ ra câu hỏi → mình chưa hiểu audience. |
| 3 | Chuẩn bị dữ liệu dự phòng | "Mỗi claim — BẰNG CHỨNG ở đâu?" | "Tôi tin" ≠ bằng chứng. "Dữ liệu cho thấy" = bằng chứng. |
| 4 | Chuẩn bị Plan B | "Nếu họ nói 'không' — mình đề xuất gì?" | Không có Plan B = được ăn cả ngã về không = lời xin rủi ro. |
| 5 | Tập 3 câu phản biện | "Số liệu lấy ở đâu? Nếu giả định sai? Chưa tính gì?" | Nếu không trả lời được → chưa sẵn sàng trình bày. |

Mẫu đã điền (GrabGPT) — bản lớp = bản phòng thủ 5 phút; sổ tay = bản quyết định 7 slide đầy đủ:

```
Slide 1 — VẤN ĐỀ (2 phút): "500 kỹ sư bị block 2–4h/lần ✅. Đội Platform
  mất 🧮 67h/tuần [ước tính để giảng]. Tri thức có nhưng không tra cứu được."
Slide 2 — BẰNG CHỨNG (3 phút): 200 Q/tuần, 60% lặp, 🧮 $15K/tháng chi phí
  cơ hội [ước tính để giảng]. Khảo sát 50 kỹ sư xác nhận pain.
Slide 3 — CÁCH LÀM (3 phút): Boost — LLM + RAG + tuyến riêng. Pattern: như
  Stripe/Shopify đã làm. KHÔNG build mô hình riêng (không cần, không có đội).
Slide 4 — DEMO (5 phút): chiếu live/video: kỹ sư hỏi → bot trả lời → <30s.
  Weekend hack: 300 người organic [✅ Grab blog]. Chuyên gia: 🧮 70% dùng
  được [ước tính để giảng, không phải Grab công bố].
Slide 5 — KẾ HOẠCH (5 phút): 8 tuần, 3 giai đoạn, ngân sách $1K/tháng, 1 kỹ
  sư 20%. Chỉ số: ≥100 người dùng/ngày, chính xác ≥85%, giảm support −30%.
Slide 6 — RỦI RO + DỪNG (3 phút): rò rỉ dữ liệu → dừng ngay; chi phí >$3K
  → tạm dừng. Rủi ro: docs lỗi thời (cách giảm: kế hoạch cập nhật).
Slide 7 — LỜI XIN (2 phút): xin $1K/tháng + 20% 1 kỹ sư + tuyến riêng.
  Hứa: báo cáo bằng chứng trong 8 tuần. Lựa chọn quyết định: Duyệt / Duyệt
  có điều kiện / Thiết kế lại / Dừng.

3 CÂU PHẢN BIỆN CHUẨN BỊ:
  Q "Số liệu 67h/tuần lấy ở đâu?"
  A "Slack analytics 1 tháng + lấy mẫu 1 tuần phân loại thủ công."
     (lưu ý: 67h là 🧮 ước tính để giảng, không phải Grab công bố)
  Q "Nếu docs lỗi thời và bot trả lời sai liên tục?"
  A "Tiêu chí dừng: <80% chính xác → tạm dừng + cập nhật docs. Có phương
     án dự phòng: Slack như cũ."
  Q "Tình huống nào chưa tính?"
  A "Mở rộng ngoài engineering (sales, ops) — chưa có kế hoạch. Pilot này
     chỉ nội bộ engineering."
```

Tư duy phản biện sau Bước 8:
- Mình trình bày để THUYẾT PHỤC hay để họ CÓ ĐỦ THÔNG TIN ra quyết định? (hai cái khác nhau)
- Demo đẹp + lập luận yếu = THẤT BẠI (McDonald's). Bằng chứng mạnh + demo vừa = THẮNG (JPMorgan).
- "Plan B" — mình có sẵn chưa? Hay chỉ có 1 lựa chọn "duyệt hoặc thôi"?
- Đúng AUDIENCE: CEO quan tâm khác VP Engineering khác Tài chính.

---

## 6. Bộ Câu Hỏi Dùng Với AI — Bản Tư Duy Phản Biện

> KHÔNG phải "dán vào rồi để AI làm hộ". Mỗi mục là một bài tập tư duy: **nghĩ trước → hỏi AI → kiểm tra → phản biện**. AI là *công cụ*, KHÔNG phải người ra quyết định.

Cấu trúc mỗi mục giống nhau: (a) tự nghĩ trước khi hỏi, (b) prompt có sẵn câu thách thức, (c) kiểm tra sau khi AI trả lời, (d) phản biện. Dưới đây là phần lõi cho 8 bước.

### Bước 1 — AI hỗ trợ Nhận đề bài

**Tự nghĩ trước:** Tôi đã NGHE kỹ chưa hay đang vội diễn giải? "Tại sao bây giờ" — có câu trả lời chưa? Đề này dạng ⓐ/ⓑ/ⓒ?

**Prompt:**
```
Bối cảnh: Tôi vừa nhận yêu cầu từ [CHỨC VỤ]: "[DÁN NGUYÊN VĂN]"
Hoàn cảnh: [TẠI SAO HỌ NÓI ĐIỀU NÀY BÂY GIỜ? CHUYỆN GÌ ĐÃ XẢY RA?]
Giúp tôi PHÂN TÍCH (không phải giải):
1. Đề này thuộc dạng nào: ⓐ mơ hồ, ⓑ cụ thể, ⓒ tích hợp? Tại sao?
2. Câu này có phải đề bài THẬT không? Hay là TRIỆU CHỨNG của vấn đề khác?
3. 5 câu hỏi tôi NÊN HỎI LẠI để xác định vấn đề thật
4. "Tại sao bây giờ" — giả thuyết về động lực thật (FOMO vs nỗi đau thật?)
5. CẢNH BÁO: cái gì có thể SAI nếu tôi nhận đề này y nguyên?
```
**Kiểm tra sau:** AI có giả định quá nhiều (nó không biết bối cảnh nội bộ)? Trong "5 câu hỏi", câu nào tôi đã biết câu trả lời rồi → bỏ. Câu quan trọng nhất hỏi TRƯỚC.
**Phản biện:** AI KHÔNG thay tôi nghe người giao đề. Prompt này chỉ giúp *chuẩn bị* — không thay cuộc họp. Nếu AI nói "dạng ⓐ" nhưng tôi thấy có đủ info cho ⓑ → AI có thể sai, tôi biết bối cảnh hơn.

### Bước 2 — AI hỗ trợ Bóc tách & khảo sát

**Tự nghĩ trước:** Tôi đã gặp bao nhiêu người (chỉ 1–2 = CHƯA ĐỦ)? Có đang nghe một phía? Pain họ kể có số liệu hay cảm tính?

**Prompt (tra cứu sâu):**
```
Công ty tôi: [NGÀNH], [QUY MÔ], [MÔ HÌNH]. Đề bài thô: "[DÁN TỪ BƯỚC 1]"
Ràng buộc: [LIỆT KÊ]
Nghiên cứu và TRẢ LỜI CÓ PHẢN BIỆN:
1. Các bài toán AI phổ biến trong ngành này — CHỈ liệt kê bài đã có
   BẰNG CHỨNG thành công (không liệt kê bài "nghe hay")
2. Công ty TƯƠNG TỰ (cùng quy mô) đã nhiệm vụ trọng tâm? Chỉ nguồn cho từng case.
3. Bài nào có ROI rõ ĐƯỢC GHI NHẬN (có số liệu)?
4. Bài nào thường THẤT BẠI? TẠI SAO (cụ thể, không phải "khó")?
5. CẢNH BÁO: bài nào nghe hay nhưng KHÔNG phù hợp quy mô/ngành của tôi?
```
**Kiểm tra sau:** Case AI đưa có *trích dẫn* không hay tự bịa? "Tương tự cùng quy mô" — đúng là tương tự không? "ROI rõ" — từ báo cáo chính thức hay blog?
**Phản biện:** Bảng kê use case phải đến từ NGƯỜI THẬT (phỏng vấn) — không phải từ AI nghiên cứu. AI nhìn từ ngoài; tôi phải xác nhận với từng leader.

### Bước 3 — AI hỗ trợ Chọn Quick Win

**Tự nghĩ trước:** Bảng kê đã hoàn chỉnh chưa (thiếu info = chọn sai)? Tôi có thiên vị (thích bài quen/dễ)? "Quick Win" = bài *chứng minh được nhanh nhất*, KHÔNG phải bài dễ nhất.

**Prompt:**
```
Đây là Bảng kê use case của tôi: [DÁN BẢNG]. Ràng buộc: [NGÂN SÁCH, THỜI GIAN, ĐỘI]
Giúp tôi PHÂN TÍCH (không phải CHỌN — tôi chọn):
1. Chấm từng bài: Tác động(30%) × Khả thi(25%) × Người duyệt(25%) × Tốc độ(20%)
2. Với MỖI bài: 1 LÝ DO NÊN CHỌN và 1 LÝ DO KHÔNG NÊN CHỌN
3. Bài nào RỦI RO CAO NHẤT nếu thất bại (mất uy tín/ngân sách/niềm tin)?
4. Bài nào BẰNG CHỨNG NHANH NHẤT (chứng minh trong < 2 tuần)?
5. KIỂM TRA BẪY: bài nào "nghe hay" nhưng rủi ro cao hoặc tác động ảo?
6. NẾU TÔI CHỌN SAI — hậu quả gì? Quay lại được không?
```
**Kiểm tra sau:** Điểm số — tôi có đồng ý không (AI chấm dựa trên *chữ*, tôi biết *thực tế*)? "Leader ủng hộ" — AI không biết ai *thực sự* ủng hộ.
**Phản biện:** AI CHẤM = gợi ý. QUYẾT ĐỊNH là của tôi. "Tác động cao" nhưng không ai ủng hộ = KHÔNG phải Quick Win. Ủng hộ > Tác động.

### Bước 4 — AI hỗ trợ Quyết định Approach

**Tự nghĩ trước:** Đội tôi *thực sự* có gì (không phải "sẽ có")? Bài này có ai đã giải ở ngành khác chưa (hầu hết là CÓ)? Tôi muốn "tự build" vì *thích* hay vì *cần* (kiểm tra cái tôi)?

**Prompt (đối chiếu pattern):**
```
Bài toán: Input [GÌ VÀO] · Output mong muốn [GÌ RA] · Lĩnh vực [NGÀNH] ·
Người dùng [AI DÙNG, BAO NHIÊU, TRÌNH ĐỘ] · Tương tác [CHAT/VOICE/BATCH/REALTIME]
PHÂN TÍCH TRUNG THỰC:
1. Lõi trừu tượng: bỏ hết nghiệp vụ — bài này thực chất là gì?
2. Tìm 3–5 case TƯƠNG TỰ (cùng lõi) ở NGÀNH KHÁC. Chỉ nguồn.
3. Họ dùng gì (công cụ/mô hình/cách làm)?
4. BUILD mất bao lâu THẬT SỰ? (×2–3 ước tính của kỹ sư)
5. BUY có gì sẵn? Giá? Giới hạn? — 6. BOOST khả thi không?
7. CẢNH BÁO: tôi có đang muốn build vì CÁI TÔI không? (80–90% case là Boost/Buy)
```
**Kiểm tra sau:** Pattern có *đúng là giống* không hay chỉ giống bề ngoài? Thông tin nhà cung cấp có cập nhật không (dữ liệu huấn luyện AI có thể cũ)? "Build mất X tháng" — hỏi KỸ SƯ, không tin AI ước.
**Phản biện:** "Tự build" là quyết định KHÓ rút lại. AI không biết động lực nội bộ của đội tôi. Hỏi: "Nếu chọn sai approach — mất gì? Bao lâu để sửa?"

### Bước 5 — AI hỗ trợ Bản thử

**Tự nghĩ trước:** Bản thử để *kiểm chứng* (học được gì), không phải để *gây ấn tượng*. Tôi cần CHO XEM để người ta nói "đúng/sai" — không cần "đẹp".

**Prompt:**
```
Bài toán [MÔ TẢ] · Approach [BUILD/BOOST/BUY/PARTNER] · Người dùng [AI, Nhiệm vụ trọng tâm] ·
Thời gian có [BAO LÂU]
Giúp tôi THIẾT KẾ bản thử thông minh:
1. MVP cực nhỏ: người dùng nhiệm vụ trọng tâm → công cụ trả gì? (tối đa 3 bước)
2. KHÔNG cần gì cho v1?
3. Tôi (PM, không code) làm được gì KHÔNG cần kỹ sư? (người đóng vai AI,
   mockup, công cụ no-code, demo do AI sinh)
4. Gì cần kỹ sư? (ước tính thời gian THẬT — ×2)
5. SAU KHI cho xem — hỏi gì để kiểm chứng? ("đúng không? thiếu gì? sai ở
   đâu?" — không phải "hay không?")
6. CA BIÊN: input nào làm bản thử HỎNG? (chuẩn bị trước)
```
**Kiểm tra sau:** "MVP nhỏ" có *thật sự nhỏ* không? Câu hỏi sau khi cho xem có giúp *kiểm chứng* hay chỉ câu khen?
**Phản biện:** Bản thử ĐẸP ≠ bản thử TỐT. Tốt = học được điều gì đó. Chuyên gia soi TRƯỚC khi cho người duyệt xem — sai nghiệp vụ trước mặt sếp = thảm họa.

### Bước 6 — AI hỗ trợ Pilot Plan

**Tự nghĩ trước:** Tôi có đủ bằng chứng để viết cam kết chưa (Problem Framing ✓, Demo ✓, Chuyên gia ✓)? Ngân sách — tôi *thực sự* biết giá hay đang đoán? "Hứa gì" — tôi giao được không hay đang hứa quá?

**Prompt:**
```
Bối cảnh: Vấn đề [1–2 CÂU] · Approach [...] · Kết quả demo [...] · Chuyên gia
nói [...] · Ngân sách có [...] · Ràng buộc thời gian [...] · Đội có [AI, % THỜI GIAN]
Soạn nháp AI Pilot Plan 13 mục — VÀ THÁCH THỨC MỖI MỤC:
... (Tóm tắt vấn đề · Approach + lý do không chọn cách khác · Kết quả demo ·
Kế hoạch chuyên gia · Phạm vi · RACI · Ngân sách từng hạng mục + chi phí ẩn ·
Lịch + mốc · Chỉ số SMART + mốc nền + ngưỡng + cách đo · Tiêu chí dừng 4 cấp
+ ai quyết · Kế hoạch adoption L7 · Lời hứa đầu ra · Lời xin) ...
SAU KHI NHÁP — tự thách thức: ngân sách thiếu hạng mục nào? Chỉ số đo được
không? Tiêu chí dừng đủ mạnh để thực sự dừng? Nếu KHÔNG AI DÙNG — kế hoạch gì?
```
**Kiểm tra sau:** Ngân sách có chi phí ẩn (thời gian kỹ sư là chi phí dù "đã có")? Lịch có thực tế không (thường quá lạc quan)? Ngưỡng chỉ số đã đồng thuận với người duyệt chưa?
**Phản biện:** Pilot Plan KHÔNG phải đề xuất xin tiền. Là cam kết hai chiều. "Hứa giao báo cáo bằng chứng" — NẾU bằng chứng cho thấy THẤT BẠI, tôi có đủ can đảm nói không? Tiêu chí dừng chỉ có giá trị nếu *người có quyền* thực thi.

### Bước 7 — AI hỗ trợ Đo lường

**Tự nghĩ trước:** Chỉ số này đo được không (không đo được = không có)? Mốc nền — có số liệu hiện tại chưa (chưa → đo TRƯỚC khi bắt đầu pilot)? "Thành công" — tôi và người duyệt đồng nhất định nghĩa chưa?

**Prompt:**
```
Pilot: Bài toán [GÌ] · Người dùng [AI, BAO NHIÊU] · Thời lượng [BAO LÂU] ·
Mốc nền hiện tại [SỐ LIỆU — chưa có thì nói "chưa đo"]
Giúp tôi THIẾT KẾ và THÁCH THỨC:
1. 3–5 chỉ số thành công — mỗi cái phải: ĐO ĐƯỢC (bằng gì?), CÓ MỐC NỀN, CÓ NGƯỠNG
2. CHỈ BÁO SỚM — biết sớm (1–2 tuần) trước khi chỉ số chính ra kết quả
3. Tiêu chí dừng 4 cấp + ai có QUYỀN dừng + quy trình
4. BẪY: chỉ số nào dễ BỊ "lách"? (người dùng cao vì bắt buộc, không phải hữu ích)
5. AI HỎNG ÂM THẦM — chỉ số nào phát hiện TRƯỚC KHI người dùng biết?
6. Cỡ mẫu: cần BAO NHIÊU điểm dữ liệu? Trong BAO LÂU? (mức tin cậy?)
```
**Kiểm tra sau:** Chỉ số có thật "SMART" không? Ngưỡng AI đề xuất dựa trên gì, có mốc đối chiếu ngành không? "DỪNG NGAY" — ai làm, có quy trình chuẩn không?
**Phản biện:** Chỉ số không có mốc nền = vô nghĩa. "AI hỏng âm thầm" là rủi ro LỚN NHẤT — cần giám sát chủ động, không đợi người dùng báo.

### Bước 8 — AI hỗ trợ Trình bày

**Tự nghĩ trước:** Người nghe là ai, họ *quan tâm* gì (CEO quan tâm ROI, VP kỹ thuật quan tâm khả thi, Tài chính quan tâm rủi ro)? Tôi trình bày để họ *ra quyết định* — không phải để họ *khen hay*. Ba câu phản biện — tôi tự trả lời trước được không?

**Prompt:**
```
Bối cảnh: Pilot Plan [TÓM 3 CÂU] · Người nghe [AI — chức vụ, họ quan tâm gì] ·
Thời gian [BAO LÂU] · Demo có [CÓ/KHÔNG — dạng gì]
Giúp tôi CHUẨN BỊ TRÌNH BÀY + PHẢN BIỆN:
1. Cấu trúc deck: mỗi slide 1 THÔNG ĐIỆP CHÍNH (tối đa 7 slide) — slide 1 trả
   lời "tại sao nên nghe tiếp?"; slide cuối là LỜI XIN RÕ RÀNG
2. 5 câu hỏi KHÓ NHẤT họ sẽ hỏi — và nháp câu trả lời
3. Với MỖI tuyên bố: bằng chứng ở đâu? (không có → bỏ)
4. PHƯƠNG ÁN B: nếu họ nói "không"/"chưa" — tôi đề xuất gì?
5. CHỐNG MẪU XẤU: demo đẹp + lập luận yếu (bẫy McDonald's); quá nhiều dữ
   liệu không có câu chuyện; xin quá nhiều không có cách giảm rủi ro
6. 3 CÂU PHẢN BIỆN bắt buộc: "Số liệu lấy ở đâu?" / "Nếu giả định [X] sai?" /
   "Tình huống nào chưa tính?"
```
**Kiểm tra sau:** Deck có *câu chuyện* không hay như báo cáo? 5 câu hỏi — tôi trả lời được không (thử với đồng nghiệp)? Có tuyên bố nào tôi KHÔNG có bằng chứng → bỏ ra (thật hơn đẹp).
**Phản biện:** "Demo đẹp + lập luận yếu" → thất bại (McDonald's). "Bằng chứng mạnh + demo vừa" → thắng (JPMorgan COiN: 360K giờ/năm, duyệt ngay). KHÔNG BAO GIỜ nói "không có rủi ro" — nói "rủi ro là X, cách giảm là Y".

---

## 7. Kho Case + Nguồn

> Một case xuyên suốt (GrabGPT) đi từ Bước 1 đến Bước 8 + các case ngắn neo từng bước. Mọi số liệu giữ nguyên dấu nguồn.

### 7.1 Case xuyên suốt: GrabGPT (Grab, Singapore, 3/2023)

Công ty siêu ứng dụng (~10.000 nhân viên). Nguồn: ✅ Grab Engineering Blog (công khai, chi tiết).

| Bước | GrabGPT đã trải qua |
|---|---|
| 1. Nhận đề | Lãnh đạo: "Explore LLMs" — cực mơ hồ, không chỉ giải bài gì, cho ai |
| 2. Bóc tách | Đội ML Platform phát hiện đang chìm trong câu hỏi Slack, ~60% lặp lại — pain thật |
| 3. Quick Win | Chatbot Q&A về ML platform cho kỹ sư nội bộ — tác động rõ, người dùng sẵn, dữ liệu có |
| 4. Approach | Thử RAG/embedding (Build) → giới hạn token + kết quả kém → đổi sang **Boost** (LLM API + docs nội bộ) |
| 5. Demo | Weekend hack — dùng hạ tầng có sẵn + Google login + deploy nội bộ. 2 ngày, không phải 3 tháng |
| 6. Pilot | Không có pilot chính thức — triển khai tự nhiên. 300 người ngày 1, 600 ngày 2. Tuyến riêng + audit trail |
| 7. Đo lường | 3.000+ người trong 3 tháng. 600 người dùng/ngày — công cụ được dùng nhiều nhất công ty |
| 8. Trình bày | Tự chứng minh giá trị bằng adoption — từ side project thành sản phẩm được cấp nguồn lực chính thức |

Bài học: đề mơ hồ ("explore LLMs") + đúng đội = tìm được vấn đề thật · Bản thử HỎNG (RAG) → đổi nhanh, không tiếc công đã bỏ · Weekend hack > kế hoạch 3 tháng — adoption tự nhiên là bằng chứng mạnh nhất. *Lưu ý khi dùng case: phần Bước 6–8 của Grab là bottom-up, không có quy trình duyệt chính thức — dùng DBS Bank bổ sung độ chặt về quản trị/đo lường cho Bước 7–8.*

### 7.2 Case ngắn theo từng bước

**Bước 1–2 · DBS Bank — "dùng AI cho ngân hàng" → 240+ ý tưởng → 15 vào production.** DBS (Singapore, ~33.000 nhân viên). Đề mơ hồ "leverage generative AI". Cơ chế bóc tách: Data Chapter — 700 chuyên gia dữ liệu nằm *trong* từng phòng ban (không phải một đội AI ngồi riêng). Kết quả: 240+ ý tưởng GenAI (2023), **15 progressing from experimentation to production** [✅ Annual Report 2023]; con số "20+" là từ nguồn thứ cấp cio.inc [⚠️]. Bài học: "dùng AI cho ngân hàng" thực ra là hàng trăm bài cho nhiều phòng — cần cơ chế sàng lọc → production, không phải mọi ý tưởng đều thành pilot. *(Bổ sung: Microsoft Work Trend Index 2025 — khảo sát thị trường 31.000 người [⚠️ không phải dữ liệu nội bộ Microsoft] — yếu tố tổ chức (văn hóa, hỗ trợ quản lý) tạo tác động gấp đôi nỗ lực cá nhân khi triển khai AI. Khi khảo sát đừng chỉ hỏi "pain gì" mà cả "tổ chức sẵn sàng chưa".)*

**Bước 3 · Zillow (chọn SAI) vs Stanford Retail Allocation (chọn ĐÚNG).**

| | Zillow Offers (SAI) | Stanford Allocation (ĐÚNG) |
|---|---|---|
| Phạm vi | Toàn thị trường bất động sản | Nhóm ~10 chuyên viên phân phối (nhỏ, 1 tuyến báo cáo) |
| Tính trung tâm của tác vụ | Mỗi căn nhà mỗi khác → khó chuẩn hóa | Phân phối = công việc CHÍNH, đồng nhất cho tất cả |
| Người dùng đầu tư | Cấm chuyên gia override (Project Ketchup) | Người dùng đầu tư vì công cụ giải đúng việc chính họ |
| Rủi ro mỗi lần sai | $100K–300K/căn | Thấp (tồn kho thu hồi được) |
| Kết quả | $304M write-down Q3/2021; tổng > $540M; full-year 2021 lỗ mảng Homes $881M | Thành công |

Nguồn: Zillow Q3/FY2021 Investor Release ✅ · Inman (Project Ketchup) ✅ · Stanford HAI 2024 ✅ (số ~10 vs ~200 là ước tính từ bài gốc). Bài học: Quick Win đúng = nhóm nhỏ + tính trung tâm của tác vụ + đồng nhất + người dùng đầu tư; Quick Win sai = phạm vi quá lớn + rủi ro cao + không lặp nhanh. *(Dự án chị em của Stanford cho ~200 quản lý cửa hàng thì THẤT BẠI — vì vận hành cửa hàng không đồng nhất, mỗi cửa hàng mỗi khác.)*

**Bước 4 · Pattern matching: Long Châu ↔ The Coach (case người trong cuộc kể 🗣️).** Long Châu (chuỗi nhà thuốc VN) muốn AI đào tạo sức khỏe — lõi là *học tương tác + chấm điểm + tương tác giọng nói*. The Coach (app dạy tiếng Anh) đã làm đúng lõi đó ở lĩnh vực khác. Kết nối đội đã làm → "đi từ 5 lên". Bài học: hỏi "ai đã giải bài tương tự?" trước khi hỏi "làm sao build?". *(Các ví dụ loại suy khác — phát hiện gian lận giao dịch ↔ phát hiện người bán giả; phân loại triệu chứng ↔ định tuyến yêu cầu tổng đài — là phép loại suy ghép để minh họa cách nghĩ, KHÔNG phải dự án có thật của thương hiệu nào.)*

**Bước 4 · Bẫy "muốn tự build":** Klarna over-automate CSKH rồi phải tuyển lại người [⚠️ phát ngôn CEO, chưa kiểm chứng tài chính sơ cấp]. McDonald's mua Dynamic Yield $300M (2019) rồi bán lại; AI không là sản phẩm cốt lõi [⚠️ báo chí]. Build chỉ đúng khi AI LÀ điểm khác biệt cốt lõi VÀ đội đủ năng lực.

**Bước 5 · Morgan Stanley GPT.** Bản thử GPT-4 tìm + tổng hợp tài liệu nghiên cứu nội bộ, cho cố vấn tài chính xem (đúng người — chuyên gia, không phải hội đồng). Triển khai toàn bộ mảng quản lý tài sản, **trên 98% đội cố vấn dùng** [✅ OpenAI customer story + Morgan Stanley press]. Bài học: bản thử chạy được cho ĐÚNG NGƯỜI > PowerPoint cho lãnh đạo.

**Bước 6 · Pilot không có adoption thì hỏng:** GE Predix (~$7B, retired 2022 — công nghệ chạy được nhưng không ai dùng, không có chủ sở hữu ở tầng vận hành) [⚠️ phân tích thứ cấp]. IBM Watson Health/MD Anderson ($62M — bác sĩ từ chối: không đọc được clinical notes, không tích hợp workflow, thêm việc thay vì bớt việc) [⚠️ STAT News + UT System audit, cần subscription]. *Lưu ý khi giảng: không nói "đầu ra sai vì thiếu chuyên gia" như fact — đây là phân tích thứ cấp.* Bài học: công nghệ đúng + ngân sách lớn + lãnh đạo ủng hộ ≠ thành công. Cần tích hợp workflow + huấn luyện + chủ sở hữu ở tầng vận hành.

**Bước 7 · AI hỏng âm thầm:** Zillow Offers — cấm chuyên gia định giá override (Project Ketchup ✅), thị trường biến động, không có chốt chặn người → $304M write-down Q3/2021, tổng > $540M ✅; các diễn giải "model drift 6 tháng / không ai giám sát" là phân tích thứ cấp 🧮, không phải Zillow công bố. Amazon Hiring (2018) — công cụ thử nghiệm phạt CV chứa từ "women's", phát hiện *trước* khi vào production thật [⚠️ Reuters 2018, Amazon chưa xác nhận chính thức]; bài học là kiểm định công bằng phải bắt đầu từ dữ liệu huấn luyện, không chờ tới khi công cụ "chạy được". Bài học chung: không có tiêu chí dừng = không bao giờ biết lúc nào nên dừng; chỉ số "tổng" che giấu chỉ số "chi tiết"; người *có quyền dừng* phải được chỉ định TỪ ĐẦU.

**Bước 8 · McDonald's (FAIL) vs JPMorgan COiN (WIN).** McDonald's AI drive-through: demo ấn tượng, thực tế chính xác 80–85% (người 90%+), nhận order từ xe bên cạnh; chấm dứt hợp tác IBM 6/2024 [⚠️ báo chí]. JPMorgan COiN: công cụ đọc hợp đồng, không hào nhoáng nhưng bằng chứng áp đảo — **360.000 giờ luật sư/năm tiết kiệm**, 12.000 hợp đồng xử lý trong vài giây, gần như không lỗi [✅ Bloomberg 2017 (sau tường phí) · ✅ ABA Journal (đọc được)]; duyệt ngay. Bài học: người ra quyết định quan tâm ROI định lượng, giảm rủi ro, phạm vi rõ, tiêu chí dừng — không phải demo đẹp.

### 7.3 Bảng tổng hợp case ↔ bước ↔ trạng thái nguồn

| Case | Bước | Dùng để dạy | Trạng thái nguồn |
|---|---|---|---|
| DBS Bank (240+ ý tưởng → 15 production) | 1, 2 | Toàn cảnh → cơ chế sàng lọc | ✅ Annual Report 2023 · ⚠️ cio.inc (con số 20+) |
| Zillow Offers ($304M Q3; full-year 2021 lỗ Homes $881M) | 3, 7 | Chọn sai + Project Ketchup | ✅ Q3/2021 + Q4/FY2021 + Inman |
| Stanford Retail Allocation | 3 | Quick Win đúng cách | ✅ Stanford HAI 2024 |
| Long Châu ↔ The Coach | 4 | Đối chiếu pattern | 🗣️ Người trong cuộc kể (giảng viên) |
| Klarna / McDonald's | 4, 8 | Bẫy Build / demo > bằng chứng | ⚠️ Báo chí (chưa kiểm chứng tài chính) |
| Morgan Stanley GPT | 5 | Bản thử → adoption | ✅ OpenAI customer story (>98% đội cố vấn) |
| GrabGPT | 1–8 | Case xuyên suốt | ✅ Grab Engineering Blog |
| GE Predix (~$7B) | 6 | Không có kế hoạch adoption | ⚠️ Phân tích thứ cấp |
| IBM Watson Health ($62M) | 6 | Workflow + adoption hỏng | ⚠️ STAT News + UT audit (cần mua) |
| Amazon Hiring bias | 7 | Kiểm định công bằng trước triển khai | ⚠️ Reuters 2018 (Amazon chưa xác nhận) |
| JPMorgan COiN | 8 | Bằng chứng → phê duyệt | ✅ Bloomberg 2017 (sau tường phí) · ✅ ABA Journal |

---

### 7.4 Nguồn — link đầy đủ (để học viên tự kiểm chứng)

> Mọi số liệu case ở trên đều truy ngược được về nguồn dưới đây (sao từ `D28-CASE-BANK-v0.1.md`). Giữ nguyên dấu nguồn: ✅ primary · ⚠️ secondary/chưa kiểm chứng · 📖 sau tường phí · 🗣️ người trong cuộc kể. Cả buổi dạy nguyên tắc *"số liệu phải có nguồn"* — đây là chỗ để chính học viên mở link mà kiểm.

**Case xuyên suốt — GrabGPT**
- ✅ https://engineering.grab.com/the-birth-of-grab-gpt — GrabGPT full story (3/2023, weekend hack → company-wide)

**DBS Bank (Bước 1–2)**
- ✅ https://www.dbs.com/annualreports/2023/ceo-reflections.html — PRIMARY: "over 240 GenAI ideas, 15 progressing... to production"
- ⚠️ https://www.cio.inc/asian-banking-giant-maps-its-gen-ai-powered-future-a-27276 — secondary (con số 20+ không khớp Annual Report — tham khảo phụ)
- ✅ https://www.dbs.com/newsroom/DBS_empowers_its_Customer_Service_Officers_with_Gen_AI_powered_virtual_assistant_to_reduce_toil_and_enhance_customer_experience — CSO Assistant
- ✅ https://www.dbs.com/artificial-intelligence-machine-learning/artificial-intelligence/dbs-ai-powered-digital-transformation.html — AI portfolio overview
- ✅ https://www.prnewswire.com/news-releases/harvard-business-school-examines-dbs-ai-strategy-and-implementation-in-its-first-case-study-focusing-on-ai-in-an-asian-bank-302248738.html — HBS case study announcement
- 📖 https://www.hbs.edu/faculty/Pages/item.aspx?num=66332 — HBS Case 625-053 (sau tường phí)

**Microsoft Work Trend Index (Bước 2 — tham chiếu)**
- ✅ https://www.microsoft.com/en-us/worklab/work-trend-index/2025-the-year-the-frontier-firm-is-born — báo cáo 2025 (khảo sát thị trường ~31.000 người, KHÔNG phải data nội bộ Microsoft)

**Zillow + Stanford HAI (Bước 3, 7)**
- ✅ https://investors.zillowgroup.com/investors/news-and-events/news/news-details/2021/Zillow-Group-Reports-Third-Quarter-2021-Financial-Results--Shares-Plan-to-Wind-Down-Zillow-Offers/default.aspx — Q3/2021 chính thức: $304M write-down
- ✅ https://www.inman.com/2021/11/09/zillow-raced-to-catch-up-with-opendoor-in-a-secret-initiative-called-project-ketchup-report/ — Project Ketchup
- ✅ https://www.geekwire.com/2021/ibuying-algorithms-failed-zillow-says-business-worlds-love-affair-ai/ — phân tích lỗi thuật toán
- ✅ https://www.cnn.com/2021/11/02/homes/zillow-exit-ibuying-home-business — đóng chương trình, sa thải 25%
- 📖 https://www.gsb.stanford.edu/insights/flip-flop-why-zillows-algorithmic-home-buying-venture-imploded — Stanford GSB (403 lúc kiểm)
- ✅ https://hai.stanford.edu/news/why-corporate-ai-projects-succeed-or-fail — Stanford HAI retail case

**Pattern Matching + Build Trap (Bước 4) — không có link công khai, ghi rõ dấu nguồn**
- 🗣️ Long Châu ↔ The Coach — case người trong cuộc kể (giảng viên), không có nguồn công khai
- ⚠️ Klarna rehiring — từ phát biểu CEO 2024–2025 (chưa verify link cụ thể)
- ⚠️ McDonald's Dynamic Yield — mua/bán được đưa tin rộng, chưa verify link primary

**Morgan Stanley (Bước 5)**
- ✅ https://openai.com/index/morgan-stanley/ — Morgan Stanley + OpenAI
- ✅ "over 98% advisor teams" — OpenAI customer story (https://openai.com/customer-stories/morgan-stanley) + Morgan Stanley press release (https://www.morganstanley.com/press-releases/ai-at-morgan-stanley-debrief-launch)

**GE Predix / IBM Watson (Bước 6)**
- ✅ https://platformengineering.org/blog/how-general-electric-burned-7-billion-on-their-platform — GE Predix $7B (phân tích chi tiết)
- ⚠️ IBM Watson/MD Anderson $62M — STAT News investigation + UT System audit (link gốc có thể cần subscription)

**Silent Failure (Bước 7)**
- ✅ Zillow — cùng nguồn Bước 3 ở trên
- ⚠️ Amazon recruiting bias — Reuters 2018 + MIT Tech Review (Amazon chưa xác nhận chính thức)

**Demo vs Evidence (Bước 8)**
- ⚠️ McDonald's AI drive-through + IBM kết thúc 6/2024 — CNBC, chưa verify link cụ thể
- ✅ https://www.bloomberg.com/news/articles/2017-02-28/jpmorgan-marshals-an-army-of-developers-to-automate-high-finance — JPMorgan COiN 360K giờ (Bloomberg 2017, sau tường phí)
- ✅ https://www.abajournal.com/news/article/jpmorgan_chase_uses_tech_to_save_360000_hours_of_annual_work_by_lawyers_and — ABA Journal (đọc được)

**Bổ sung**
- ⚠️ Stripe — từ Stripe Sessions 2024 + engineering blog (chưa compile link cụ thể)

---

## 8. Phần Lab — AI20k Learning OS

> Phần này dùng bối cảnh đặc thù của khóa AI20k. Đây là nơi duy nhất trong tài liệu nhắc tới giai đoạn 6 tuần thực chiến — phần lý thuyết chung (Phần 1–7) cố ý không nhắc tới điều này.

### 8.1 Bối cảnh

Khóa AI Thực Chiến có **~500 học viên** (sinh viên năm cuối + người đi làm), đang chuẩn bị cho giai đoạn 6 tuần thực chiến sau Ngày 28. Lab này do track Sản phẩm AI (~80 học viên, làm nhóm 3 người) thực hiện. Hoạt động chính nằm trên Discord, LMS, lớp live, lab, nộp bài và coaching ở quy mô ~500 người; coach/giảng viên phải hỗ trợ nhiều nhóm cùng lúc. Lãnh đạo chương trình muốn xây **AI20k Learning Operating System** — một hệ sinh thái công cụ AI hỗ trợ việc học và vận hành khóa. Chính quy mô ~500 người là lý do không thể xây hết — phải chọn 1 track, bóc tách, chọn Quick Win.

Yêu cầu của người giao đề (chủ chương trình):

> "Khóa học có nhiều điểm có thể dùng AI: Discord, LMS, lab, quiz, review bài, cá nhân hóa học tập, phân loại cho coach, tóm tắt lớp live. KHÔNG build hết cùng lúc. Mỗi nhóm chọn một track, phân rã các use case, chọn lát cắt đầu tiên đáng pilot nhất, và trình bày AI Pilot Plan để tôi quyết định có duyệt không. Tôi không cần sản phẩm hoàn chỉnh. Tôi cần thấy: làm vấn đề nào trước, vì sao, cần dữ liệu gì, cần ai, tốn bao nhiêu, pilot bao lâu, đo bằng gì, và nếu sai thì dừng khi nào."

Ràng buộc chung: không dùng AI thay hoàn toàn coach/giảng viên ở các quyết định quan trọng · chấm điểm AI trong lab là *để phản hồi định hình* (formative), không phải điểm chính thức nếu chưa có hiệu chỉnh của người · output rủi ro cao phải có người soi · trả lời dựa trên tài liệu khóa phải có nguồn trích dẫn · ngân sách pilot nhỏ (ưu tiên công cụ/API có sẵn) · dữ liệu học viên/Discord có rủi ro riêng tư, phải nói rõ dùng dữ liệu nào và dùng thế nào · pilot phải đủ nhỏ để chạy được trong bối cảnh khóa hiện tại.

Thông điệp cốt lõi học viên phải nhớ:

> Trong doanh nghiệp, người giao đề thường giao một "công cụ AI" quá lớn. Việc của PM/PO AI không phải build tất cả, mà chọn lát cắt đầu tiên có bằng chứng để xin pilot.

### 8.2 Tám track (mỗi nhóm chọn 1)

Mỗi track là một công cụ lớn. Nhóm KHÔNG được trình bày "build tất cả"; bắt buộc phân rã và chọn lát cắt đầu tiên.

| # | Track | Công cụ lớn (rút gọn) | Một vài Quick Win gợi ý | Cờ đỏ cần tránh |
|---|---|---|---|---|
| 1 | **Personalized Learning Path** | Cá nhân hóa lộ trình học theo mục tiêu/level/tiến độ/điểm yếu | Checklist cá nhân "bạn đang yếu ở đâu"; gợi ý 3 tài liệu cần xem lại từ 1 bài nộp | Cá nhân hóa giả (đổi tên nhưng nội dung như nhau); khuyến nghị quá tải; dùng dữ liệu nhạy cảm không có đồng ý |
| 2 | **Interactive LMS Tutor** | Biến LMS thành gia sư tương tác có trích dẫn từ tài liệu khóa | Gia sư riêng cho Ngày 28; mini practice 5 câu sau mỗi mục | Bịa nội dung khóa; trả lời "nghe hay" nhưng không nguồn; làm học viên hỏi bot thay vì đọc tài liệu |
| 3 | **AI Lab Copilot** | Hỗ trợ làm lab/code: gợi ý bước, debug, soi trước khi nộp — KHÔNG làm hộ | Soi bài nộp Ngày 28 trước khi submit (thiếu chỉ số/ngân sách/tiêu chí dừng nào?); bot gợi ý không cho đáp án | AI làm hộ bài; phản hồi chung chung không bám tiêu chí; không phân biệt "gợi ý" và "đáp án" |
| 4 | **Learning Memory / Knowledge Graph** | Bộ nhớ học tập xuyên khóa: concept/case/slide/lab liên kết | Bot trả lời "concept X nằm ở đâu trong khóa" có nguồn; bản đồ Ngày 2 → Ngày 27 → Ngày 28 | Graph quá to không ai bảo trì; liên kết nhiều nhưng không giúp hành động; sai nguồn; chạm riêng tư |
| 5 | **Live Class Companion** | Trợ lý trong giờ live: gom câu hỏi, cụm hóa nhầm lẫn, tạo tóm tắt | Cụm 30 câu hỏi Discord thành 5 nhóm cho giảng viên; tóm tắt Ngày 28 (ý chính + câu hỏi ngỏ) | Làm ồn Discord bằng quá nhiều tin bot; tóm tắt sai ý; độ trễ cao; câu hỏi riêng tư lọt vào tóm tắt |
| 6 | **Assessment & Rubric Engine** | Soi artifact lớn theo tiêu chí; AI nháp phản hồi, coach hiệu chỉnh & duyệt | Soi 5-slide Pilot Plan theo tiêu chí Ngày 28, gắn cờ thiếu chỉ số/tiêu chí dừng; nháp phản hồi cho coach | AI chấm như thật khi chưa hiệu chỉnh; phản hồi nghe chuyên nghiệp nhưng sai tiêu chí; thiên vị theo văn phong |
| 7 | **Expert Review Simulator** | AI mô phỏng người duyệt/chuyên gia để phản biện trước khi present thật | Sinh 5 câu phản biện cho AI Pilot Plan Ngày 28; mô phỏng Q&A người giao đề 5 phút | Hỏi câu chung chung; tạo cảm giác "đã luyện" nhưng không sát nghiệp vụ; thay chuyên gia thật ở bài cần nghiệp vụ sâu |
| 8 | **Quiz & Auto-Grading Engine** | Tự tạo quiz từ tài liệu, chấm *định hình* để học viên biết hổng chỗ nào | Tạo quiz 10 câu cho Ngày 28; chấm câu trả lời ngắn; phát hiện top 3 hiểu sai | Quiz quá dễ; AI chấm sai câu mở; không phân biệt định hình vs chính thức; không có nguồn. *Quy tắc riêng: chỉ dùng cho phản hồi định hình; nếu muốn làm điểm chính thức, Pilot Plan phải có hiệu chỉnh người + quy trình khiếu nại.* |

### 8.3 A3 Working Canvas (7 mục — bản nộp)

Nhóm nộp một canvas gồm 7 mục, ánh xạ thẳng với 3 phase:

| Mục | Câu hỏi bắt buộc | Phase |
|---|---|---|
| 1. Track & Big Ask | Track nào? Công cụ lớn người giao đề muốn là gì? | FRAME |
| 2. Tool Breakdown | Công cụ lớn gồm 5–8 module/use case nào? | FRAME |
| 3. Quick Win | Chọn use case nào làm trước? Vì sao? Không chọn cái gì? | FRAME |
| 4. Problem Framing | Ai đau, đau ở workflow nào, mốc nền/tác động, chỉ số thành công, ràng buộc? | FRAME |
| 5. Solution Approach (đã gồm Data & Expert) | Build/Buy/Boost/Partner? Cần công cụ/API/nhà cung cấp nào? Cần dữ liệu gì, ai soi đầu ra, soi bao nhiêu mẫu? | SOLUTION |
| 6. Demo/Mockup/Flow | Người duyệt sẽ nhìn thấy gì? User flow, mockup màn hình, prompt flow, agent flow, hoặc demo chạy được? | SOLUTION |
| 7. AI Pilot Plan | Phạm vi, lịch, người, ngân sách, chỉ số, tiêu chí dừng, lời hứa đầu ra, lời xin | PILOT PLAN |

Cùng nộp: **5-slide Pitch** (Vấn đề & người dùng · Phân rã + Quick Win · Cách làm + Demo trực quan · AI Pilot Plan · Chỉ số + tiêu chí dừng + lời xin) và **Nhật ký AI hỗ trợ** (AI giúp gì / AI đưa output nghe hợp lý nhưng nhóm phải sửa gì / phần nào nhóm tự lập luận, không copy AI).

Lịch lab 70 phút (nhóm 3): 0–5 chọn track + đọc card · 5–15 phân rã công cụ lớn (5–8 use case) · 15–25 chọn Quick Win (chấm điểm) · 25–40 Problem Framing · 40–55 Cách làm + Demo/Mockup/Flow (artifact trực quan) · 55–65 AI Pilot Plan lõi · 65–70 5-slide Pitch.

### 8.4 Tiêu chí chấm 5-Gate

Chấm theo mốc (gate), không theo checklist dài.

| Gate | Đạt khi | Tín hiệu trượt |
|---|---|---|
| **Gate 1 — Phân rã đúng** | Tách công cụ lớn thành các use case riêng biệt | Pitch nguyên cả nền tảng, không biết lát cắt nào làm trước |
| **Gate 2 — Quick Win có lý do** | Có chấm điểm/lý do rõ: tác động, khả thi, bằng chứng, rủi ro | Chọn vì "nghe hay" hoặc "dễ demo" |
| **Gate 3 — Problem Framing thật** | Rõ người dùng, workflow, nỗi đau, mốc nền/chỉ số, ràng buộc | Vấn đề chung chung: "học viên cần học tốt hơn" |
| **Gate 4 — Cách làm + Trực quan rõ** *(BẮT BUỘC)* | Build/Buy/Boost/Partner có lý do; **CÓ mockup/sketch/demo flow** để người duyệt hình dung | Chỉ kể bằng miệng, không có artifact trực quan; mặc định "tự build" |
| **Gate 5 — Pilot Plan đủ để quyết** | Có phạm vi, lịch, người, ngân sách, chỉ số, tiêu chí dừng, lời xin | Demo đẹp nhưng không biết duyệt cái gì |

> Gate 4 là điểm nhấn: nhóm PHẢI có artifact trực quan. Chỉ kể bằng miệng hoặc mặc định "tự build" = trượt Gate 4. Không chấm "slide đẹp" — chấm lập luận chặt, bằng chứng đủ, trả lời phản biện tự tin. Một bản demo chạy được chỉ là điểm cộng, không bắt buộc.

### 8.5 Ba câu phản biện mặc định

Người giao đề / giảng viên hỏi mỗi nhóm 1–2 câu:

1. **"Số liệu / giả định này lấy ở đâu?"**
2. **"Nếu giả định quan trọng nhất của bạn sai thì sao?"**
3. **"Tình huống nào sẽ khiến bạn dừng pilot?"**

---

## 9. Bảng Tổng Mang Về + Nguyên Tắc Chuyển Giao

### 9.1 Bản đồ một trang

```
Ý TƯỞNG →[ HIỂU VẤN ĐỀ · CHỌN CÁCH LÀM · KẾ HOẠCH THỬ NGHIỆM ]→ CHẠY THỬ → PRODUCTION
          └────────────── Ngày 28 hôm nay ──────────────┘

HIỂU VẤN ĐỀ     → Phần A: Hồ sơ Vấn đề   (Bước 1–3 + Problem Framing)
CHỌN CÁCH LÀM   → Phần B+C: Approach + Demo/Mockup/Flow (artifact trực quan bắt buộc)
KẾ HOẠCH THỬ    → Phần D+E: AI Pilot Plan + Pitch        (Bước 6–8)

Nộp: A3 Working Canvas (7 mục) + 5-slide Pitch + Nhật ký AI hỗ trợ
"Không cần nhớ hết. Cần biết: TÔI ĐANG Ở ĐÂU."
```

### 9.2 Bảy lối tư duy — bảng tra một trang

| # | Lối tư duy | Một câu | Câu hỏi tự kiểm |
|---|---|---|---|
| L1 | Decompose | Đề mơ hồ = triệu chứng | "Tôi đã hỏi đủ 'tại sao' chưa?" |
| L2 | Quick Win | Chứng minh giá trị nhanh nhất | "Bài này cho thấy kết quả trong 2 tuần?" |
| L3 | Domain Expert | Chuyên gia từ ngày 1 | "Ai hiểu nghiệp vụ sẽ ngồi với tôi?" |
| L4 | Show → Validate | Cho xem trước, xây sau | "Tôi đã đưa bản thử cho người duyệt xem chưa?" |
| L5 | Pattern Match | Tìm người đã giải bài tương tự | "Bài này giống bài nào ở ngành khác?" |
| L6 | Measure → Decide | Pilot = thí nghiệm có giả thuyết | "Tôi đang đo gì? Ngưỡng bao nhiêu?" |
| L7 | Adopt to Operate | AI chỉ có giá trị trong workflow thật | "Ai dùng hằng ngày? Họ có *muốn* dùng?" |

### 9.3 Mười điều cần khắc

| # | Nguyên tắc | Diễn giải |
|---|---|---|
| 1 | Đầu ra là **bằng chứng**, không phải slide đẹp | Mục tiêu của một PM/PO AI là làm cho một quyết định *duyệt hoặc dừng* diễn ra được — không phải gây ấn tượng |
| 2 | Pilot Plan cho vấn đề **SAI** vẫn là sai | Dù viết hay đến đâu. Vì vậy mốc Problem Framing là không thể bỏ qua |
| 3 | Đề bài mơ hồ là **triệu chứng** | "Làm chatbot" hiếm khi là vấn đề gốc. Đào đến ràng buộc thật trước khi giải |
| 4 | Quick Win = **chứng minh được nhanh**, không phải dễ nhất | Cũng không phải lớn nhất. Chọn theo 4 tiêu chí: tác động, khả thi, ủng hộ, tốc độ |
| 5 | Người giao đề phải **xác nhận** trước khi đi tiếp | Hỏi ngược "anh tóm tắt lại?" — gật cho xong ≠ hiểu đúng |
| 6 | Phần lớn đội chỉ cần **Boost** | Build chỉ đúng khi AI là lý do tồn tại của sản phẩm VÀ đội đủ năng lực |
| 7 | Trực quan hóa là **bắt buộc** ở phase SOLUTION | Mockup/flow để người duyệt nhìn được; demo chạy được chỉ là điểm cộng |
| 8 | Pilot Plan là **cam kết hai chiều** | Xin gì – hứa gì – đo gì – dừng khi nào. Không phải đề xuất xin tiền |
| 9 | AI **hỏng âm thầm** | Không có mốc nền + ngưỡng + người có quyền dừng = không bao giờ biết lúc nào nên dừng |
| 10 | **Adoption > độ chính xác** | Công cụ 99% mà 0 người dùng < công cụ 85% mà 500 người dùng. Ai dùng đầu, workflow đổi gì, ai vận hành |

### 9.4 Bộ công cụ mang về (một trang)

Double Diamond (hai viên kim cương, là lăng kính) · Bảng kê use case AI · Khung chấm Quick Win 4 tiêu chí · Cây quyết định Build/Buy/Boost/Partner · Mẫu Problem Framing 9 mục · Mẫu AI Pilot Plan · Mẫu Tiêu chí dừng 4 cấp · Bảng tra 7 lối tư duy · Bộ câu hỏi dùng với AI (tư duy phản biện) · Ba câu phản biện chuẩn bị cho mọi cuộc duyệt.

---

*Sổ tay học viên — Ngày 28: Triển khai AI trong doanh nghiệp · Từ yêu cầu mơ hồ đến AI Pilot Plan*
*Chương trình VinUni A20 — AI Thực Chiến · Track Sản phẩm AI*

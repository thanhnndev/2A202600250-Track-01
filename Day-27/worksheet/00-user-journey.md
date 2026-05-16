# 00 · User Journey Simulation — Đóng vai Tourist

> **Mục tiêu**: Trước khi tính chi phí, nhóm phải hình dung được khách hàng thật sự hỏi gì, hỏi như thế nào, và 1 conversation thực tế trông ra sao.

---

## Bước 1 — Mỗi người đóng vai 1 tourist

### Tourist #1 (Tên thành viên: Nông Nguyễn Thành — US solo traveler, first-time, budget $600)

```text
Do I need a visa on arrival for Vietnam as a US citizen?
What is the safest way to get from Hanoi airport to the Old Quarter at night?
Can you suggest a 4-day Hanoi + Ha Long itinerary under $600?
Is March a good time for the Ha Giang motorbike loop?
How much should I budget per day for food and local transport?
Can I pay with credit card widely or should I carry cash?
```

### Tourist #2 (Tên thành viên: Nông Nguyễn Thành — UK couple, returning visitor, mid-range)

```text
We want a 7-day itinerary covering Hoi An and Da Nang. Any suggested plan?
Are there any festivals in Hoi An next week?
What's the weather like in Da Nang in early June?
We need a private airport transfer and 3-star hotel booking. Can you arrange?
Is it safe to eat street food if we have nut allergies?
Do you have a guided tour for Ba Na Hills?
```

### Tourist #3 (Tên thành viên: Nông Nguyễn Thành — Australian family of 4, first-time with kids)

```text
We are a family of four with kids. What are kid-friendly activities in HCMC?
How long does it take to get the e-visa approved?
We missed our hotel pickup and want to file a complaint.
What is the best time of day to visit Cu Chi Tunnels?
Can you help us book a Mekong Delta day tour for tomorrow?
Is it raining a lot in HCMC this week?
```

---

## Bước 2 — Gom lại và phân loại

| # | Câu hỏi (1 dòng) | Intent thuộc loại nào | Cần bao nhiêu lượt chat để xong? | Bot trả lời hay chuyển người? |
|---|---|---|---|---|
| 1 | Do I need a visa on arrival for Vietnam as a US citizen? | Visa/Policy | 3 | ☑ Bot · □ Người |
| 2 | How long does it take to get the e-visa approved? | Visa/Policy | 3 | ☑ Bot · □ Người |
| 3 | What's the weather like in Da Nang in early June? | Weather/Event | 2 | ☑ Bot · □ Người |
| 4 | Are there any festivals in Hoi An next week? | Weather/Event | 2 | ☑ Bot · □ Người |
| 5 | Can you suggest a 4-day Hanoi + Ha Long itinerary under $600? | Guide/Destination | 4 | ☑ Bot · □ Người |
| 6 | How much should I budget per day for food and local transport? | Guide/Destination | 3 | ☑ Bot · □ Người |
| 7 | We are a family of four with kids. What are kid-friendly activities in HCMC? | Guide/Destination | 3 | ☑ Bot · □ Người |
| 8 | We need a private airport transfer and 3-star hotel booking. Can you arrange? | Tour/Booking | 1 | □ Bot · ☑ Người |
| 9 | Can you help us book a Mekong Delta day tour for tomorrow? | Tour/Booking | 1 | □ Bot · ☑ Người |
| 10 | We missed our hotel pickup and want to file a complaint. | Khiếu nại | 1 | □ Bot · ☑ Người |

---

## Bước 3 — Rút insight cho nhóm

**Tổng số câu hỏi nhóm gom được**:

```text
10
```

**Phân bố intent thực tế của nhóm** (% mỗi intent):

```text
Guide/Destination: 30%
Visa/Policy: 20%
Weather/Event: 20%
Tour/Booking: 20%
Khiếu nại: 10%
```

**Số lượt chat trung bình để xong 1 chủ đề**:

```text
3-4 lượt cho info questions (visa, guide, weather)
1 lượt cho booking/complaint (handoff ngay)
Trung bình weighted: ~3 lượt
```

**Đối chiếu với đề bài** (Scenario A = 4 lượt, Scenario B = 7 lượt):

```text
Scenario A (4 turns) khá sát với câu hỏi thông tin thực tế. Scenario B (7 turns)
dài hơn — phản ánh tourist hay hỏi gộp nhiều intent trong 1 conversation (VD: hỏi
visa → hỏi weather → hỏi itinerary trong cùng 1 chat).
```

**Insight bất ngờ — điều gì nhóm chỉ hiểu sau khi đóng vai?**

```text
Tourist thường hỏi gộp nhiều intent trong 1 cuộc trò chuyện. Booking/complaint
thường rất ngắn (1 turn) và nên handoff sớm — không nên để AI cố trả lời.
Câu hỏi visa tuy ngắn nhưng cần nhiều follow-up (passport type, duration, fee)
nên actual conversation dài hơn dự kiến.
```

---

## Bảng kiểm trước khi sang file tiếp theo

- [x] Mỗi người trong nhóm đã viết ≥5 câu hỏi tourist
- [x] Đã gom + phân loại intent cho ≥10 câu
- [x] Đã có phân bố intent % của nhóm
- [x] Có ít nhất 1 insight về cách tourist thật sự dùng chatbot

Xong → mở `01-base-flow.md`.

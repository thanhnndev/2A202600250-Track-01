# Mẫu 03 — Dashboard Mock

Vẽ nhanh 4-6 ô để người đọc thấy dashboard sẽ dùng như thế nào. Không cần high-fidelity.

## Quy Tắc

- Ô đầu tiên: tình trạng toàn sản phẩm.
- Các ô tiếp theo: tín hiệu theo quy trình, trust/quality/value, hoặc quyết định.
- Mỗi ô có số hiện tại, mục tiêu, trạng thái, hành động nếu đỏ.
- Không vẽ quá 6 ô.

## Khung 6 Ô

```text
┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 1: PRODUCT HEALTH             │ │ TILE 2: WORKFLOW 1                 │
│ Metric: __________________________ │ │ Metric: __________________________ │
│ Current: ______ Target: _________  │ │ Current: ______ Target: _________  │
│ Status: GREEN / AMBER / RED        │ │ Status: GREEN / AMBER / RED        │
│ Action if red: ___________________ │ │ Action if red: ___________________ │
└────────────────────────────────────┘ └────────────────────────────────────┘

┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 3: WORKFLOW 2                 │ │ TILE 4: TRUST / QUALITY            │
│ Metric: __________________________ │ │ Metric: __________________________ │
│ Current: ______ Target: _________  │ │ Current: ______ Target: _________  │
│ Status: GREEN / AMBER / RED        │ │ Status: GREEN / AMBER / RED        │
│ Action if red: ___________________ │ │ Action if red: ___________________ │
└────────────────────────────────────┘ └────────────────────────────────────┘

┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 5: VALUE / COVERAGE           │ │ TILE 6: DECISION                   │
│ Metric: __________________________ │ │ Continue / Pivot / Kill: _________ │
│ Current: ______ Target: _________  │ │ Metric mạnh nhất: ________________ │
│ Status: GREEN / AMBER / RED        │ │ Before scale: ____________________ │
│ Action if red: ___________________ │ │ Người phụ trách: _________________ │
└────────────────────────────────────┘ └────────────────────────────────────┘
```

## Tự kiểm tra

- [ ] Có 4-6 ô.
- [ ] Ô đầu là toàn sản phẩm.
- [ ] Có ít nhất 1 ô Quality hoặc Trust.
- [ ] Có ô Decision.
- [ ] Mỗi ô có action nếu đỏ.

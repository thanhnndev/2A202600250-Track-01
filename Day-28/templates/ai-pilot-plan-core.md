# Template — AI Pilot Plan core

> Mẫu đầy đủ cho `worksheet/03-pilot-plan/1-pilot-plan.md`. Bản nộp lab chỉ cần **12 mục core** dưới đây (handbook §A7 có bản 13 mục chi tiết hơn — tham khảo sau lab). AI Pilot Plan là **cam kết 2 chiều**: xin nguồn lực ↔ hứa giao bằng chứng + chấp nhận dừng.

---

## Khung 12 mục (copy vào worksheet/03-pilot-plan/1-pilot-plan.md)

```text
1. TÓM TẮT VẤN ĐỀ (1 câu)
   …

2. CÁCH LÀM + LÝ DO
   Chọn: Build / Buy / Boost / Partner
   Vì: …
   Không chọn cách khác vì: …

3. PHẠM VI PILOT
   Phục vụ: … (bao nhiêu người / nhóm nào)
   Thời lượng: … tuần
   Số phase: …

4. NGƯỜI
   Nhóm làm: …
   Review output rủi ro cao: … (coach/instructor/expert)
   Quyết định approve/dừng: …

5. DỮ LIỆU
   Dùng (mẫu/giả định trong lab): …
   Privacy / dẫn nguồn: …

6. NGÂN SÁCH (từng hạng mục)
   - API/tool: …
   - Thời gian người (kể cả đã có): …
   - Hạng mục ẩn (training/maintenance): …

7. THỜI GIAN + CỔNG
   Phase 1 (… tuần): … → cổng: …
   Phase 2 (… tuần): … → cổng: …

8. CHỈ SỐ THÀNH CÔNG
   | Chỉ số | Đo bằng gì · ai đo | Baseline | Ngưỡng đạt |
   Chỉ báo sớm: …

9. TIÊU CHÍ DỪNG (≥2 mức)
   | Mức | Điều kiện | Hành động | Ai có quyền dừng |
   - Cảnh báo: …
   - Nghiêm trọng: …

10. ADOPTION
    Ai dùng, công việc đổi sao: …
    Nếu không ai dùng: …

11. LỜI HỨA GIAO GÌ (realistic)
    …

12. LỜI XIN (rõ ràng)
    Xin: …
    Đổi lại hứa: …
    Mức rủi ro: …
```

---

## Ví dụ điền (KHÔNG phải đáp án — minh họa độ chi tiết cần đạt)

> Track giả định: Assessment & Rubric Engine. Quick Win giả định: review 5-slide AI Pilot Plan theo rubric, flag thiếu chỉ số/ngân sách/tiêu chí dừng. *Đây là ví dụ để thấy mức cụ thể — không phải lựa chọn đúng cho nhóm bạn.*

```text
1. TÓM TẮT VẤN ĐỀ
   Coach review bài nộp thủ công, không nhất quán giữa các coach, học viên không biết
   bài thiếu gì trước khi nộp.

2. CÁCH LÀM + LÝ DO
   Chọn: Boost (LLM có sẵn + rubric D28 + 10 bài cũ làm calibration).
   Vì: rubric đã có sẵn, không cần xây model riêng.
   Không Build vì: quá tốn cho 1 lát cắt; không Buy vì rubric đặc thù khóa học.

3. PHẠM VI PILOT
   Phục vụ: 10 nhóm track AI Product. Thời lượng: 3 tuần. 2 phase.

4. NGƯỜI
   Nhóm làm: 3 thành viên. Review output: 1 coach calibrate. Quyết định: lead coach.

5. DỮ LIỆU
   Dùng: 10 bài nộp mẫu (ẩn danh) + rubric D28. Không dùng dữ liệu học viên thật.
   Output luôn kèm trích mục rubric tương ứng.

6. NGÂN SÁCH
   - API: ~$X/tháng pilot (ước lượng từ số bài × token)
   - Thời gian người: coach 2h/tuần calibrate
   - Ẩn: 1 buổi train coach đọc feedback AI

7. THỜI GIAN + CỔNG
   Phase 1 (1 tuần): chạy trên 10 bài cũ, so AI vs coach → cổng: trùng khớp ≥70%?
   Phase 2 (2 tuần): chạy formative cho 10 nhóm → cổng: coach thấy tiết kiệm thời gian?

8. CHỈ SỐ
   - Trùng khớp AI vs coach trên bài cũ: đo thủ công, lead coach đo; baseline: chưa có;
     ngưỡng ≥70%.
   - Thời gian coach/bài: baseline ~20 phút; ngưỡng giảm ≥30%.
   Chỉ báo sớm: phản hồi coach sau 10 bài đầu (định tính).

9. TIÊU CHÍ DỪNG
   - Cảnh báo: trùng khớp 60–70% → review lại prompt/rubric.
   - Nghiêm trọng: trùng khớp <60% hoặc coach thấy feedback gây hiểu sai → dừng,
     quyền dừng: lead coach.

10. ADOPTION
    Học viên chạy tự kiểm trước khi nộp; coach dùng feedback draft làm điểm xuất phát.
    Nếu không ai dùng: gắn vào bước nộp bài như checklist tự nguyện, thu phản hồi vì sao.

11. LỜI HỨA
    Cuối 3 tuần giao báo cáo: trùng khớp thực tế, thời gian tiết kiệm, lỗi hay gặp —
    kể cả khi kết luận là NÊN DỪNG.

12. LỜI XIN
    Xin: 2h/tuần của 1 coach + ~$X API + 10 bài mẫu ẩn danh.
    Đổi lại: báo cáo bằng chứng sau 3 tuần để quyết mở rộng hay dừng.
    Mức rủi ro: thấp (formative, có người calibrate, không phải điểm chính thức).
```

---

## Tự kiểm trước khi đóng

- [ ] Tóm tắt vấn đề gói được trong **1 câu**
- [ ] Ngân sách **tách hạng mục**, có nghĩ tới hạng mục ẩn
- [ ] Chỉ số có **baseline + ngưỡng + ai đo**
- [ ] Tiêu chí dừng có **người có quyền thực thi**
- [ ] Lời xin **rõ**, lời hứa **realistic** (không over-promise)
- [ ] Tiêu chí dừng chặn được 2 Red Flags ghi ở `worksheet/00-context.md`

---

*Template AI Pilot Plan core · D28 · liên kết handbook §A7 + §A8.*

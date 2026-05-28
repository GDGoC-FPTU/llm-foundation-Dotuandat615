# Ngày 1 — Bài Tập & Phản Ánh
## Nền Tảng LLM API | Phiếu Thực Hành

**Thời lượng:** 1:30 giờ  
**Cấu trúc:** Lập trình cốt lõi (60 phút) → Bài tập mở rộng (30 phút)

---

## Phần 1 — Lập Trình Cốt Lõi (0:00–1:00)

Chạy các ví dụ trong Google Colab tại: https://colab.research.google.com/drive/172zCiXpLr1FEXMRCAbmZoqTrKiSkUERm?usp=sharing

Triển khai tất cả TODO trong `template.py`. Chạy `pytest tests/` để kiểm tra tiến độ.

**Điểm kiểm tra:** Sau khi hoàn thành 4 nhiệm vụ, chạy:
```bash
python template.py
```
Bạn sẽ thấy output so sánh phản hồi của GPT-4o và GPT-4o-mini.

---

## Phần 2 — Bài Tập Mở Rộng (1:00–1:30)

### Bài tập 2.1 — Độ Nhạy Của Temperature
Gọi `call_openai` với các giá trị temperature 0.0, 0.5, 1.0 và 1.5 sử dụng prompt **"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**

**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)
> Khi temperature tăng, câu trả lời trở nên đa dạng và sáng tạo hơn, còn temperature thấp cho câu trả lời ổn định và ít bất ngờ hơn. 0.0 thường rất chính xác và lặp lại, trong khi 1.5 có thể tạo ra nội dung thú vị nhưng ít dự đoán hơn và có thể xa đề hơn.

**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**
> Tôi sẽ chọn temperature khoảng 0.2–0.5 để giữ sự chính xác, nhất quán và giảm rủi ro tạo thông tin sai, trong khi vẫn duy trì phản hồi tự nhiên.

---

### Bài tập 2.2 — Đánh Đổi Chi Phí
Xem xét kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người thực hiện 3 lần gọi API, mỗi lần trung bình ~350 token.

**Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:**
> Với cùng lượng token, GPT-4o thường đắt hơn GPT-4o-mini khoảng 30–35 lần, vì chi phí token của GPT-4o cao hơn rất nhiều so với GPT-4o-mini.

**Mô tả một trường hợp mà chi phí cao hơn của GPT-4o là xứng đáng, và một trường hợp GPT-4o-mini là lựa chọn tốt hơn:**
> GPT-4o xứng đáng khi cần trả lời chính xác cho nội dung quan trọng, phức tạp, hoặc dịch vụ cao cấp như tư vấn pháp lý/đầu tư. GPT-4o-mini phù hợp khi cần phục vụ nhiều người dùng với chi phí nhỏ, ví dụ chatbot nội dung đơn giản, tự động hóa hỗ trợ kỹ thuật cơ bản hoặc trả lời FAQ.

---

### Bài tập 2.3 — Trải Nghiệm Người Dùng với Streaming
**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì non-streaming lại phù hợp hơn?** (1 đoạn văn)
> Streaming quan trọng khi người dùng cần phản hồi nhanh và cảm nhận liên tục, như trợ lý chat trực tiếp hoặc công cụ hỗ trợ khách hàng với nhiều câu hỏi. Non-streaming phù hợp hơn cho các tác vụ không gấp, khi cần kết quả đầy đủ một lần, ví dụ tạo báo cáo hoặc xử lý batch, để giảm phức tạp và tiêu thụ băng thông.


## Danh Sách Kiểm Tra Nộp Bài
- [ ] Tất cả tests pass: `pytest tests/ -v`
- [ ] `call_openai` đã triển khai và kiểm thử
- [ ] `call_openai_mini` đã triển khai và kiểm thử
- [ ] `compare_models` đã triển khai và kiểm thử
- [ ] `streaming_chatbot` đã triển khai và kiểm thử
- [ ] `retry_with_backoff` đã triển khai và kiểm thử
- [ ] `batch_compare` đã triển khai và kiểm thử
- [ ] `format_comparison_table` đã triển khai và kiểm thử
- [ ] `exercises.md` đã điền đầy đủ
- [ ] Sao chép bài làm vào folder `solution` và đặt tên theo quy định 

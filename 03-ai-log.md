# 03-ai-log.md — AI Thought-Partner Log

## Tóm tắt (1 đoạn)
Trong buổi Lab tôi dùng LLM như một thought‑partner để: brainstorm pain‑points vận hành, soạn ngôn từ cho worksheet, sinh Quick Problem Cards.

---

## AI giúp gì
- Brainstorm nhanh 5 pain‑points theo 4 lenses, giúp điền và tinh chỉnh `01-worksheet.md`.
- Viết và chỉnh 3 Quick Problem Cards (workflow, bottleneck, metric) để dùng trực tiếp trong Phase 2.
- Gợi ý kiến trúc kỹ thuật sơ bộ (rule vs LLM vs agent) và các metric đo thành công.

## AI sai gì (ít nhất một ví dụ)
- AI sinh ra các con số % cải thiện và ước tính thiệt hại mà không có nguồn dữ liệu, gây nguy cơ hiểu nhầm là dữ liệu thực tế.

## Sửa đổi ra sao (cụ thể)
- Sử dụng AI kết hợp tra cứu trên internet để đảm bảo số liệu chính xác và có nguồn rõ ràng.
## Lessons learned & Next steps
- Không dùng số liệu do model sinh làm baseline quyết định — phải thu thập logs vận hành để tính baseline.
- Luôn kèm validators, confidence thresholds và HITL cho mọi quy trình có rủi ro tài chính/an toàn.


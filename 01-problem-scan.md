
# 🔍 Phase 1 — SCAN (Cá nhân, 20 min)

Hãy sử dụng **4 Lenses** dưới đây để quét qua hoạt động vận hành của các công ty thành viên Vingroup. Ghi lại **ít nhất 5 bài toán/bottleneck** thực tế.

### 4 Lenses tìm bài toán AI cho Vingroup:
1. **Lặp lại (Repetitive):** Tác vụ lặp đi lặp lại nhiều lần hằng ngày. (Ví dụ: So khớp hóa đơn sạc điện tại VinFast, route lại chuyến taxi tại Xanh SM).
2. **Tốn thời gian (Time-consuming):** Tác vụ ngốn thời gian xử lý thủ công của nhân viên. (Ví dụ: Soạn thảo phản hồi đánh giá 1-star của cư dân Vinhomes).
3. **AI có thể tốt hơn (AI-upgrade):** Dịch vụ khách hàng hiện tại còn chậm hoặc phản hồi rập khuôn. (Ví dụ: Chatbot CSKH Vinpearl hỗ trợ đặt vé vui chơi).
4. **Pain từ người khác (Stakeholder Pain):** Bottleneck khiến khách hàng hoặc nhân viên thực địa phàn nàn. (Ví dụ: Tài xế Xanh SM phàn nàn về việc hệ thống gợi ý điểm đón khách không chính xác).

> [!TIP]
> **🤖 AI Prompts — Partner brainstorm:**
> Hãy sử dụng prompt sau để brainstorm các bài toán thực tế nếu bạn chưa có ý tưởng:
> *"Tôi là AI Engineer tại Vin Smart Future (Vingroup). Tôi đang tìm kiếm các pain point vận hành cụ thể có thể tối ưu bằng AI cho mảng [Chọn một: VinFast / Xanh SM / Vinhomes / Vinmec]. Hãy gợi ý cho tôi 5 quy trình nghiệp vụ thủ công, tốn nhiều thời gian và gây rò rỉ hiệu suất kèm con số thống kê ước tính về tổn thất."*

### 📝 List bài toán của tôi:
| # | Subsidiary (VinFast/Xanh SM...) | Lens | Mô tả ngắn bài toán |
|---|----------------------------------|------|---------------------|
| 1 | Vinhomes | Tốn thời gian (Time-consuming) | Người dân nấu nướng có hơi nước bốc lên cảm biến cháy khiến tạo ra báo động giả và kích hoạt hệ thống phun nước chữa cháy|
| 2 | Xanh SM | Tốn thời gian (Time-consuming) | Cuốc xe bắn cho tài xế xa làm tài xế phải di chuyển xa để đón khách |
| 3 | Vinhomes | AI có thể tốt hơn (AI-upgrade) | Hệ thống đèn điện có cảm biến tự động bật/tắt hiện đang hoạt động cả ban ngày, gây giảm tuổi thọ thiết bị và tăng chi phí bảo trì và sửa chữa|
| 4 | Vinmec | Tốn thời gian (Time-consuming) | Khách hàng đặt lịch trước nhưng đến nơi vẫn cần check-in để xác minh |
| 5 | Xanh SM | Pain từ người khác (Stakeholder Pain) | Ước tính thời gian di chuyển còn sai lệch khiến khách hàng phàn nàn về thông tin không chính xác |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #1                           │
│                                                             │
│ Bài toán (1 câu): Hơi nước và khói khi nấu ăn kích hoạt cảm biến   │
│ khói, gây báo động giả và có thể phun nước chữa cháy nhầm.  │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [x] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Cư dân (gián đoạn, thiệt hại tài sản), │
│ BQL/đội PCCC (xử lý liên tục), kỹ thuật (điều tra, reset).  │
│                                                             │
│ Workflow thủ công hiện tại (5 bước):                        │
│   1. Cư dân nấu ăn → hơi nướng chạm cảm biến khói          │
│   → 2. Hệ thống báo động, cảnh báo tòa / trung tâm giám sát│
│   → 3. BQL hoặc an ninh lên căn hộ xác minh thủ công        │
│   → 4. Tắt báo động, reset; có thể đã kích hoạt phun nước   │
│   → 5. Ghi sự cố, điều chỉnh cảm biến nếu lặp lại          │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2–3 (⏱ 15–25 phút/  │
│ lượt; rủi ro phun nhầm + chi phí PCCC giả)                  │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2 — phân loại   │
│ khói thật vs hơi nướng/nấu ăn trước khi báo động/phun.      │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                       │
│ Giảm tỷ lệ báo động giả từ ~40% sự cố khói/tháng ──> dưới  │
│ 10%; giảm thời gian xử lý mỗi sự cố từ 20 phút ──> dưới 5 phút.│
│                                                             │
│ Quick Architecture: [ ] No AI  [x] Rule  [ ] LLM  [] Agent │
│ (ML vision + rule đa cảm biến)        │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #2                             │
│                                                             │
│ Bài toán (1 câu): Cuốc xe gán cho tài xế ở xa điểm đón,    │
│ khiến tài xế chạy thêm km rỗng và khách chờ lâu.           │
│ Công ty thành viên: [ ] VinFast  [x] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Tài xế (km rỗng, pin), khách (chờ),    │
│ điều phối viên (phải đổi cuốc tay khi khiếu nại).           │
│                                                             │
│ Workflow thủ công hiện tại (4 bước):                        │
│   1. Khách đặt xe trên app                                  │
│   → 2. Hệ thống phân bổ cuốc (chưa tối ưu khoảng cách đón)  │
│   → 3. Tài xế di chuyển xa; khách theo dõi ETA trên app     │
│   → 4. CSKH/điều phối can thiệp hủy hoặc gán lại cuốc       │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2–3 (⏱ 8–15 phút     │
│ thêm/khách; tài xế ~3–8 km rỗng/cuốc)                       │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2 — Smart        │
│ Dispatch: ưu tiên tài xế gần, dự báo nhu cầu, mức pin.       │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                       │
│ Giảm khoảng cách tài xế→điểm đón TB từ 4.5 km ──> dưới 2 km;│
│ giảm thời gian chờ khách từ 12 phút ──> dưới 6 phút.        │
│                                                             │
│ Quick Architecture: [ ] No AI  [x] Rule  [ ] LLM  [] Agent │
│ (Rule scoring + ML dự báo)     │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #3 (SCAN #4)                             │
│                                                             │
│ Bài toán (1 câu): Bệnh nhân đã đặt lịch online nhưng đến   │
│ Vinmec vẫn phải xếp hàng check-in thủ công để xác minh lịch.│
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [x] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Bệnh nhân/người nhà (chờ lâu, trải     │
│ nghiệm kém), lễ tân (quá tải giờ cao điểm), bác sĩ (trễ lịch).│
│                                                             │
│ Workflow thủ công hiện tại (5 bước):                        │
│   1. Bệnh nhân đặt lịch qua app Vinmec / web / tổng đài     │
│   → 2. Đến bệnh viện, lấy số hoặc xếp hàng quầy lễ tân      │
│   → 3. Nhân viên tra cứu lịch trên HIS, đối chiếu CMND/CCCD │
│   → 4. In phiếu khám, hướng dẫn phòng; chờ gọi số           │
│   → 5. Y tá/phòng khám tiếp nhận và gọi vào khám              │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2–3 (⏱ 15–25 phút/  │
│ lượt giờ cao điểm; ~3–5% nhập/sai lịch do tra cứu tay)     │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2–3 — check-in   │
│ tự phục vụ (QR/mã đặt lịch), đồng bộ HIS real-time, chatbot  │
│ hướng dẫn phòng khám; lễ tân chỉ xử lý ngoại lệ.            │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                       │
│ Giảm thời gian chờ tại quầy từ 20 phút ──> dưới 5 phút; tỷ │
│ lệ check-in đúng lịch lần đầu từ 80% ──> trên 97%.           │
│                                                             │
│ Quick Architecture: [ ] No AI  [x] Rule  [x] LLM  [ ] Agent │
│ (Rule đồng bộ HIS + QR; LLM chatbot FAQ/hướng dẫn đến phòng) │
└─────────────────────────────────────────────────────────────┘
```

> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: [Dán nội dung]. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."*

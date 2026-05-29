# Lab 02 — Worksheet: AI Product Scoping (Vin Smart Future)

---

## 🏛️ 1. Bối cảnh thực tế: Vin Smart Future (Vingroup)

**Vingroup** — Tập đoàn tư nhân lớn nhất Việt Nam — vừa sáp nhập toàn bộ các phòng ban công nghệ thuộc các công ty thành viên thành một đơn vị công nghệ thống nhất mang tên **Vin Smart Future**. 

Nhiệm vụ của **Vin Smart Future** là xây dựng các giải pháp AI, số hóa, và tự động hóa cốt lõi để nâng cao hiệu suất vận hành và trải nghiệm khách hàng xuyên suốt các công ty thành viên:
* 🚗 **VinFast:** Hệ thống xe điện thông minh (EV), trợ lý AI ảo trong xe, dự đoán bảo trì pin, và quản lý chuỗi cung ứng sản xuất.
* 🚕 **Xanh SM (GSM):** Vận hành đội xe taxi/xe máy điện thông minh, điều vận thông minh (Smart Dispatching), tối ưu hóa lộ trình di chuyển.
* 🏢 **Vinhomes:** Quản lý đô thị thông minh (Smart Cities), trợ lý cư dân thông minh, tối ưu hóa mức tiêu thụ năng lượng.
* 🏥 **Vinmec:** Y tế thông minh, chẩn đoán hình ảnh bằng AI, tối ưu hóa quản lý hồ sơ bệnh án.
* 🎢 **Vinpearl / VinWonders:** Trải nghiệm du lịch số hóa, quản lý phòng và luồng khách thông minh tại các khu vui chơi.

Trong buổi Lab hôm nay, nhóm của bạn sẽ đóng vai trò là **AI Product Engineer** tại **Vin Smart Future**, tiến hành tìm kiếm, scoping, phân tích độ khả thi, thiết lập ranh giới vận hành, và xây dựng một **bản mẫu kỹ thuật (prompt prototype)** cho một bài toán cụ thể thuộc một trong những mảng kinh doanh trên.

---

## 📊 2. Cơ cấu tính điểm bài lab

### 👥 Điểm nhóm (60 điểm)

| Gate | Điểm | Deliverable | Tiêu chí chấm |
|---|---:|---|---|
| **G1. Workflow Mapping** | 20 | Problem Deep-Dive | Vẽ chi tiết quy trình hiện tại: các bước, handoff, thời gian, bottleneck |
| **G2. Problem Statement** | 20 | Problem Deep-Dive | Problem Statement 6-field bám sát thực tế, metric có số và ranh giới rõ ràng |
| **G3. AI Fit & Future Flow** | 10 | Problem Deep-Dive | So sánh Rule vs LLM vs Agent, future flow có bước AI, ranh giới và Fallback |
| **G4. Decision Quality** | 10 | Problem Deep-Dive | Quyết định Go/Not Yet/No-Go trung thực và có chứng cứ rõ ràng |

### 👤 Điểm cá nhân (40 điểm)

| Gate | Điểm | Deliverable | Tiêu chí chấm |
|---|---:|---|---|
| **I1. Scan & Cards** | 15 | Quick Cards | Liệt kê 5 problems sử dụng 3 lenses, hoàn thiện 3 quick cards chất lượng |
| **I2. Prototyping** | 10 | 02-lab/ | Chạy thử nghiệm programmatic prompt prototype thành công |
| **I3. AI Log & Reflection** | 15 | 03-ai-log.md | Phản ánh trung thực về việc dùng AI làm thought-partner (giúp gì, sai gì, sửa gì) |

---

# 🚀 Phase 0 — worked Example: Xanh SM Intelligent Dispatcher (15 min)

*Giảng viên walk-through ví dụ thực tế từ Vin Smart Future để bạn hiểu rõ cách scoping một bài toán AI.*
Đọc chi tiết worked example tại file [02-deliverable-example.md](02-deliverable-example.md).

---

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
| 1 | Vin Bus | Repetitive | Điều phối xe/tài xế theo thời gian thực dựa trên dữ liệu nhu cầu khách hàng cho mỗi tuyến |
| 2 | VinFast | Stakeholder Pain | Khó khăn tìm trạm đổi pin xe máy điện: AI gợi ý trạm đổi phù hợp hiện tại và chủ động đề xuất trạm tối ưu dựa trên lượng pin thực tế và lộ trình. |
| 3 | VinFast | Repetitive | Đối soát hóa đơn sạc, nhật ký xe và giao dịch thanh toán để phát hiện sai lệch, thiếu chứng từ hoặc trùng lặp nhanh hơn. |
| 4 | Vinhomes | AI-upgrade | Tự động thu thập review 1-sao từ cộng đồng cư dân, đồng thời gắn nhãn mức độ khẩn cấp để ưu tiên xử lý. |
| 5 | Vinmec | Stakeholder Pain | Trích xuất và tóm tắt hồ sơ bệnh án để bác sĩ tra cứu nhanh thông tin liên quan trước khi khám, giảm thời gian đọc hồ sơ thủ công. |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
### Completed Quick Problem Cards (top 3)

┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #1                                         │
│                                                               │
│ Bài toán (1 câu): Tối ưu điều phối tuyến/xe (Vin Bus) để giảm thao tác gán chuyến thủ công và thời gian chờ khách. │
│ Công ty thành viên: Vin Bus                                    │
│ Ai đang đau (Actor)? Ops/Dispatcher phụ trách điều phối tuyến và giám sát vận hành. │
│ Workflow thủ công hiện tại (3-5 bước):                        │
│   1. Thu thập dữ liệu cầu theo tuyến (logs, lượt đặt) ──> 2. So sánh nguồn lực (số xe, tài xế, ca trực) ──> 3. Gán chuyến/tuyến thủ công vào lịch ──> 4. Giám sát và sửa tay khi có ngoại lệ │
│ Bước nào tốn thời gian/lỗi nhất? Bước 3: gán chuyến và cân đối nguồn lực (⏱ ~8–15 phút/phiên điều chỉnh) │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2–3: dự đoán cầu, đề xuất phân bổ tối ưu và đưa ra danh sách gợi ý để ops chỉ cần phê duyệt. │
│ Đo thành công bằng gì (Metric có số)?                         │
│   - Giảm thời gian gán chuyến trung bình từ 12 phút → ≤3 phút (−75%). │
│   - Tăng tỷ lệ đáp ứng nhu cầu tuyến (fill-rate) +4–6%.       │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent    │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #2                                         │
│                                                               │
│ Bài toán (1 câu): Khách đi xe máy điện VinFast gặp khó khăn tìm trạm đổi pin; AI gợi ý trạm phù hợp hiện tại và chủ động đề xuất trạm tối ưu dựa trên lượng pin thực tế và lộ trình. │
│ Công ty thành viên: VinFast                                   │
│ Ai đang đau (Actor)? Khách hàng lái xe máy điện VinFast và đội ngũ vận hành trạm. │
│ Workflow thủ công hiện tại (3-5 bước):                        │
│   1. Khách hàng nhận thấy xe máy điện sắp hết pin ──> 2. Phải dừng xe bên đường tra cứu bản đồ trạm pin trên app ──> 3. Tự ước tính quãng đường còn đi được và khả năng đáp ứng pin sạc đầy của trạm ──> 4. Di chuyển tới trạm đổi pin │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2-3: Dừng xe tra cứu và tự tính toán/dự báo trạm pin tối ưu (⏱ ~5–8 phút/lần) │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Giám sát dung lượng pin thời gian thực và tự động gợi ý trạm đổi pin phù hợp; chủ động đề xuất trạm tối ưu dựa trên lộ trình đi tiếp. │
│ Đo thành công bằng gì (Metric có số)?                         │
│   - Giảm tỷ lệ xe máy điện hết pin giữa đường xuống <0.05%.   │
│   - Giảm thời gian tìm kiếm và chọn trạm đổi pin từ 8 phút → <15 giây (chủ động đề xuất trên app/màn hình xe). │
│   - Tăng chỉ số hài lòng CSAT về dịch vụ đổi pin lên >95%.    │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent    │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #3                                         │
│                                                               │
│ Bài toán (1 câu): Tự động đối soát hóa đơn sạc và giao dịch thanh toán VinFast để phát hiện sai lệch/tính phí trùng lặp nhanh hơn. │
│ Công ty thành viên: VinFast                                   │
│ Ai đang đau (Actor)? Nhân viên kế toán/finance và ops quản lý trạm sạc. │
│ Workflow thủ công hiện tại (3-5 bước):                        │
│   1. Gom file hóa đơn và logs giao dịch ──> 2. So khớp hóa đơn vs. logs sử dụng (mã xe, thời gian, số tiền) ──> 3. Đánh dấu bất thường, mở ticket điều tra ──> 4. Hoàn thiện đối soát và booking ghi sổ │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2–3: khớp và xử lý ngoại lệ (⏱ ~20–90 phút/case tùy phức tạp) │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Trích xuất thông tin từ hóa đơn (OCR + NER), tự động so khớp với logs và gắn nhãn anomalies để giảm thao tác thủ công. │
│ Đo thành công bằng gì (Metric có số)?                         │
│   - Tự động khớp 90% giao dịch không cần can thiệp người.     │
│   - Giảm thời gian xử lý exception trung bình từ 45 phút → ≤12 phút. │
│   - Giảm lỗi đối soát gây trễ báo cáo xuống <1%.               │
│ Quick Architecture: [ ] No AI  [x] Rule  [ ] LLM  [ ] Agent    │
└─────────────────────────────────────────────────────────────┘

```

> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: [Dán nội dung]. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."*

---

# 🏗️ Phase 3 — DEEP-DIVE (Nhóm, 85 min)

## 3.1. Current-State Workflow Mapping (25 min)
**Vẽ quy trình hiện tại lên bảng/giấy A3.** Sử dụng các ký hiệu:
* 🔴 **Bottleneck:** Bước gây tắc nghẽn, tốn thời gian, hoặc sai sót nhiều nhất.
* 🔄 **Handoff:** Điểm chuyển giao thông tin giữa người và hệ thống, hoặc giữa các bộ phận.
* Ghi rõ thời gian vận hành trung bình: **Tổng cộng = ____ phút/lượt**.

## 3.2. Problem Statement (6-field) & Metrics (15 min)
Điền đầy đủ 6 trường thông tin của bài toán:

| Field | Nội dung chi tiết |
|---|---|
| **1. Actor / Operator** | Ai đang thực hiện tác vụ hằng ngày? |
| **2. Current Workflow** | Mô tả tóm tắt quy trình thủ công hiện tại và công cụ sử dụng. |
| **3. Bottleneck** | Bước nào chậm, lỗi, hoặc cần xử lý ngôn ngữ tự động nhiều nhất? |
| **4. Business Impact** | Tổn thất thực tế đo bằng thời gian, chi phí, hoặc SLA của Vingroup. |
| **5. Success Metric** | AI giải quyết được thì đạt ngưỡng số mấy? (Ví dụ: *"85% vé được phân loại dưới 10s"*). |
| **6. Operational Boundary** | AI được phép làm gì, TUYỆT ĐỐI không được làm gì, điểm nào cần duyệt? |

## 3.3. Future-State Flow & AI Fit (25 min)
* **Xác định mức AI Fit (AI-Fit Matrix):** Giải pháp thuộc nhóm nào? [ ] Rule / State-Machine [ ] LLM Feature [ ] Agentic Loop.
* **Vẽ Future-State Flow:** Đánh dấu rõ:
  * 🔵 **AI Step:** Tác vụ LLM xử lý.
  * 🟢 **Human Step (HITL):** Bước con người phê duyệt/review (Human-in-the-loop).
  * ↩️ **Fallback:** Kế hoạch dự phòng khi LLM trả về kết quả lỗi hoặc không tự tin.

---

# 💻 Phase 4 — TECHNICAL PROMPT PROTOTYPE (Nhóm, 30 min)

Để đảm bảo kỹ sư của Vin Smart Future luôn giữ vững năng lực lập trình, nhóm của bạn sẽ tiến hành **lập trình bản mẫu prompt** trực tiếp trên **Gemini 2.5 Flash** bằng Python để stress-test hệ thống.

### Hướng dẫn thực hiện:
1. Mở file [starter-code/prompt_prototype.py](starter-code/prompt_prototype.py) bằng VS Code/Cursor.
2. Hoàn thiện các nội dung sau:
   * **System Prompt:** Viết chỉ thị cực kỳ nghiêm ngặt quy định vai trò, nhiệm vụ, định dạng output và **Operational Boundary (Ranh giới cấm)** của mô hình.
   * **Structured Output:** Định nghĩa định dạng JSON output rõ ràng.
   * **Adversarial Test Cases:** Viết ít nhất 3 prompts "tấn công" (Adversarial inputs) cố tình dụ AI vượt ranh giới hoặc đưa ra câu trả lời không được phép để kiểm tra xem ranh giới của bạn có thực sự vững chắc.
3. Chạy file python:
   ```bash
   python3 prompt_prototype.py
   ```
4. Kiểm tra xem các ranh giới an toàn có bị LLM phá vỡ hay không và ghi lại kết quả vào worksheet.

---

# 🏁 Phase 5 — EVALUATE (Nhóm, 20 min)

### AI Readiness Checklist:
1. [ ] Chúng tôi có sẵn dữ liệu mẫu/logs sạch để test?
2. [ ] Rủi ro khi AI sai có nằm trong tầm kiểm soát (qua HITL hoặc Fallback)?
3. [ ] Stakeholders sẵn sàng thay đổi quy trình làm việc cũ?

### Quyết định cuối cùng của Ban Giám Đốc Vin Smart Future:
[ ] **GO (Bắt đầu xây dựng Prototype):** Bắt đầu phát triển với scope hẹp.
[ ] **NOT YET (Cần tích lũy thêm dữ liệu/xác lập baseline):** Trì hoãn để chuẩn bị thêm.
[ ] **NO-GO (Không khả thi / Rule-based tốt hơn):** Hủy bỏ dự án AI này.

**Justification (Lý giải quyết định dựa trên bằng chứng kỹ thuật và chi phí):**
> *Viết lý giải chi tiết tại đây*

---

# 📝 Phase 6 — REFLECTION (Cá nhân)
*Ghi nhận phản ánh của cá nhân bạn về việc phối hợp với AI trong buổi học hôm nay vào file `03-ai-log.md`.*

# Compliance Audit V2 — StockFund AI

> Audit nội bộ phục vụ Day 22. Tài liệu này dựa trên các file trong repo và **khung luật/điều khoản được nêu trong `Requirements.md` của workshop**. Đây không phải ý kiến pháp lý chính thức; trước khi public hoặc launch nên có luật sư fintech/privacy review lại.

## 1. Nguồn đã rà soát

- PRD / product scope: [B-.md](../Nguyen_Quoc_Nam-2A202600201-Day17/B-.md), [A-Version.md](../Nguyen_Quoc_Nam-2A202600201-Day17/A-Version.md)
- Marketing materials: [pitch_memo.md](../Day_19/pitch_memo.md), [twitter_pitch.md](../Day_19/twitter_pitch.md), [ai_vc_critique_log.md](../Day_19/ai_vc_critique_log.md)
- Tech stack / vendor / roadmap: [dependency_map.md](../Nguyen_Quoc_Nam-2A202600201-Day17/Day_20/dependency_map.md), [roadmap_nnl.md](../Nguyen_Quoc_Nam-2A202600201-Day17/Day_20/roadmap_nnl.md)
- Risk / control / incident docs: [risk_register_v2.md](../Day_21/risk_register_v2.md), [rules_rails_ritual.md](../Day_21/rules_rails_ritual.md), [incident_playbook.md](../Day_21/incident_playbook.md)
- Workshop outputs Day 22: [marketing_claims_audit.md](./marketing_claims_audit.md), [territorial_scope.md](./territorial_scope.md), [document_trail.md](./document_trail.md)

## 2. Kết luận nhanh

- **Tổng số vi phạm/rủi ro compliance chính:** **7**
- **Đủ 4 nhóm theo prompt:** **3 marketing (Kera), 2 dữ liệu cá nhân (PDPL/CIC), 1 phân loại AI, 1 vendor/partner-payment (Pips)**
- **Điểm đỏ nhất hiện tại:** startup đang public hình ảnh “AI advisor” và hiệu quả đầu tư, trong khi luồng dữ liệu cá nhân, vendor nước ngoài và hồ sơ phân loại AI chưa được chuẩn hóa.

## 3. Danh sách vi phạm chi tiết

### VI PHẠM 1: Claim “bớt thua lỗ / đầu tư thông minh hơn” vượt quá bằng chứng đang có

- **Luật áp dụng:** Bộ luật Hình sự VN
- **Điều:** **Điều 198** theo khung workshop về hành vi quảng cáo/selling gây hiểu lầm
- **Bằng chứng trong sản phẩm:** [twitter_pitch.md](../Day_19/twitter_pitch.md), [pitch_memo.md](../Day_19/pitch_memo.md)
- **Trích nguyên văn:**
  - “Giúp nhà đầu tư F0 Việt Nam bớt thua lỗ bằng AI ‘coach hành vi’ đầu tư”
  - “StockFund AI giúp nhà đầu tư mới đầu tư thông minh hơn, kỷ luật hơn”
- **Pattern khớp với:** **Kera** — dùng ngôn ngữ outcome mạnh hơn mức bằng chứng có thật
- **Đánh giá:** **Nghiêm trọng cao**. Đây là claim public-facing, rủi ro xảy ra ngay khi chạy landing page/bài pin.
- **Hành động sửa trong 1 tuần:**
  1. Đổi toàn bộ outcome promise sang wording hỗ trợ/hướng dẫn, không hứa kết quả đầu tư.
  2. Thêm disclaimer “không phải khuyến nghị đầu tư, không cam kết lợi nhuận/giảm lỗ”.
  3. Chỉ cho phép public claim sau khi có evidence register và người duyệt ký tên.
- **Deadline:** **2026-05-12**

### VI PHẠM 2: Public số 65% / 82% / 4.8x mà không có hồ sơ chứng minh gốc

- **Luật áp dụng:** Bộ luật Hình sự VN
- **Điều:** **Điều 198** theo khung workshop
- **Bằng chứng trong sản phẩm:** [twitter_pitch.md](../Day_19/twitter_pitch.md), [pitch_memo.md](../Day_19/pitch_memo.md)
- **Trích nguyên văn:**
  - “Pilot 80 users: giảm 65% trade cảm tính, 82% giữ app. LTV/CAC=4.8x.”
  - “Hiệu suất danh mục trung bình cải thiện rõ rệt sau 2 tháng.”
- **Pattern khớp với:** **Kera** — lấy con số hấp dẫn làm bằng chứng marketing nhưng không kèm raw proof, mẫu đo hay điều kiện đo
- **Đánh giá:** **Nghiêm trọng cao**. Nếu bị hỏi nguồn mà không xuất trình được, startup rất yếu cả về pháp lý lẫn niềm tin nhà đầu tư.
- **Hành động sửa trong 1 tuần:**
  1. Tạm gỡ toàn bộ metric khỏi copy public.
  2. Dựng phụ lục “pilot evidence pack”: raw cohort, định nghĩa metric, thời gian đo, sample note.
  3. Chỉ re-publish số nào có dữ liệu gốc, owner chịu trách nhiệm và câu chữ có qualifier.
- **Deadline:** **2026-05-12**

### VI PHẠM 3: Định vị “AI tư vấn cổ phiếu cá nhân hóa” mâu thuẫn với PRD “không khuyến nghị mua/bán”

- **Luật áp dụng:** Bộ luật Hình sự VN + kiểm soát claim marketing
- **Điều:** **Điều 198** theo khung workshop
- **Bằng chứng trong sản phẩm:** [pitch_memo.md](../Day_19/pitch_memo.md), [B-.md](../Nguyen_Quoc_Nam-2A202600201-Day17/B-.md)
- **Trích nguyên văn:**
  - “StockFund AI là ứng dụng AI tư vấn cổ phiếu cá nhân hóa”
  - “Gợi ý giảm về 35% và đa dạng sang tiêu dùng & công nghệ để cân bằng.”
  - Trong PRD Day 17: “❌ Không tự động gợi ý mua/bán”
- **Pattern khớp với:** **Kera** — capability inflation và message không nhất quán giữa product thật với copy bán hàng
- **Đánh giá:** **Nghiêm trọng cao**. Đây là điểm vừa marketing-risk vừa regulatory-risk.
- **Hành động sửa trong 1 tuần:**
  1. Chốt một positioning duy nhất: công cụ giải thích dữ liệu/cảnh báo rủi ro, không phải “advisor”.
  2. Xóa ví dụ phân bổ tỷ trọng cá nhân hóa khỏi public copy.
  3. Tạo checklist approval để mọi tài liệu pitch phải đối chiếu lại PRD trước khi ra ngoài.
- **Deadline:** **2026-05-12**

### VI PHẠM 4: Chuyển dữ liệu cá nhân/tài chính ra nước ngoài mà chưa có hồ sơ đánh giá tác động

- **Luật áp dụng:** Luật/Bộ quy tắc bảo vệ dữ liệu cá nhân theo khung workshop
- **Điều:** **PDPL Điều 8** và nhóm nghĩa vụ đánh giá/chuyển dữ liệu theo yêu cầu workshop (tham chiếu thêm yêu cầu “Điều 30” trong prompt)
- **Bằng chứng trong sản phẩm:** [pitch_memo.md](../Day_19/pitch_memo.md), [dependency_map.md](../Nguyen_Quoc_Nam-2A202600201-Day17/Day_20/dependency_map.md), [rules_rails_ritual.md](../Day_21/rules_rails_ritual.md)
- **Trích nguyên văn:**
  - “Đồng bộ tự động với tài khoản chứng khoán và ngân hàng qua Open Banking & API”
  - “Xây dựng model-agnostic pipeline — switch giữa Gemini ↔ Claude ↔ GPT-4o”
  - “Helicone.ai log toàn bộ request/response”
- **Pattern khớp với:** **CIC** — dữ liệu nhạy cảm đi qua nhiều bên nhưng founder chưa có hồ sơ tập trung chứng minh đã thẩm định luồng đó
- **Đánh giá:** **Critical**. Đây là vi phạm/rủi ro có thể chạm ngay dữ liệu tài chính và danh mục cá nhân.
- **Hành động sửa trong 1 tuần:**
  1. Lập data inventory + transfer map: dữ liệu nào đi qua vendor nào, ở nước nào, lưu bao lâu.
  2. Viết hồ sơ đánh giá tác động chuyển dữ liệu ra nước ngoài và legal notice/consent tương ứng.
  3. Không cho broker/bank sync vào beta công khai cho tới khi hoàn tất bộ hồ sơ này.
- **Deadline:** **2026-05-19**

### VI PHẠM 5: Log prompt/response thô qua Helicone và fallback multi-model mà chưa có data minimization/retention policy

- **Luật áp dụng:** Luật/Bộ quy tắc bảo vệ dữ liệu cá nhân theo khung workshop
- **Điều:** **PDPL Điều 8** và nghĩa vụ bảo vệ dữ liệu tối thiểu theo logic workshop
- **Bằng chứng trong sản phẩm:** [rules_rails_ritual.md](../Day_21/rules_rails_ritual.md), [dependency_map.md](../Nguyen_Quoc_Nam-2A202600201-Day17/Day_20/dependency_map.md)
- **Trích nguyên văn:**
  - “Log toàn bộ request/response của Gemini/Claude API”
  - “Nếu Gemini quá đắt → chuyển sang Claude 3.5 Sonnet”
- **Pattern khớp với:** **CIC** — quá nhiều bản sao dữ liệu nhạy cảm tồn tại trong log, monitoring và vendor fallback
- **Đánh giá:** **Nghiêm trọng cao**. Ngay cả khi claim marketing được sửa, dữ liệu vẫn đang đi qua quá nhiều điểm.
- **Hành động sửa trong 1 tuần:**
  1. Mask hoặc tách thông tin định danh, account ID và holdings trước khi gửi vào log/observability.
  2. Đặt retention ngắn cho log AI; mặc định không lưu prompt thô nếu không thật sự cần debug.
  3. Tạo chế độ “redacted tracing” cho production, chỉ cho phép raw trace ở môi trường kiểm thử có kiểm soát.
- **Deadline:** **2026-05-19**

### VI PHẠM 6: Chưa phân loại chính thức hệ thống AI dù sản phẩm tác động trực tiếp tới quyết định tài chính cá nhân

- **Luật áp dụng:** Luật AI Việt Nam theo khung workshop
- **Điều:** **Điều 9**
- **Bằng chứng trong sản phẩm:** [pitch_memo.md](../Day_19/pitch_memo.md), [B-.md](../Nguyen_Quoc_Nam-2A202600201-Day17/B-.md), [territorial_scope.md](./territorial_scope.md)
- **Trích nguyên văn:**
  - “AI tư vấn cổ phiếu cá nhân hóa”
  - “phân tích danh mục, mức độ rủi ro và mục tiêu cá nhân”
  - “gửi ‘Báo cáo Sức khỏe Danh mục’”
- **Pattern khớp với:** Vi phạm phân loại AI — sản phẩm đang hoạt động như hệ thống ảnh hưởng quyết định tài chính, nhưng hồ sơ hiện tại mới dừng ở kỹ thuật/control rời rạc
- **Đánh giá:** **Critical**. Nếu không phân loại đúng từ đầu, mọi control sau đó sẽ lệch.
- **Hành động sửa trong 1 tuần:**
  1. Tự phân loại sản phẩm ở mức rủi ro cao khi còn giữ messaging “AI advisor”.
  2. Hoặc thu hẹp MVP xuống “tóm tắt dữ liệu công khai + citation + no recommendation” để giảm mức rủi ro.
  3. Tạo AI classification register: scope, use-case cấm, human override, review cadence.
- **Deadline:** **2026-05-22**

### VI PHẠM 7: Hứa hẹn tích hợp broker/bank/API và lớp insight qua nhiều vendor nhưng chưa có hồ sơ thẩm định đối tác

- **Luật áp dụng:** Bộ luật Hình sự VN + kiểm soát vendor/partner-payment theo khung workshop
- **Điều:** **Điều 324** theo nhóm pattern “vendor/payment/intermediary risk” trong brief Day 22
- **Bằng chứng trong sản phẩm:** [pitch_memo.md](../Day_19/pitch_memo.md), [dependency_map.md](../Nguyen_Quoc_Nam-2A202600201-Day17/Day_20/dependency_map.md), [risk_register_v2.md](../Day_21/risk_register_v2.md)
- **Trích nguyên văn:**
  - “Đồng bộ tự động với tài khoản chứng khoán và ngân hàng qua Open Banking & API”
  - “Tích hợp sâu API với 5 công ty chứng khoán & ngân hàng lớn nhất”
  - “Core asset = insight layer + behavior intelligence”
- **Pattern khớp với:** **Pips** — tạo cảm giác hợp pháp/tin cậy nhờ lớp trung gian tài chính và đối tác, trong khi hồ sơ kiểm soát vendor thực tế chưa tồn tại
- **Đánh giá:** **Nghiêm trọng cao**. Đây là loại rủi ro dễ bị bỏ sót vì nằm giữa product, legal và BD.
- **Hành động sửa trong 1 tuần:**
  1. Cấm public claim tên loại tích hợp/đối tác cho tới khi có hợp đồng hoặc LOI thật.
  2. Dựng vendor due diligence pack: legal entity, data country, DPA, SLA, incident notice, subprocessor list.
  3. Tách rõ “đã có”, “đang thử”, “định hướng” trong mọi tài liệu gọi vốn/marketing.
- **Deadline:** **2026-05-22**

## 4. Top 5 vi phạm nghiêm trọng nhất và 3 hành động sửa mỗi cái

| Ưu tiên | Vi phạm | Vì sao nghiêm trọng | 3 hành động sửa |
|---|---|---|---|
| 1 | **Vi phạm 4 — Chuyển dữ liệu ra nước ngoài chưa có hồ sơ** | Chạm trực tiếp dữ liệu tài chính/danh mục cá nhân và nhiều vendor nước ngoài | 1) Hoàn tất transfer map. 2) Làm impact assessment + consent text. 3) Chặn broker/bank sync trước khi đủ hồ sơ. |
| 2 | **Vi phạm 6 — Chưa phân loại AI chính thức** | Sai ở tầng phân loại thì toàn bộ control sau đó dễ lệch | 1) Chốt mức rủi ro. 2) Thu hẹp hoặc chỉnh positioning. 3) Mở AI classification register. |
| 3 | **Vi phạm 1 — Claim “bớt thua lỗ”** | Đây là claim dễ gây phản ứng pháp lý và niềm tin nhất khi public | 1) Gỡ promise kết quả. 2) Thêm disclaimer chuẩn. 3) Áp quy trình duyệt claim. |
| 4 | **Vi phạm 2 — Metric 65% / 82% / 4.8x không có proof pack** | Bị hỏi bằng chứng là vỡ ngay cả ở góc marketing lẫn fundraising | 1) Gỡ metric khỏi copy. 2) Build pilot evidence pack. 3) Chỉ republish metric có raw data. |
| 5 | **Vi phạm 7 — Vendor/partner claims chưa có hồ sơ đối tác** | Dễ trượt sang “mượn uy tín đối tác” và làm xấu thêm rủi ro PDPL | 1) Cấm public claim đối tác chưa ký. 2) Build vendor due diligence pack. 3) Phân tầng rõ trạng thái tích hợp. |

## 5. Đối chiếu thủ công với Workshop 1 + 2 + 3

| Loại vi phạm | Workshop liên quan | Kết quả đối chiếu |
|---|---|---|
| Marketing thổi phồng | Workshop 1 | WS1 đã bắt đúng phần claim outcome, metric và “AI advisor”; audit V2 bổ sung thêm điểm mâu thuẫn giữa PRD và copy public |
| Dữ liệu cá nhân / chuyển dữ liệu | Workshop 2 | WS2 xác nhận PDPL chắc chắn áp dụng; audit V2 chỉ ra rõ nhất hai luồng đỏ: broker/bank sync và prompt/log đi qua vendor nước ngoài |
| Tăng rủi ro AI | Workshop 2 | WS2 xếp mức **cao** là hợp lý; audit V2 củng cố bằng các câu chữ đang tác động trực tiếp tới quyết định tài chính |
| Vendor/thanh toán/đối tác | Workshop 3 + Dependency Map | Điểm AI/manual dễ bỏ sót nhất là “Open Banking & API” đang được dùng như trust signal nhưng chưa có gói thẩm định vendor |
| Hồ sơ founder | Workshop 3 | Khoảng trống lớn nhất hiện tại không phải thiếu playbook incident, mà là thiếu hồ sơ dữ liệu cá nhân và vendor diligence |

## 6. Kết luận cuối

- Nếu chỉ sửa một lớp duy nhất, hãy sửa **copy public** ngay vì đó là nơi rủi ro phát nổ nhanh nhất.
- Nếu chỉ build một bộ hồ sơ duy nhất trong 1 tuần tới, hãy build **hồ sơ dữ liệu cá nhân + chuyển dữ liệu ra nước ngoài**.
- Nếu muốn giữ positioning “AI advisor”, startup nên tự quản trị như **hệ thống AI rủi ro cao**; nếu không, nên hạ scope messaging về “giải thích dữ liệu công khai + citation + no recommendation”.

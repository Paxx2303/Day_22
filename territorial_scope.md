# Territorial Scope — Day 22

> Tài liệu trả lời 3 câu hỏi phạm vi áp dụng theo workshop. Phần kết luận dưới đây dựa trên tài liệu trong repo, không thay thế tư vấn pháp lý chính thức.

## 1. Có user EU không? Có kế hoạch mở EU trong 12 tháng tới không?

### Bằng chứng hiện có

- Tất cả persona và kênh phân phối đều đang khóa vào Việt Nam: “nhà đầu tư cá nhân Việt Nam”, “HN & HCM”, “StockTalk, Facebook groups, YouTube finance channels” — xem [B-.md](../Nguyen_Quoc_Nam-2A202600201-Day17/B-.md), [pitch_memo.md](../Day_19/pitch_memo.md).
- Roadmap hiện tập trung vào PDF BCTC Việt Nam, benchmark ngành Việt Nam và rủi ro đặc thù Việt Nam — xem [roadmap_nnl.md](../Nguyen_Quoc_Nam-2A202600201-Day17/Day_20/roadmap_nnl.md).
- Không thấy tài liệu nào trong repo nói tới website tiếng Anh, hỗ trợ EUR, legal rep tại EU, hay kế hoạch GTM vào EU trong 12 tháng.

### Kết luận

**EU AI Act: KHÔNG phải phạm vi chính ở trạng thái tài liệu hiện tại.**

Lý do: hiện chưa có dấu hiệu sản phẩm nhắm người dùng EU hoặc mở thị trường EU trong 12 tháng tới. Tuy nhiên, cần gắn cờ review lại ngay khi có một trong ba trigger sau:

- Có user cư trú tại EU đăng ký hoặc tham gia beta.
- Bắt đầu chạy ads/landing page tiếng Anh cho EU.
- Dùng đối tác phân phối có user base tại EU.

## 2. Startup đang xử lý những loại dữ liệu cá nhân nào tại Việt Nam? Có chuyển dữ liệu ra nước ngoài không?

### 5 loại dữ liệu cá nhân đang/định xử lý

| Loại dữ liệu | Dấu hiệu trong repo | Nhận định |
|---|---|---|
| Dữ liệu định danh và liên hệ | Pilot users, beta testers, founder liên hệ trực tiếp user trong [pitch_memo.md](../Day_19/pitch_memo.md) và [incident_playbook.md](../Day_21/incident_playbook.md) | Có khả năng xử lý tên, email, số điện thoại, user ID |
| Dữ liệu tài khoản tài chính | “Đồng bộ tự động với tài khoản chứng khoán và ngân hàng qua Open Banking & API” — [pitch_memo.md](../Day_19/pitch_memo.md) | Rất nhạy cảm; cần coi là dữ liệu ưu tiên kiểm soát |
| Dữ liệu danh mục và giao dịch | “Phân tích danh mục”, “giảm 65% trade cảm tính”, “FOMO” — [pitch_memo.md](../Day_19/pitch_memo.md), [twitter_pitch.md](../Day_19/twitter_pitch.md) | Bao gồm holdings, tỷ trọng, lịch sử giao dịch, hành vi mua bán |
| Dữ liệu hồ sơ đầu tư cá nhân | “mức độ rủi ro và mục tiêu cá nhân” — [pitch_memo.md](../Day_19/pitch_memo.md) | Thể hiện risk tolerance, mục tiêu tài chính, sở thích đầu tư |
| Log hành vi / prompt / response | Helicone log toàn bộ request-response và AI middleware trong [rules_rails_ritual.md](../Day_21/rules_rails_ritual.md) | Có thể chứa lại dữ liệu danh mục, hành vi và suy luận nhạy cảm |

### Có chuyển dữ liệu ra nước ngoài không?

**CÓ, theo logic vận hành hiện tại.**

Các dấu hiệu mạnh nhất:

- Stack dùng **Gemini**, có fallback sang **Claude** và **GPT-4o** — xem [dependency_map.md](../Nguyen_Quoc_Nam-2A202600201-Day17/Day_20/dependency_map.md).
- Log/observability dùng **Helicone.ai** — xem [rules_rails_ritual.md](../Day_21/rules_rails_ritual.md).
- Nếu prompt chứa dữ liệu danh mục, lịch sử giao dịch hoặc mục tiêu cá nhân, dữ liệu đó rất có thể đi qua hạ tầng vendor nước ngoài.

### Kết luận

**PDPL áp dụng: CÓ.**

**Có khả năng cần hồ sơ đánh giá tác động chuyển dữ liệu ra nước ngoài: CÓ.**

Việc cần làm ngay:

1. Lập data inventory: dữ liệu nào đi vào model, log, analytics và support tools.
2. Gắn legal basis/notice/consent cho các luồng broker-bank-account, portfolio, prompt logging.
3. Tách dữ liệu định danh ra khỏi prompt khi không cần thiết; áp retention tối thiểu cho log AI.

## 3. Sản phẩm có làm tăng rủi ro theo Luật AI Việt Nam không?

### Kết luận

**Mức rủi ro: CAO.**

### Lập luận 1 câu

Tài liệu marketing hiện mô tả sản phẩm như một hệ thống **“AI tư vấn cổ phiếu cá nhân hóa”**, **phân tích danh mục, mức độ rủi ro và mục tiêu cá nhân**, thậm chí đưa ví dụ **gợi ý cơ cấu lại tỷ trọng**, nên hệ thống đang tác động trực tiếp tới quyết định tài chính cá nhân chứ không còn là công cụ tóm tắt nội dung thuần túy.

### Hệ quả vận hành

- Nếu giữ messaging hiện tại, startup nên tự quản trị như một hệ thống AI rủi ro cao.
- Nếu muốn giảm rủi ro, cần hạ scope về “giải thích dữ liệu công khai + citation + không khuyến nghị mua/bán”.

## 4. 4 deadline cụ thể cần note vào Notion

| Deadline | Việc phải xong | Owner đề xuất | Vì sao |
|---|---|---|---|
| **2026-05-12** | Chốt lại toàn bộ copy marketing: bỏ hoặc làm mềm các claim “bớt thua lỗ”, “AI tư vấn cổ phiếu cá nhân hóa”, “65%/82%/4.8x” nếu chưa có bằng chứng gốc | Founder + Product | Đây là điểm rủi ro public nhanh nhất |
| **2026-05-15** | Hoàn tất bản đồ dữ liệu cá nhân + vendor map + danh sách nơi dữ liệu đi qua (Gemini/Claude/GPT/Helicone/broker API) | Founder + Tech Lead | Là nền cho mọi việc PDPL và vendor review |
| **2026-05-19** | Hoàn tất hồ sơ đánh giá chuyển dữ liệu ra nước ngoài + notice/consent text + chính sách retention log AI | Founder + Legal reviewer | Đây là khoảng trống pháp lý lớn nhất hiện tại |
| **2026-05-22** | Chốt phân loại hệ thống AI, danh sách control bắt buộc, và gói hồ sơ founder evidence pack trước beta/launch | Founder + Product + Legal reviewer | Để tránh vừa build vừa phát ngôn sai phạm |

## Kết luận ngắn

- **EU AI Act:** chưa phải phạm vi chính hiện tại.
- **PDPL:** chắc chắn có liên quan, và luồng chuyển dữ liệu ra nước ngoài là điểm đỏ.
- **Luật AI VN:** nên tự xem đây là hệ thống rủi ro cao nếu vẫn giữ messaging “AI advisor” và phân tích danh mục cá nhân hóa.

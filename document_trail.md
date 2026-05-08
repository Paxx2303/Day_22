# Document Trail — Day 22

> Mục tiêu: biến compliance từ “nói miệng” thành bộ hồ sơ founder có thể xuất trình khi cần. Bảng dưới đây dùng đúng tinh thần workshop: cái gì đã có thì link lại, cái gì chưa có thì gắn deadline build.

## Bảng 5 loại hồ sơ

| Loại hồ sơ | Trạng thái | Link hiện có / Deadline build | Ghi chú |
|---|---|---|---|
| 1. Hồ sơ claim marketing và bằng chứng công bố | ❌ **Chưa có bản chuẩn** | Hiện chỉ có materials thô: [pitch_memo.md](../Day_19/pitch_memo.md), [twitter_pitch.md](../Day_19/twitter_pitch.md), [marketing_claims_audit.md](./marketing_claims_audit.md). Deadline build bản evidence register: **2026-05-12** | Đang thiếu bảng đối chiếu claim ↔ raw proof ↔ người duyệt trước khi public |
| 2. Hồ sơ dữ liệu cá nhân + data flow + chuyển dữ liệu ra nước ngoài | ❌ **Chưa có** | Có dữ liệu rải rác ở [dependency_map.md](../Nguyen_Quoc_Nam-2A202600201-Day17/Day_20/dependency_map.md), [rules_rails_ritual.md](../Day_21/rules_rails_ritual.md), [territorial_scope.md](./territorial_scope.md). Deadline build hồ sơ chuẩn: **2026-05-19** | Đây là lỗ hổng lớn nhất vì sản phẩm đụng broker/bank data và vendor AI nước ngoài |
| 3. Hồ sơ phân loại hệ thống AI + change log prompt/model | ❌ **Chưa có** | Có tín hiệu ở [B-.md](../Nguyen_Quoc_Nam-2A202600201-Day17/B-.md), [risk_register_v2.md](../Day_21/risk_register_v2.md). Deadline build AI classification register: **2026-05-22** | Hiện có control kỹ thuật nhưng chưa có quyết định phân loại pháp lý chính thức |
| 4. Hồ sơ thẩm định nhà cung cấp / đối tác / API | ❌ **Chưa có** | Có dependency notes ở [dependency_map.md](../Nguyen_Quoc_Nam-2A202600201-Day17/Day_20/dependency_map.md) và [risk_register_v2.md](../Day_21/risk_register_v2.md). Deadline build vendor due diligence pack: **2026-05-22** | Thiếu DPA, SLA, retention, country transfer, incident notification, subprocessor map |
| 5. Hồ sơ kiểm soát AI output và ứng phó sự cố | ✅ **Đã có nền tảng** | [rules_rails_ritual.md](../Day_21/rules_rails_ritual.md), [incident_playbook.md](../Day_21/incident_playbook.md), [risk_register_v2.md](../Day_21/risk_register_v2.md) | Đây là nhóm tài liệu trưởng thành nhất hiện tại; chỉ cần chuẩn hóa owner, version và lịch review |

## TOP 1 ưu tiên

**Chọn:** Hồ sơ dữ liệu cá nhân + data flow + chuyển dữ liệu ra nước ngoài

**Lý do:** Đây là phần rủi ro cao nhất so với trạng thái hiện tại của startup vì tài liệu marketing đang nói đến đồng bộ tài khoản chứng khoán/ngân hàng, phân tích danh mục cá nhân và log AI qua vendor nước ngoài, nhưng repo chưa có một hồ sơ tập trung nào chứng minh founder đã thẩm định luồng dữ liệu đó.

## Hành động 1 tuần cho TOP 1

### Template tài liệu sẽ xây

**Tên tài liệu đề xuất:** `cross_border_data_transfer_assessment.md`

**Mẫu 3–5 dòng:**

1. **Luồng dữ liệu:** Dữ liệu nào đi từ user → app → model/log/vendor nào.
2. **Loại dữ liệu:** Định danh, tài khoản tài chính, danh mục, hành vi, prompt/response.
3. **Mục đích & căn cứ xử lý:** Vì sao cần từng luồng, có thể tối thiểu hóa hay ẩn danh hóa phần nào.
4. **Rủi ro & biện pháp:** Masking, retention, access control, incident reporting, country transfer.
5. **Người phê duyệt:** Founder, Tech Lead, Legal reviewer; ngày review kế tiếp.

### Owner + tần suất cập nhật

- **Owner chính:** Founder
- **Phối hợp:** Tech Lead + Product + Legal reviewer ngoài
- **Tần suất cập nhật:** mỗi feature chạm dữ liệu cá nhân và tối thiểu **hàng tháng** trước launch; sau launch chuyển sang **mỗi quý**

## Kết luận ngắn

- Startup đã có khung tốt cho incident và AI output control.
- Startup đang thiếu nặng ở hồ sơ dữ liệu, vendor và AI classification.
- Nếu chỉ được build 1 loại hồ sơ trong 1 tuần tới, nên build hồ sơ dữ liệu/chuyển dữ liệu ra nước ngoài trước.

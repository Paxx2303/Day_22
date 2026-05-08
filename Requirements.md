# Requirements - AI Compliance Workshop & Lab

## Workshop 1 – Rà soát claim marketing (15 phút)

**Tình huống:**  
Bạn là Quang Linh Vlogs vào tháng 2/2025 - chưa bị phạt. Có 15 phút để rà soát một câu claim marketing, sửa lại trước khi quá muộn.

**Vật liệu cần:**
- Trang giới thiệu chính + bài pin trên MXH + slide “What we do” Day 19

### 4 bước (14 phút):

1. **Highlight (3’):** Đánh dấu câu claim nói với AI – “làm được X”, “tăng Y%”, “thay thế Z”

2. **Phân loại 3 mức (5’):**
   - **Mức A – Chứng minh được** = có data, demo, ví dụ thực tế thật
   - **Mức B – Chưa chứng minh nhưng có thể** = cần test thêm
   - **Mức C – Thổi phồng** = không có evidence (vững Điêu 198)

3. **Viết lại honest version (4’):** Mỗi câu **Mức C** viết phiên bản trung thực

4. **Tự kiểm tra (2’):** Trang giới thiệu mới có còn convert được không?

**Output:**  
`marketing_claims_audit.md` – bảng 4 cột (Câu gốc / Mức / Evidence / Honest version)

---

## Workshop 2 – 3 câu hỏi 30 phút (15 phút)

**Vật liệu:**  
PRD Day 17 + Danh sách khách hàng Day 16 + Công nghệ đang dùng hiện tại

### 4 bước:

1. **Câu hỏi 1: User EU? (3’)**  
   - Có 1 user EU không? Có kế hoạch mở rộng EU 12 tháng tới không?  
   - Kết quả: EU AI Act áp dụng = CÓ / KHÔNG

2. **Câu hỏi 2: Dữ liệu Việt Nam? (3’)**  
   - Liệt kê 5 loại dữ liệu cá nhân đang xử lý (tên, SDT, email, hành vi, vị trí…).  
   - Có chuyển dữ liệu ra nước ngoài không? (dùng AI nước ngoài = chuyển)  
   - Kết quả: PDPL áp dụng + có cần đánh giá tác động chuyển dữ liệu không

3. **Câu hỏi 3: Tăng rủi ro Luật AI VN? (5’)**  
   - AI châm + tối ưu hóa chính? → Cao. Tạo content nhảm lẳn? → Trung bình. Còn lại → Thấp  
   - Viết 1 câu lập luận tại sao

4. **Lịch (3’):** Note 4 mốc deadline vào Notion

**Output:**  
`territorial_scope.md` – 1 trang trả lời 3 câu + 4 deadline cụ thể

---

## Workshop 3 – Hồ sơ chứng cứ founder (15 phút)

**Tình huống:**  
Bạn là Shark Bình tháng 5/2020 – chưa bị truy tố. Bạn build hồ sơ để khi cơ quan điều tra hỏi, bạn chứng minh được mình đã thẩm định.

### 3 bước:

1. **Đối chiếu 5 loại hồ sơ (5’):** Kẻ bảng 5 dòng. Cho mỗi loại: tick  
   - ✅ ĐÃ có (link đến file hiện tại)  
   - ❌ CHƯA có (viết deadline khi sẽ build)

2. **Chọn TOP 1 ưu tiên (5’):** Cho các ô ❌  
   - Cái nào rủi ro cao nhất với startup mình hiện tại?  
   - Lý do (1 câu)

3. **Hành động 1 tuần (5’):** Cho TOP 1  
   - Template tài liệu sẽ xây (mẫu 3-5 dòng)  
   - Người chịu trách nhiệm + Tần suất cập nhật (hằng tuần / hằng quý / mỗi feature)

**Output:**  
`document_trail.md` – bảng 5 dòng + TOP 1 ưu tiên + template 1 tuần. Đây là “bảo hiểm pháp lý” dạng tài liệu thật.

---

## Lab Setup – 5 bước

**Khác Lab Day 21 thế nào:**
- Day 21: AI tìm rủi ro tài chính (do bảng tháng runway)
- Day 22: AI tìm vi phạm pháp lý cụ thể (kèm Điều luật + cách sửa)

### Quy trình 5 bước (10 phút mỗi bước):

| # | Bước | Kết quả |
|---|------|--------|
| 1 | Chuẩn bị tài liệu đầu vào | PRD Day 17 + Tài liệu marketing + Sơ đồ luồng dữ liệu |
| 2 | Chạy prompt AI Tuần thứ pháp lý (tiếng Việt) | 7+ vi phạm tiềm năng theo Điều luật |
| 3 | Đối chiếu thủ công với Workshop 1+2+3 | Cái nào AI ra mà bạn bò sót? |
| 4 | Ưu tiên TOP 5 vi phạm nghiêm trọng | Mỗi cái viết 3 hành động sửa |
| 5 | Tổng hợp file cuối | `compliance_audit_v2.md` |

**Lý do yêu cầu AI output tiếng Việt:**  
Các Điều luật (198, 324, Điều 9 Luật AI VN, Điều 8 PDPL) là tiếng Việt. Output tiếng Việt = bạn email cho luật sư bạn ngoài → họ đọc 30 phút thay vì 5 tiếng tự cứu.

---

## Prompt cho AI Compliance Officer (sử dụng ở Lab)

**Vai trò:** Chuyên viên Tuần thứ pháp lý về startup AI Việt Nam. Nâng cao.

**Kiến thức bắt buộc:**
- Luật AI Việt Nam 154/2024/QH15 (niêm luật 1/3/2026)
- Luật Bảo vệ Dữ liệu Cá nhân (niêm luật 1/7/2026)
- Bộ Luật Hình sự VN: Điều 174, 198, 324
- EU AI Act + GDPR
### 3 vụ enforcement Việt Nam cần áp dụng pattern:

- **Vụ kẹo Kera 11/2025** (3 KOL đi tù theo Điều 198)
- **Vụ Mr Pips 2/2026** (Shark Bình bị đề nghị truy tố theo Điều 324)
- **Vụ rò rỉ CIC 9/2025** (PDPL Điều 8 phạt 10x doanh thu)

### Rà soát sản phẩm sau để tìm vi phạm pháp lý tiềm năng:
**[paste PRD + marketing materials + tech stack + data flow]**

### Format mỗi vi phạm:

**VI PHẠM N:** [tên ngắn]

- **Luật áp dụng:** [Luật AI VN / PDPL / BLHS / EU AI Act]
- **Điều:** [số điều + khoản]
- **Bằng chứng trong sản phẩm:** [trích nguyên văn]
- **Pattern khớp với:** [vụ Việt Nam tương tự]
- **Hành động sửa:** [founder làm trong 1 tuần]
- **Deadline:** [theo grace period]

### Yêu cầu tối thiểu:
- 3 vi phạm marketing (kiểu Kera)
- 2 vi phạm DLCN (PDPL Điều 30)
- 1 vi phạm phân loại AI (Điều 9 Luật)
- 1 vi phạm vendor/payment (kiểu Pips)

**Yêu cầu output:**
- Search đầy đủ materials + tech stack + data flow
- Format rõ ràng: Vi phạm N: [tên] → Luật VN / PDPL / EU AI Act → Bằng chứng trong sản phẩm → Trích nguyên văn → Pattern chung → Đánh giá: [thoe grace period]
- Yêu cầu tài liệu: 7 vi phạm marketing (Kera) + 2 vi phạm DL CN (PDPL Điều 8) + 1 vi phạm Loại AI (Điều 9 Luật AI VN) + 1 vi phạm vendor/partner

**Output:** Toàn bộ bảng tiếng Việt. Trả lời logic, không né tránh.

---
### Bảng Đối chiếu thủ công với AI:

| Loại vi phạm                  | Workshop liên quan          | Câu hỏi đối chiếu |
|-------------------------------|-----------------------------|-------------------|
| Marketing thổi phồng (Kera)   | WS1 – rà soát claim        | AI tìm ra cái nào bạn bỏ sót? |
| Tăng rủi ro AI                | WS2 – 3 câu hỏi            | AI có xếp cùng tầng không? |
| Rủi ro vendor/thanh toán      | WS3 – hồ sơ chứng cứ       | AI thấy thiếu sót nào trong hồ sơ? |
| Dữ liệu cá nhân               | Tất cả + Công nghệ đang dùng | Có vi phạm Điều 30 nào ẩn? |
## Tiêu chí cuối – File đạt yêu cầu (compliance_audit_v2.md)

- Có ≥ 7 vi phạm (4 loại theo prompt)
- Mỗi vi phạm có **Điều luật cụ thể** (không nói chung “vi phạm pháp luật”)
- Mỗi vi phạm có trích nguyên văn + bằng chứng từ tài liệu của bạn
- Mỗi vi phạm có **Việt Nam khớp pattern** (Kera / Pips / CIC)
- Top 5 nghiêm trọng nhất có 3 hành động sửa mỗi cái
- Tất cả output tiếng Việt, có thể email luật sư đọc tiếp

---

**File cần tạo:**
- `marketing_claims_audit.md`
- `territorial_scope.md`
- `document_trail.md`
- `compliance_audit_v2.md`

Hoàn thành theo thứ tự Workshop 1 → 2 → 3 → Lab Setup.
# Marketing Claims Audit — Day 22

> Audit nội bộ cho workshop. Giả định `../Day_19/pitch_memo.md` là trang giới thiệu chính / slide “What we do”, và `../Day_19/twitter_pitch.md` là bài pin MXH vì repo không có file slide riêng.

## Quy ước mức

- **Mức A**: Có dữ liệu/demonstration thật ngay trong repo, đủ để chứng minh public claim.
- **Mức B**: Claim có thể đúng nhưng hiện mới là giả thuyết hoặc chưa có bằng chứng gốc để public.
- **Mức C**: Thổi phồng, dễ bị hiểu thành cam kết kết quả, hoặc mâu thuẫn với chính tài liệu sản phẩm hiện có.

| Câu gốc | Mức | Evidence hiện có | Honest version |
|---|---|---|---|
| “Giúp nhà đầu tư F0 Việt Nam bớt thua lỗ bằng AI ‘coach hành vi’ đầu tư” — [twitter_pitch.md](../Day_19/twitter_pitch.md) | C | Chỉ có câu marketing; không có nghiên cứu đối chứng hoặc dữ liệu trước/sau đủ mạnh trong repo. | “StockFund AI được thiết kế để giúp nhà đầu tư mới nhận ra hành vi FOMO và đầu tư kỷ luật hơn; tác động lên kết quả đầu tư vẫn cần kiểm chứng thêm.” |
| “Pilot 80 users: giảm 65% trade cảm tính” — [twitter_pitch.md](../Day_19/twitter_pitch.md) và [pitch_memo.md](../Day_19/pitch_memo.md) | C | Không có file pilot raw data, định nghĩa metric, cỡ mẫu hợp lệ hoặc cách đo trong repo. | “Trong một pilot nhỏ 80 người dùng, nhóm ghi nhận tín hiệu tích cực về việc giảm giao dịch cảm tính; số liệu này chưa sẵn sàng để dùng như claim đại chúng.” |
| “82% giữ app” — [twitter_pitch.md](../Day_19/twitter_pitch.md) | C | Không có cohort table, thời gian đo retention hay dashboard gốc. | “Một phần người dùng pilot vẫn tiếp tục dùng ứng dụng sau thử nghiệm; cần theo dõi retention 3–6 tháng để kết luận chắc hơn.” |
| “LTV/CAC = 4.8x” — [twitter_pitch.md](../Day_19/twitter_pitch.md) và [pitch_memo.md](../Day_19/pitch_memo.md) | B | Có nêu giả định CAC và giá thuê bao trong memo, nhưng chưa có worksheet hoặc dữ liệu doanh thu thật trong repo. | “Mô hình tài chính nội bộ hiện giả định LTV/CAC mục tiêu khoảng 4.8x; đây chưa phải số đã kiểm toán từ vận hành thực tế.” |
| “StockFund AI là ứng dụng AI tư vấn cổ phiếu cá nhân hóa” — [pitch_memo.md](../Day_19/pitch_memo.md) | C | Mâu thuẫn với PRD Day 17 Version B, nơi sản phẩm nói rõ “không đưa khuyến nghị mua/bán cụ thể”. | “StockFund AI là công cụ AI hỗ trợ đọc dữ liệu đầu tư và cảnh báo rủi ro; sản phẩm chưa nên tự nhận là ‘tư vấn cổ phiếu cá nhân hóa’.” |
| “Đồng bộ tự động với tài khoản chứng khoán và ngân hàng qua Open Banking & API” — [pitch_memo.md](../Day_19/pitch_memo.md) | C | Không có danh sách đối tác đã ký, tài liệu tích hợp, DPA hoặc ảnh chụp luồng chạy thật trong repo. | “Lộ trình sản phẩm có định hướng tích hợp dữ liệu tài khoản qua API đối tác; hiện chưa nên public như tính năng đã sẵn sàng.” |
| “AI phân tích danh mục, mức độ rủi ro và mục tiêu cá nhân rồi gửi ‘Báo cáo Sức khỏe Danh mục’ dễ hiểu” — [pitch_memo.md](../Day_19/pitch_memo.md) | B | Có mô tả khái niệm sản phẩm, nhưng chưa có demo/public artifact trong repo xác nhận end-to-end flow này đã hoạt động. | “Sản phẩm đang được định hướng để phân tích danh mục và tạo báo cáo dễ hiểu; cần thêm bản demo và test thật trước khi claim mạnh.” |
| “Gợi ý giảm về 35% và đa dạng sang tiêu dùng & công nghệ để cân bằng” — [pitch_memo.md](../Day_19/pitch_memo.md) | C | Đây là ví dụ mang tính khuyến nghị phân bổ tài sản, tạo cảm giác sản phẩm đang cho lời khuyên đầu tư cá nhân hóa. | “Ví dụ minh họa nên đổi thành: ‘hệ thống nêu mức tập trung rủi ro và các nhóm ngành liên quan để người dùng tự đánh giá tiếp’.” |
| “AI giúp nhà đầu tư mới đầu tư thông minh hơn, kỷ luật hơn” — [pitch_memo.md](../Day_19/pitch_memo.md) | B | Claim định tính, hợp lý ở mức product vision nhưng chưa có proof đủ mạnh để biến thành promise. | “StockFund AI hướng tới việc giúp nhà đầu tư mới hiểu danh mục rõ hơn và xây thói quen đầu tư kỷ luật hơn.” |
| “Hiệu suất danh mục trung bình cải thiện rõ rệt sau 2 tháng” — [pitch_memo.md](../Day_19/pitch_memo.md) | C | Không có baseline, benchmark VN-Index, sample construction hay công thức tính trong repo. | “Nhóm có quan sát sớm rằng một số user pilot đánh giá tốt hơn về trải nghiệm đầu tư; hiệu suất danh mục cần kiểm chứng bằng cohort dài hạn.” |

## Tự kiểm tra sau khi sửa copy

- Bản sửa vẫn giữ được ý chính: AI hỗ trợ đọc dữ liệu, cảnh báo rủi ro, xây kỷ luật.
- Các câu dễ bị hiểu thành “cam kết lợi nhuận” hoặc “đã tích hợp xong” đều đã được làm trung thực hơn.
- Nếu muốn public lại các số 65%, 82%, 4.8x, cần bổ sung phụ lục bằng chứng riêng trước.

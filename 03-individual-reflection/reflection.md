## 1. Đóng góp của tôi trong làm việc nhóm

Bảng ghi nhận vai trò và mức độ tham gia thực tế của bản thân trong suốt 7 Phase của buổi Lab Day 02:

| Hoạt động trong Lab | Tôi đã làm gì? | Kết quả & Tác động tới bài làm nhóm |
|---|---|---|
| Scan cá nhân (Phase 1) | Chuẩn bị danh sách bài toán thực tế, nổi bật là bài toán *"Viết Daily Standup report dựa trên commit history và task Jira/Trello"* ," *"Quản lý và phân loại tài liệu tuyển dụng (Job Descriptions - JD): Không biết hồ sơ (CV) của mình thiếu skill nào so với yêu cầu tuyển dụng thực tế"* và "Đọc báo lỗi (Error Log/Stack trace) dài ngoẵng từ thư viện hoặc framework mới để tìm đúng nguyên nhân gốc (Root cause)" | Đóng góp 3 bài toán có quy trình kỹ thuật rõ ràng. |
| Pitch Problem Card (Phase 2 & 3) | Pitch bài toán Auto Daily từ Git commit; đồng thời ủng hộ bài toán Discord FAQ của bạn Vũ. | Bài toán Git Daily được bình chọn vào Shortlist Top 2 của nhóm. |
| Challenge bài của bạn khác (Phase 3) | Đặt câu hỏi cho bài toán điểm danh/tính tiền học của Hưng về việc tại sao không dùng Excel/phần mềm truyền thống mà phải dùng AI. | Giúp nhóm phân biệt rõ giữa Rule-based software và AI Workflow. |
| Gom trùng / Cluster (Phase 3) | Phụ trách nhóm Cluster A (Hỗ trợ tự động hóa trên Discord/Git). | Giúp nhóm thấy rõ điểm tương đồng về nền tảng triển khai Discord. |
| Quick Validation & Research (Phase 4) | Chủ trì tìm kiếm giải pháp có sẵn (Slack AI, Discord Dyno Bot, Pinned FAQ) và dẫn link bằng chứng. | Rút ra bài học: Rule thuần túy (Dyno Bot) quá cứng nhắc, cần dùng RAG Workflow. |
| Xây dựng Workflow (Phase 5) | Phối hợp cùng Phong xác định luồng dữ liệu của bước RAG Search và AI soạn phản hồi. | Đảm bảo tính khả thi kỹ thuật cho Future State Workflow. |
| Viết Problem Statement (Phase 5 & 6) | Đóng góp ý kiến cho trường AI Intervention Point và Rủi ro AI Hallucination trong PS v1. | Làm rõ ranh giới khi nào AI can thiệp và khi nào phải có người duyệt. |
| Chọn mức AI & Decision (Phase 6)| Phân tích bài toán vào Ma trận độ mơ hồ × độ phức tạp và bảo vệ lựa chọn Workflow. | Giúp nhóm thống nhất không sa vào việc chọn Agent quá phức tạp. |

---

## 2. Nhật ký sử dụng AI trong quá trình làm bài (AI Usage Audit)

Bảng ghi nhận cách thức tương tác với AI, những điểm AI hỗ trợ tốt, điểm AI hời hợt/sai và cách tôi tự điều chỉnh bằng nhận định cá nhân:

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai / hời hợt ở đâu? | Tôi đã tự điều chỉnh gì bằng nhận định cá nhân? |
|---|---|---|---|---|
| Scan bài toán (Phase 1) | Gợi ý thêm bài toán trong bối cảnh lập trình/Dev. | Gợi ý bài toán chuyển đổi commit log thành báo cáo daily. | Đưa ra vài ý tưởng tự động sửa lỗi code quá rộng. | Lọc bỏ ý tưởng tự sửa lỗi code, giữ lại ý tưởng Auto Daily vì workflow khép kín. |
| Problem Card (Phase 2) | Phản biện Problem Card Auto Daily từ Git commit. | Chỉ ra rủi ro dev gõ commit message sơ sài dẫn đến AI draft sai. | AI tự động gợi ý chuyển thành Agent tự mở PR trên GitHub. | Giữ nguyên phạm vi hỗ trợ viết Daily status, không ôm đồm tính năng Agent. |
| Research (Phase 4) | Tìm kiếm các tool Discord Bot có sẵn trên thị trường. | Tìm thấy Dyno Bot và các giải pháp FAQ bot hiện có. | Cung cấp thông tin tính năng của Slack AI chưa chính xác hoàn toàn. | Kiểm tra lại thông tin trên trang trợ giúp chính thức của Slack AI để dẫn link chuẩn. |
| Problem Statement (Phase 5 & 6) | Nhờ AI đóng vai Skepical PM soi lỗ hổng trong Problem Statement v0. | Chỉ ra điểm yếu về việc chưa có cách đo lường độ chính xác của câu trả lời. | AI gợi ý viết lại PS với ngôn ngữ quá hàn lâm, khó hiểu. | Giữ cấu trúc 9 field ngắn gọn, tập trung vào metric con số thời gian cụ thể. |
| Decision (Phase 6) | Tham khảo cây quyết định cho lựa chọn Go / Not Yet / No-Go. | Gợi ý ý tưởng chạy Pilot trên 1 kênh chat nhỏ với 10-15 người. | AI khuyên nên xây dựng ngay phiên bản đầy đủ cho toàn bộ máy chủ. | Điều chỉnh lại kế hoạch Pilot nhỏ nhất (MVP) chỉ thử nghiệm với 15-20 câu FAQ. |

## Bài học của Minh
---

- Problem tốt không phải problem nghe "AI" nhất, mà là problem có workflow và metric rõ.
- Vẽ workflow giúp thấy phần nào rule đủ, phần nào AI mới có ích.
- Agent không phải đích đến mặc định. Trong case này, Workflow hợp lý hơn vì có đường đi cố định và có PM review.
- Research không phải để copy tool, mà để thấy pattern: nhiều sản phẩm tốt đều để AI draft, người thật review.


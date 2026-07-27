Minh scan 10 problems, vượt mức tối thiểu 5.

| # | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Tốn thời gian | Tìm kiếm và chọn món ăn/quán ăn phù hợp với ngân sách và sở thích mỗi trưa/tối | Bản thân, Đồng nghiệp, Bạn bè | Mất 15–20 phút lướt GrabFood/ShopeeFood mỗi buổi trưa, hay tranh cãi "Trưa nay ăn gì?" |
| 2 | Lặp lại | Lọc và phân loại thu chi hàng tháng từ sao kê ngân hàng/ví điện tử vào file quản lý tài chính | Bản thân | Cuối tháng mất 1–2 tiếng ngồi phân loại thủ công từng giao dịch; dễ quên các khoản chi bằng tiền mặt |
| 3 | Tốn thời gian | Theo dõi lịch bảo dưỡng thiết bị cá nhân (xe máy, máy tính, thay lõi lọc nước, gia hạn gói cước/subcription) | Bản thân | Xe chạy quá 3.000km mới nhớ thay nhớt; quên hủy dùng thử ứng dụng bị trừ tiền oan |
| 4 | Pain từ người khác | So sánh và lựa chọn sản phẩm công nghệ/đồ gia dụng (laptop, tai nghe, bàn ghế ergonomics) dựa trên hàng trăm đánh giá thật vs seeding | Bản thân | Mất 2–3 ngày xem video review trên Youtube và đọc comment để phát hiện đâu là nhận xét thật |
| 5 | AI có thể tốt hơn | Quản lý thời gian học kỹ năng mới (tiếng Anh, framework mới) sau giờ làm việc khi bản thân đã kiệt sức | Bản thân | Dễ bỏ cuộc giữa chừng (drop khóa học); lịch học quá cứng nhắc không tự linh hoạt theo mức độ mệt mỏi |
| 6 | Tốn thời gian | Đọc và hiểu một module/codebase cũ (legacy code) khổng lồ không có document để sửa bug | Intern Dev |Mất 2-3 ngày chỉ để trích xuất luồng logic chính (flow) trước khi gõ câu lệnh code đầu tiên |
| 7 | Tốn thời gian | Đọc báo lỗi (Error Log/Stack trace) dài ngoẵng từ thư viện hoặc framework mới để tìm đúng nguyên nhân gốc (Root cause) | Dev| Mất 1-2 tiếng search Google/Stack Overflow cho một lỗi cú pháp hoặc xung đột thư viện (dependency conflict)|
| 8 | AI có thể tốt hơn | Viết tài liệu API (Swagger/Postman doc) hoặc viết tài liệu hướng dẫn cài đặt môi trường (README.md) sau khi làm xong task| Dev| Thường xuyên bỏ qua hoặc viết sơ sài; member mới clone project về tốn nửa ngày không run được code|
| 9 | AI có thể tốt hơn | Quản lý và phân loại tài liệu tuyển dụng (Job Descriptions - JD): Không biết hồ sơ (CV) của mình thiếu skill nào so với yêu cầu tuyển dụng thực tế| Sinh viên mới ra trường, người tìm việc làm | Đọc hàng chục JD trên Facebook/ITViec nhưng chỉ đánh giá bằng cảm tính; rải CV vô hướng và tỷ lệ trượt cao |
| 10 | Lặp lại | Viết Daily Standup report (Hôm qua làm gì, hôm nay làm gì, có blocker gì) dựa trên commit history và task Jira/Trello | Mất 10-15 phút mỗi sáng ngồi mò lại git log và Jira xem hôm qua mình đã đẩy những gì |

## Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Auto Daily Standup | Workflow cực rõ, dữ liệu đầu vào có sẵn, tiết kiệm 10-15p/ngày, metric đo lường rất dễ. | Quality của commit log (nếu dev commit kiểu "fix bug", "update" thì AI khó tóm tắt đúng). |
| 2 | CV & JD Skill Matcher | Pain point trực tiếp của sinh viên ra trường, input rõ ràng (File CV + Text JD), giá trị ứng dụng cao. | Quality của AI khi xác định skill (ví dụ: JD yêu cầu "React", AI có thể nhầm lẫn với "React Native"). |
| 3 | Log & Stack Trace Analyzer | Pain nhức nhối nhất của Dev, lặp lại hàng ngày, tiết kiệm hàng giờ debug.| Risk về bảo mật log/code nội bộ và rủi ro AI "ảo giác" đưa ra cách fix sai. |

## Problem Card #1 — Auto Daily Standup

**Problem 1 câu:**  
Mỗi sáng Dev/Intern mất 10–15 phút lùng sục lại Git commit history và Jira task để viết báo cáo Daily Standup, vừa tốn thời gian vừa hay quên các task nhỏ hoặc blocker.

**Actor:**  
Dev/Intern.

**Thời điểm / bối cảnh:**  
Sáng hằng ngày, trước buổi daily standup.

**Current workflow:**

```text
1. Mở Git GUI hoặc terminal, gõ `git log` hoặc mở GitHub Desktop để xem commit list.
2. Đọc từng dòng commit message để nhớ lại hôm qua mình làm gì.
3. Vào Jira, mở các task đã close trong ngày hôm qua để kiểm tra lại các sub-task nhỏ đã xong hay chưa.
4. Soạn thảo báo cáo theo template (What I did yesterday / What I will do today / Blockers).
5. Tự review xem đã đủ ý chưa rồi mới paste vào Slack/Team.
```

**Bottleneck:**  
Bước 1 và 2 — Lùng sục và nhớ lại (Memory Recall). Không có công cụ nào tự động gom commit lại theo task; phải dựa hoàn toàn vào trí nhớ hoặc phải tự viết script grep log, việc này rất dễ sai sót và mất thời gian.

**Impact:**  
10–15 phút mỗi ngày. Với 5 ngày/tuần thì tốn khoảng 1 tiếng. Nếu nhân lên với các đồng nghiệp khác (hoặc nếu làm internship 2-3 tháng) thì sẽ rất lãng phí. Quan trọng hơn là có thể quên mất một task nhỏ nhưng quan trọng, dẫn đến báo cáo không chính xác.

**Success metric:**  
Giảm thời gian từ 10–15 phút xuống dưới 2 phút; đảm bảo 100% các task trong ngày đều được báo cáo.

**Non-AI alternative:**  
Viết thêm Git hooks hoặc chạy script Python tổng hợp log hằng đêm, nhưng cần kỹ năng kỹ thuật và không giải quyết được vấn đề thiếu insight hoặc context.

**AI hypothesis:**  
AI đọc Git log + Jira metadata, nhận dạng commit liên quan đến task nào, rồi tự động tổng hợp thành báo cáo daily standup.

**Quick gut:**  
Workflow.

### Draft current workflow
CURRENT STATE — 35 phút

[1 Nhắc team update/Gợi ý câu hỏi: 5']
→ [2 Check từng Jira ticket/PR GitHub: 10']
→ [3 Đọc message/thread Slack trong ngày: 8']
→ [4 Tổng hợp 3 câu hỏi (Done/Today/Blocker): 7']  <-- bottleneck (tốn công gom thông tin tản mạn)
→ [5 Review, format & gửi vào channel: 5']

### Draft future workflow
FUTURE STATE — 7 phút

[1 Trigger auto-collect (Jira activity + GitHub PRs + Slack): 1']
→ [2 AI tổng hợp & nhóm theo 3 mảng (Yesterday/Today/Blockers): 1']
→ [3 AI tự động tag member & highlight Rủi ro/Blocker: 1']
→ [4 PM/Scrum Master review + điều chỉnh nhẹ: 3']  <-- human boundary
→ [5 Auto-post vào channel Standup: 1']

Fallback: Thiếu data thành viên / AI phân loại nhầm → PM tag trực tiếp member hỏi nhanh & edit tay.


## Problem Card #2 — CV & JD Skill Matcher

**Problem 1 câu:**  
Mất thời gian để tìm việc và ôn tập, hoặc chuẩn bị hồ sơ trước hạn chót nộp đơn.

**Actor:**  
Sinh viên mới ra trường hoặc người đang tìm việc làm.

**Thời điểm / bối cảnh:**  
Trong giai đoạn tìm việc, ôn tập, hoặc chuẩn bị hồ sơ trước hạn chót nộp đơn.

**Current workflow:**

```text
1. Truy cập website tuyển dụng (LinkedIn, Facebook, ITViec).
2. Download/copy nội dung Job Description (JD).
3. Mở file CV của bản thân.
4. So sánh thủ công: đọc JD, highlight các kỹ năng yêu cầu, rồi rà lại CV xem mình có khớp không.
5. Ghi chú lại: "cần học thêm cái này", "cái kia có rồi nhưng chưa sâu".
```

**Bottleneck:**  
Bước 4 — So sánh thủ công: đọc JD, highlight các kỹ năng yêu cầu, rồi rà lại CV xem mình có khớp không.

**Impact:**  
- Tốn thời gian để tìm việc và ôn tập, hoặc chuẩn bị hồ sơ trước hạn chót nộp đơn.
- Cảm thấy không chắc chắn về kỹ năng của bản thân, không biết nên học gì.

**Success metric:**  
Giảm thời gian phân tích & lên kế hoạch chuẩn bị từ 90 phút xuống 15 phút/JD
Ra được ngay Danh sách Top 3 kỹ năng cần bổ sung gấp kèm Gợi ý chỉnh sửa CV theo đúng ngữ cảnh JD.

**Non-AI alternative:**  
Checklist có thể giảm format effort, nhưng chưa giải quyết tốt phần viết narrative.

**AI hypothesis:**  
AI phân tích JD, so sánh với CV, tìm ra điểm mạnh/yếu, đề xuất khóa học hoặc dự án phù hợp.

**Quick gut:**  
Agent.

### Draft current workflow
CURRENT STATE — 90 phút

[1 Lưu JD từ LinkedIn/ITViec: 10']
→ [2 Mở CV & đọc lướt JD: 20']
→ [3 So sánh thủ công, tự soi lỗ hổng skill: 25']  <-- bottleneck
→ [4 Search Google/Youtube tìm tài liệu ôn tập: 20']
→ [5 Tự sửa CV cho khớp keyword JD: 15']

### Draft future workflow
FUTURE STATE — 15 phút

[1 Input CV + JD link: 1']
→ [2 Agent phân tích Gap Analysis: 1']
→ [3 Agent xuất Gợi ý sửa CV + Checklist ôn tập: 1']
→ [4 Candidate review, duyệt edit CV & học theo checklist: 11']  <-- human boundary
→ [5 Candidate nộp CV: 1']

Fallback: JD mơ hồ/thiếu thông tin → Agent yêu cầu Candidate nhập bổ sung vị trí & level mong muốn.

## Problem Card #3 — Log & Stack Trace Analyzer

**Problem 1 câu:**  
ev tốn rất nhiều thời gian mỗi ngày để đọc, tra cứu và tra vết thủ công các dòng Log và Stack Trace dài hàng ngàn dòng khi gặp bug hoặc sự cố production, dẫn đến kéo dài thời gian debug và xử lý sự cố (MTTR - Mean Time To Resolution).

**Actor:**  
Dev

**Thời điểm / bối cảnh:**  
Khi ứng dụng gặp lỗi runtime, crash production, chạy test suite thất bại hoặc nhận cảnh báo bug từ hệ thống giám sát (Sentry, Datadog, CloudWatch).

**Current workflow:**

```text
1. Phát hiện lỗi, truy cập hệ thống log (Datadog/Sentry/Kibana) hoặc đọc log file local.
2. Lọc & cuộn tìm vị trí xảy ra Stack Trace chính giữa hàng ngàn dòng log nhiễu.
3. Đọc hiểu đoạn exception, tra cứu mã lỗi hoặc copy lỗi lên Google/Stack Overflow/GitHub Issues.
4. Đọc các câu trả lời, đối chiếu lại với source code dự án xem có đúng ngữ cảnh không.
5. Thử nghiệm các phương án fix, chạy lại code để kiểm tra.
6. Commit code fix và viết note lý do gây ra bug cho team.
```

**Bottleneck:**  
Bước 2 & 3 — Phải lọc bớt log nhiễu để tìm đúng root cause và tra cứu giải pháp trên mạng. Việc này vô cùng tốn thời gian, đặc biệt với các lỗi phức tạp liên quan đến bất đồng bộ, bất tương thích thư viện hoặc memory leak.
**Impact:**  
Mất từ 45–90 phút cho mỗi bug phức tạp. Một Dev trung bình gặp 2–4 bug/ngày, tốn gần 2–3 giờ làm việc/ngày chỉ để đọc log và debug.

Trễ deadline sprint, kéo dài thời gian downtime khi sự cố xảy ra trên môi trường Production.

Rủi ro lớn (Risk):

Bảo mật: Dev vô tình copy log chứa dữ liệu nhạy cảm (API Key, PII, Credentials, SQL Queries nội bộ) paste lên các công cụ AI công cộng.

Ảo giác (Hallucination): AI đưa ra đoạn code fix sai hoặc không tối ưu, khiến Dev áp dụng mù quáng gây ra bug ẩn nghiêm trọng hơn.
**Success metric:**  
Giảm thời gian đọc log và tìm nguyên nhân gốc (Root Cause) từ 60 phút xuống 10 phút/bug (giảm ~83%), tuyệt đối không leak dữ liệu nhạy cảm ra ngoài và 100% giải pháp phải qua kiểm duyệt của Dev trước khi áp dụng.
**Non-AI alternative:**  
Dùng công cụ Log Aggregator (Datadog/Sentry) đặt rule cảnh báo + viết Regex filter: Giúp nhóm các lỗi giống nhau lại, nhưng không tự giải thích nguyên nhân gốc và không gợi ý đoạn code fix trực tiếp cho dự án.

**AI hypothesis:**  
Hệ thống AI tích hợp cơ chế Anonymizer/Data Masking tự động che bớt thông tin nhạy cảm trước khi xử lý, sau đó phân tích Stack Trace để trích xuất nguyên nhân gốc (Root Cause) kèm gợi ý hướng sửa (Fix Suggestion). Dev giữ vai trò thẩm định logic và tự chạy test kiểm tra.

**Quick gut:**  
Workflow.

### Draft current workflow
CURRENT STATE — 60 phút / bug

[1 Tải log / mở Sentry: 5']
→ [2 Cuộn tìm Stack Trace & bóc tách log nhiễu: 15']
→ [3 Copy lỗi lên Google / Stack Overflow / Github: 15']  <-- bottleneck
→ [4 Đọc giải pháp & rà lại Source Code: 15']
→ [5 Thử nghiệm fix + viết note bug: 10']

### Draft future workflow
FUTURE STATE — 10 phút / bug

[1 Dán Log / Auto-trigger từ Sentry: 1']
→ [2 Auto-masking dữ liệu nhạy cảm (PII/Key/Token): 1']
→ [3 AI bóc bớt nhiễu + phán đoán Root Cause + gợi ý Code Fix: 1']
→ [4 Dev thẩm định logic, chỉnh sửa & test code: 6']  <-- human boundary
→ [5 Dev commit fix & đóng ticket: 1']

Fallback: AI phán đoán sai / ảo giác → Dev tự khoanh vùng theo vị trí dòng code AI đã highlight và debug thủ công bằng Breakpoint.
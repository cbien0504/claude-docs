---
title: Advisor tool (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/advisor-tool
description: Kết hợp một mô hình thực thi nhanh hơn với một mô hình cố vấn thông minh hơn, đưa ra hướng dẫn chiến lược ngay trong lúc sinh nội dung.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/advisor-tool). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Advisor tool cho phép một **mô hình thực thi (executor)** nhanh và rẻ hơn tham vấn một **mô hình cố vấn (advisor)** thông minh hơn ngay giữa lúc sinh nội dung. Advisor đọc toàn bộ hội thoại và đưa ra kế hoạch hoặc chỉnh hướng, rồi executor tiếp tục công việc. Mẫu này phù hợp với workload agent dài hạn (agent lập trình, computer use, pipeline nghiên cứu nhiều bước), nơi phần lớn lượt là cơ học nhưng kế hoạch tốt rất quan trọng: chất lượng gần với việc chỉ dùng advisor trong khi phần lớn token được sinh với giá của executor.

## Các điểm chính

- **Cách dùng theo bề mặt:** trong Messages API, thêm advisor tool (type `advisor_20260301`) vào `tools` của request; trong Managed Agents, đặt `advisor` trong khối `multiagent` của agent (không có tùy chọn `max_uses` hay `max_tokens`).
- **Beta:** tính năng đang ở dạng beta, cần beta header `advisor-tool-2026-03-01`.
- **Khi nào nên dùng:** đang dùng Sonnet cho tác vụ phức tạp (thêm advisor cấp cao hơn; Opus giữ tổng chi phí tương đương hoặc thấp hơn, Claude Fable 5.1 cho mức tăng chất lượng lớn nhất); đang dùng Haiku và muốn nâng trí tuệ (thêm advisor Opus hoặc Fable, chi phí cao hơn Haiku đơn thuần nhưng thấp hơn đổi sang executor lớn hơn). Kết quả phụ thuộc tác vụ, nên cần đánh giá trên workload của bạn. Ít phù hợp với hỏi đáp một lượt, bộ chọn mô hình chuyển tiếp thuần túy, hoặc workload mà lượt nào cũng cần toàn bộ năng lực của advisor.
- **Phản hồi:** `content` chứa block `advisor_tool_result`. Với advisor là mô hình Opus mới nhất, trường `content` ở dạng `advisor_redacted_result` (được mã hóa; executor đọc phía máy chủ còn client của bạn thì không). Dùng `claude-opus-4-8` làm advisor để nhận dạng văn bản thường `advisor_result`.

## Các mục trong trang gốc

Khi nào dùng · Quick start · Cách hoạt động · Tham số công cụ · Cấu trúc phản hồi (lệnh gọi thành công, các biến thể kết quả, kết quả lỗi) · Hội thoại nhiều lượt (tiếp tục lượt bị tạm dừng, nhắc nhẹ khi executor gọi quá ít) · Streaming · Sử dụng và thanh toán · Prompt caching cho advisor (phía executor, phía advisor) · Kết hợp với công cụ khác · Thực hành tốt (prompt cho tác vụ lập trình và agent, giới hạn đầu ra advisor, kết hợp với cài đặt effort, kiểm soát chi phí) · Tương thích mô hình (nền tảng khả dụng) · Advisor trên Claude Managed Agents · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/advisor-tool)
- [Tổng quan sử dụng công cụ](overview.md)
- [Effort](../../build-with-claude/effort.md)
- [Prompt caching](../../build-with-claude/prompt-caching.md)

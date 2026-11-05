---
title: Task budgets – beta (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/task-budgets
description: Cho Claude một ngân sách token mang tính tham khảo cho toàn bộ vòng lặp agent, giúp mô hình tự điều tiết trong các tác vụ agent dài.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/task-budgets). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Task budgets cho bạn nói với Claude mình có bao nhiêu token cho cả một vòng lặp agent, gồm thinking, lệnh gọi công cụ, kết quả công cụ và đầu ra. Mô hình nhận một bộ đếm ngược chạy liên tục và dùng nó để ưu tiên công việc và kết thúc êm khi ngân sách bị tiêu hao. Tính năng ở dạng beta và cần beta header.

## Các điểm chính

- **Khi nào dùng:** hợp nhất với workflow agent trong đó Claude thực hiện nhiều lệnh gọi công cụ và quyết định trước khi chốt đầu ra để chờ phản hồi tiếp theo của người dùng.
- **Cách bộ đếm ngược hoạt động:** trang giải thích thế nào được tính là một lượt, có ví dụ đếm ngân sách qua nhiều request, và cách mang ngân sách qua compaction bằng `remaining`.
- **Đổi ngân sách giữa hội thoại** được nêu ở mục riêng.
- **Mang tính tham khảo, không bị ép buộc (advisory, not enforced):** task budget không phải giới hạn cứng.
- **Chọn ngân sách:** đo mức sử dụng hiện tại trước khi đặt.
- Trang cũng nói về tương tác với các tham số khác và hỗ trợ tính năng.

## Các mục trong trang gốc

Khi nào dùng task budgets · Đặt task budget · Cách bộ đếm ngược hoạt động · Đổi ngân sách giữa hội thoại · Task budgets mang tính tham khảo, không bị ép buộc · Chọn ngân sách · Tương tác với các tham số khác · Hỗ trợ tính năng · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/task-budgets)
- [Effort](effort.md)
- [Tổng quan compaction](compaction.md)

---
title: Extended thinking – bản cũ (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/extended-thinking
description: Cấu hình extended thinking thủ công với ngân sách cố định budget_tokens trên các mô hình Claude hỗ trợ, và chuyển sang adaptive thinking.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/extended-thinking). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Extended thinking ở chế độ thủ công cho bạn kiểm soát trực tiếp lượng suy nghĩ của Claude: bạn đặt ngân sách token cho thinking trên mỗi request bằng `thinking: {type: "enabled", budget_tokens: N}`, và Claude suy nghĩ theo ngân sách đó trước khi bắt đầu câu trả lời cuối cùng.

> **Lưu ý:** Extended thinking là tính năng cũ (legacy) và đã bị ngừng khuyến khích (deprecated). Các mô hình Claude 4.7 trở lên không hỗ trợ nó và từ chối request dùng nó với lỗi 400. Cách thay thế được khuyến nghị là adaptive thinking; trang có hướng dẫn chuyển đổi.

## Các điểm chính

- **Bật chế độ thủ công:** thêm đối tượng `thinking` với `type` là `enabled` và giá trị `budget_tokens`.
- **`budget_tokens`:** đặt mục tiêu số token Claude được dùng cho quá trình suy luận nội bộ; ngân sách lớn hơn có thể cải thiện chất lượng nhờ phân tích kỹ hơn với vấn đề phức tạp.
- **Mô hình hỗ trợ:** xem bảng cấu hình theo từng mô hình trong trang xử lý sự cố thinking, gồm cả các mô hình mà extended thinking là chế độ duy nhất.
- Về bản chất của thinking (thinking block, hình dạng phản hồi, tham số `display`, streaming, thinking với tool use, mã hóa), xem trang tổng quan thinking.

## Các mục trong trang gốc

Mô hình được hỗ trợ · Cách dùng extended thinking · Quy tắc và tinh chỉnh ngân sách · Interleaved thinking ở chế độ thủ công · Cấu trúc lượt ở chế độ thủ công · Prompt caching ở chế độ thủ công · Cơ chế chung · Chuyển sang adaptive thinking · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/extended-thinking)
- [Tổng quan thinking](thinking.md)
- [Steering và kiểm soát chi phí của thinking](thinking-steering-and-cost.md)
- [Xử lý sự cố thinking](thinking-troubleshooting.md)

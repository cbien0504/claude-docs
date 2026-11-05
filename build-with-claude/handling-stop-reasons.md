---
title: Stop reason và dự phòng (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/handling-stop-reasons
description: Tìm hiểu ý nghĩa của từng giá trị stop_reason và cách xử lý việc cắt cụt, tool use, lượt bị tạm dừng và refusal trong ứng dụng của bạn.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/handling-stop-reasons). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Mỗi phản hồi thành công của Messages API có trường `stop_reason` cho biết vì sao Claude dừng sinh nội dung. Trang này giải thích từng giá trị và cách xử lý trong ứng dụng.

## Các điểm chính

- **Các giá trị `stop_reason`:** `end_turn`, `max_tokens`, `stop_sequence`, `tool_use`, `pause_turn`, `refusal` và `model_context_window_exceeded`.
- **Thực hành tốt:** luôn kiểm tra `stop_reason`; xử lý phản hồi bị cắt cụt một cách mềm mại; triển khai logic thử lại cho `pause_turn`.
- **Stop reason khác với lỗi:** stop reason thuộc về các phản hồi thành công, còn lỗi thuộc về các request thất bại.
- **Streaming:** có các lưu ý riêng khi streaming.
- **Mẫu thường gặp:** ví dụ xử lý workflow tool use.

## Các mục trong trang gốc

Tham khảo nhanh · Trường `stop_reason` · Các giá trị stop reason · Thực hành tốt khi xử lý stop reason · Stop reason so với lỗi · Lưu ý khi streaming · Mẫu thường gặp (xử lý workflow tool use) · và các mục còn lại của trang gốc.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/handling-stop-reasons)
- [Refusal và fallback](refusals-and-fallback.md)
- [Server tools](../agents-and-tools/tool-use/server-tools.md)
- [Streaming Messages](streaming.md)

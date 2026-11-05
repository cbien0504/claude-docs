---
title: Thinking trong workflow công cụ và nhiều lượt (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/thinking-tool-workflows
description: Minh họa một vòng đi lại tool use hai lượt hoàn chỉnh, giữ đúng các thinking block, và cách interleaved thinking thay đổi luồng.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/thinking-tool-workflows). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang minh họa một vòng đi lại tool use hai lượt có bật thinking: Claude suy nghĩ, yêu cầu một lệnh gọi công cụ, nhận kết quả rồi hoàn tất câu trả lời, với các thinking block được xử lý đúng ở mọi bước. Ví dụ dùng công cụ `get_weather`; các mẫu dùng adaptive thinking, còn với mô hình chỉ hỗ trợ extended thinking thì thay bằng `thinking: {type: "enabled", budget_tokens: N}` (quy tắc vòng đi lại giống nhau).

## Các điểm chính

Các quy tắc được áp dụng (toàn văn nằm ở trang Thinking):
- **Giới hạn tool choice ở `auto` hoặc `none` trong chế độ thủ công:** các tùy chọn `tool_choice` buộc dùng công cụ sẽ trả lỗi với extended thinking thủ công.
- **Giữ một cấu hình thinking cho mỗi lượt assistant:** một vòng lặp tool use là một lượt assistant, nên chỉ đổi cấu hình giữa các lượt.
- **Truyền lại thinking block đầy đủ và không sửa đổi:** khi trả kết quả công cụ, các thinking block của message assistant phải đi kèm.
- **Lặp lại nguyên văn message assistant như đã nhận:** dựng lại message hoặc lọc bỏ các block `redacted_thinking` sẽ gây lỗi 400.

Walkthrough gồm các bước: gửi request đầu tiên với công cụ khả dụng, giữ mảng nội dung để lặp lại, rồi gửi kết quả công cụ kèm lượt assistant được lặp lại đúng nguyên văn, bao gồm thinking block. Cũng có mục về cách interleaved thinking thay đổi luồng.

## Các mục trong trang gốc

Các quy tắc walkthrough áp dụng · Walkthrough vòng đi lại tool use hai lượt · Interleaved thinking thay đổi luồng thế nào · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/thinking-tool-workflows)
- [Thinking – tổng quan](thinking.md)
- [Xử lý lệnh gọi công cụ](../agents-and-tools/tool-use/handle-tool-calls.md)

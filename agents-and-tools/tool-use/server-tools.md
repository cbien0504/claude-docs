---
title: Server tools (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/server-tools
description: Làm việc với các công cụ do Anthropic chạy: block server_tool_use, tiếp tục sau pause_turn, các lượt trộn server tool và client tool, và lọc domain.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/server-tools). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Các công cụ do server thực thi có chung một số cơ chế: block `server_tool_use`, tiếp tục sau `pause_turn`, các lượt trộn server tool và client tool, tính đủ điều kiện Zero Data Retention (ZDR) và lọc domain.

## Các điểm chính

- **Block `server_tool_use`:** xuất hiện trong phản hồi của Claude khi một công cụ do server thực thi chạy; trường `id` có tiền tố `srvtoolu_` để phân biệt với lệnh gọi client tool. API chạy công cụ bên trong; bạn thấy lệnh gọi và kết quả trong phản hồi nhưng không xử lý việc thực thi, và không cần trả `tool_result` như với block `tool_use` của client. Block kết quả của công cụ (ví dụ `web_search_tool_result` cho web search) đi kèm.
- **Vòng lặp phía máy chủ và `pause_turn`:** với server tool như web search, API chạy các lệnh gọi công cụ trong một vòng lặp agent phía máy chủ; ở lượt chạy dài, API có thể tạm dừng vòng lặp và trả stop reason `pause_turn`. Khi xử lý:
  - **Tiếp tục hội thoại:** truyền nguyên phản hồi tạm dừng trong request kế tiếp để Claude tiếp tục lượt của nó.
  - **Giữ trạng thái công cụ:** đưa cùng các công cụ vào request tiếp tục; một lượt tạm dừng có thể kết thúc bằng block `server_tool_use` mà công cụ chưa chạy, và API trả lỗi xác thực nếu thiếu công cụ đó.
  - **Giữ container:** nếu phản hồi có `container` (như với code execution tool), gửi lại ID của nó trong request tiếp tục, nếu không request sẽ chạy trong container mới.
  - **Lặp lại khi cần:** lượt tiếp tục có thể tạm dừng lần nữa; kiểm tra `stop_reason` ở mỗi phản hồi và tiếp tục đến khi nhận stop reason khác, đồng thời giới hạn số lần tiếp tục như mọi vòng retry. Giữ mọi phản hồi tạm dừng trong `messages`, theo thứ tự.

## Các mục trong trang gốc

Block `server_tool_use` · Vòng lặp phía máy chủ và `pause_turn` · Trộn server tool và client tool trong một lượt · ZDR và `allowed_callers` · Lọc domain · Dynamic filtering với code execution · Streaming các sự kiện server tool · Batch request · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/server-tools)
- [Web search tool](web-search-tool.md)
- [Web fetch tool](web-fetch-tool.md)
- [Code execution tool](code-execution-tool.md)
- [Tham chiếu công cụ](tool-reference.md)

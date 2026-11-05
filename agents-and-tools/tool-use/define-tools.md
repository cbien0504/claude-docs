---
title: Định nghĩa công cụ (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/define-tools
description: Chỉ định schema công cụ, viết mô tả hiệu quả và kiểm soát khi nào Claude gọi công cụ của bạn.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/define-tools). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang này hướng dẫn cách khai báo client tool: schema, mô tả, ví dụ sử dụng và cách kiểm soát đầu ra của Claude. Cách dùng khác nhau theo sản phẩm: trong Messages API, bạn định nghĩa công cụ trong `tools` của request và gửi kết quả bằng các block `tool_result`; trong Managed Agents, khai báo trên agent với `type` là `"custom"` và các lệnh gọi đến dưới dạng sự kiện `agent.custom_tool_use`.

## Các điểm chính

- **Điều kiện tiên quyết:** hiểu phần tổng quan về tool use; có Claude API key và thiết lập SDK hoặc cURL hoạt động. Nếu dùng tool use cùng thinking, xem trang Thinking.
- **Khai báo client tool** trong tham số cấp cao nhất `tools`. Công cụ có schema do Anthropic định nghĩa (như bash, text editor) khai báo bằng `type` có phiên bản theo ngày. Với công cụ của bạn, các tham số chính là:
  - `name`: tên công cụ, phải khớp regex `^[a-zA-Z0-9_-]{1,128}$`.
  - `description`: mô tả văn bản thuần chi tiết về việc công cụ làm gì, khi nào nên dùng và hành vi của nó.
  - `input_schema`: một đối tượng JSON Schema xác định các tham số đầu vào mong đợi.
- **Cung cấp ví dụ sử dụng công cụ** (cách dùng cơ bản, yêu cầu và hạn chế).
- **Kiểm soát đầu ra của Claude:** buộc dùng công cụ, và cách mô hình phản hồi khi có công cụ.

## Các mục trong trang gốc

Điều kiện tiên quyết · Chỉ định client tool (system prompt của tool use, thực hành tốt khi định nghĩa công cụ) · Cung cấp ví dụ tool use · Kiểm soát đầu ra của Claude (buộc dùng công cụ, phản hồi của mô hình khi có công cụ) · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/define-tools)
- [Tổng quan sử dụng công cụ](overview.md)
- [Xử lý lệnh gọi công cụ](handle-tool-calls.md)
- [Strict tool use](strict-tool-use.md)
- [Công cụ và MCP server tùy chỉnh trong Managed Agents](../../managed-agents/tools.md)

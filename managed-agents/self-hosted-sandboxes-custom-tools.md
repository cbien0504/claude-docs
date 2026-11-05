---
title: Công cụ tùy chỉnh trong sandbox tự lưu trữ (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-custom-tools
description: Phục vụ công cụ tùy chỉnh từ worker của sandbox tự lưu trữ, và bao bọc một MCP server bên trong mạng của bạn thành công cụ tùy chỉnh mà không cần chạy tunnel.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-custom-tools). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Công cụ tùy chỉnh là công cụ do code của chính bạn chạy: agent phát ra sự kiện `agent.custom_tool_use` rồi chờ `user.custom_tool_result` tương ứng. Worker của bạn có thể chính là phần code đó. Khóa environment cấp quyền đăng kết quả công cụ tùy chỉnh, nên Claude API key của bạn không phải nằm trên host của worker.

> **Lưu ý:** phục vụ công cụ tùy chỉnh cần SDK worker. Worker của CLI `ant` không có cách đăng ký triển khai công cụ tùy chỉnh. Trong mẫu sandbox-cho-mỗi-session, hãy chạy SDK worker bên trong sandbox.

## Các điểm chính

- **Phục vụ một công cụ tùy chỉnh:** khai báo công cụ trên agent (thêm mục `custom` vào `tools` của agent với `name` khớp tên công cụ worker đăng ký), rồi đăng ký phần triển khai với worker.
- **Bao bọc một MCP server thành công cụ tùy chỉnh:** cài một MCP SDK, rồi khai báo và phục vụ các công cụ.
- **Giới hạn và hành vi:** công cụ được khai báo chứ không được khám phá lúc chạy; khai báo phải vừa với Managed Agents API; lỗi của công cụ hiện ra dưới dạng kết quả công cụ báo lỗi; chỉ bao bọc các server bạn vận hành hoặc tin cậy; chính sách quyền (permission policies) không áp dụng.

## Các mục trong trang gốc

Phục vụ một công cụ tùy chỉnh · Bao bọc một MCP server thành công cụ tùy chỉnh (cài MCP SDK, khai báo và phục vụ công cụ) · Giới hạn và hành vi.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-custom-tools)
- [Công cụ](tools.md)
- [Triển khai worker](self-hosted-sandboxes-workers.md)
- [Sandbox tự lưu trữ](self-hosted-sandboxes.md)

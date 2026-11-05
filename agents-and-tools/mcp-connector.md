---
title: MCP connector (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/mcp-connector
description: Kết nối trực tiếp tới các MCP server từ xa ngay từ Messages API mà không cần MCP client, đồng thời cho phép đưa vào danh sách cho phép, danh sách chặn hoặc cấu hình từng công cụ.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/mcp-connector). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Tính năng MCP connector của Claude cho phép kết nối tới các MCP server từ xa trực tiếp từ Messages API mà không cần một MCP client riêng. Phiên bản trước của tính năng (`mcp-client-2025-04-04`) đã bị ngừng khuyến khích (deprecated).

## Các điểm chính

- **Cách dùng theo bề mặt:** trong Messages API, truyền `mcp_servers` và một `mcp_toolset` tương ứng trong `tools` ở mỗi request; trong Managed Agents, khai báo MCP server trên agent, mỗi session cấp credential bằng cách tham chiếu một vault để bí mật không nằm trong định nghĩa agent.
- **Tính năng chính:** tích hợp API trực tiếp (không cần tự viết MCP client); hỗ trợ gọi công cụ; cấu hình công cụ linh hoạt (bật tất cả, đưa vào danh sách cho phép (allowlist) hoặc danh sách chặn (denylist)); cấu hình riêng cho từng công cụ; xác thực OAuth bằng Bearer token; kết nối nhiều server trong một request.
- **Khi nào Claude dùng công cụ MCP:** khi yêu cầu của người dùng khớp với khả năng mà công cụ mô tả, hoặc nói rõ ("tìm các bug đang mở trên Jira") hoặc ngầm ("điều gì đang chặn bản phát hành?" khi đã gắn server Jira). Claude **không** gọi công cụ MCP cho câu hỏi kiến thức chung về một dịch vụ đã kết nối (ví dụ hỏi cách cơ sở dữ liệu Notion hoạt động thì được trả lời trực tiếp, còn hỏi "trong cơ sở dữ liệu Projects của tôi có gì?" thì kích hoạt công cụ). Có thể điều chỉnh mức sẵn sàng gọi công cụ qua system prompt.
- **Hạn chế:**
  - Trong các tính năng của đặc tả MCP, hiện chỉ hỗ trợ gọi công cụ (tool calls).
  - Server phải được công khai qua HTTP (hỗ trợ cả Streamable HTTP và SSE); server STDIO cục bộ không kết nối trực tiếp được.
- **Hai thành phần khi dùng trong Messages API:** định nghĩa MCP server (mảng `mcp_servers`: URL, xác thực) và MCP toolset (mảng `tools`: chọn công cụ nào được bật và cấu hình ra sao).

## Các mục trong trang gốc

Tính năng chính · Khi nào Claude dùng công cụ MCP · Hạn chế · Dùng MCP connector trong Messages API · Cấu hình MCP server · Cấu hình MCP toolset · Các mẫu cấu hình thường gặp (bật tất cả, allowlist, denylist, kết hợp) · Quy tắc xác thực hợp lệ · Các loại nội dung trong phản hồi (block MCP tool use, MCP tool result) · Ghim danh sách công cụ của MCP server (beta) · Nhiều MCP server · Xác thực.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/mcp-connector)
- [Remote MCP servers](remote-mcp-servers.md)
- [MCP connector trong Managed Agents](../managed-agents/mcp-connector.md)
- [Tổng quan MCP tunnels](mcp-tunnels/overview.md)

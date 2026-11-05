---
title: MCP connector trong Managed Agents (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/mcp-connector
description: Kết nối các MCP server với agent của bạn để truy cập công cụ và nguồn dữ liệu bên ngoài.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/mcp-connector). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Claude Managed Agents hỗ trợ kết nối các Model Context Protocol (MCP) server với agent, cho agent truy cập công cụ, nguồn dữ liệu và dịch vụ bên ngoài qua một giao thức chuẩn. Cấu hình MCP chia làm hai bước: **tạo agent** khai báo agent kết nối tới những MCP server nào (theo tên và URL), và **tạo session** cung cấp xác thực cho các server đó bằng cách tham chiếu một vault đã đăng ký trước. Cách tách này giữ bí mật ra khỏi định nghĩa agent tái sử dụng, trong khi mỗi session vẫn xác thực bằng credential riêng.

## Các điểm chính

- **Khai báo MCP server trên agent:** chỉ định trong mảng `mcp_servers` khi tạo agent; mỗi server có `type` là `url`, một `name` duy nhất và `url`. Mỗi server đã khai báo cũng cần một mục `mcp_toolset` khớp trong mảng `tools`, với `mcp_server_name` trùng `name` của server.
- **Chính sách quyền mặc định:** MCP toolset mặc định dùng chính sách quyền `always_ask`, yêu cầu người dùng duyệt trước mỗi lệnh gọi công cụ; xem trang Permission policies để cấu hình.
- Trang cũng nói về chọn công cụ MCP nào khả dụng, cách xử lý đầu ra của công cụ MCP, cung cấp xác thực khi tạo session và xử lý lỗi kết nối và xác thực.

## Các mục trong trang gốc

Khai báo MCP server trên agent (tham chiếu trường `mcp_servers`) · Cấu hình công cụ MCP khả dụng (xử lý đầu ra công cụ MCP) · Cung cấp xác thực khi tạo session (xử lý lỗi kết nối và xác thực) · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/mcp-connector)
- [Xác thực bằng vault](vaults.md)
- [Permission policies](permission-policies.md)
- [MCP connector (Messages API)](../agents-and-tools/mcp-connector.md)

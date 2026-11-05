---
title: Quản lý tunnel trong Claude Console (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/console
description: Tạo tunnel, đăng ký chứng chỉ CA, lấy tunnel token và gắn các MCP server qua tunnel vào agent từ Claude Console.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/console). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang này nói về phía Console của một triển khai MCP tunnels: tạo tunnel, đăng ký chứng chỉ CA, lấy tunnel token và gắn các MCP server upstream vào một agent. MCP tunnels đang ở dạng research preview.

## Các điểm chính

Điều kiện tiên quyết:
- **Một hoặc nhiều MCP server** chạy trong mạng riêng của bạn. Tunnel chỉ định tuyến lưu lượng tới chúng chứ không lưu trữ chúng.
- **Vai trò Console có quyền "Manage tunnels"** để tạo và lưu trữ (archive) tunnel, xoay vòng token và quản lý chứng chỉ. Quản trị viên và chủ sở hữu tổ chức có quyền này mặc định; vai trò tùy chỉnh và cấp quyền theo tài khoản cũng có thể bao gồm. Vai trò không có quyền này chỉ được truy cập chỉ đọc.
- **Cách để stack xác thực với Tunnels API:** truy cập theo chương trình (khuyến nghị, thiết lập Workload Identity Federation khi tạo tunnel) hoặc thủ công (sau khi tạo tunnel, lấy tunnel token).

Tunnel thuộc phạm vi workspace: tunnel mới thuộc workspace đang chọn trong Console.

## Các mục trong trang gốc

Điều kiện tiên quyết · Tạo tunnel · Lấy thông tin kết nối · Thêm chứng chỉ CA · Triển khai tunnel stack · Dùng tunnel trong agent · Lưu trữ (archive) tunnel · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/console)
- [Tổng quan MCP tunnels](overview.md)
- [Quickstart](quickstart.md)
- [Remote MCP servers](../remote-mcp-servers.md)

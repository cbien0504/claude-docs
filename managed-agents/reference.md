---
title: Tham chiếu Managed Agents (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/reference
description: Các loại sự kiện, cờ CLI của worker tự lưu trữ, các loại MCP server được hỗ trợ, giới hạn tốc độ và hướng dẫn về thương hiệu cho Claude Managed Agents.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/reference). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang tập hợp tài liệu tra cứu cho Claude Managed Agents; với hướng dẫn theo tác vụ, hãy theo các liên kết trong từng mục.

## Các điểm chính

- **Các loại sự kiện:** chuỗi tên loại sự kiện được lưu bền theo quy ước `{domain}.{action}`; ngoại lệ là các event delta chỉ có trên stream. Trang chia theo các tab (sự kiện người dùng, và các tab khác). Một số sự kiện người dùng:
  - `user.message`: tin nhắn của người dùng với nội dung văn bản, hình ảnh hoặc tài liệu.
  - `user.interrupt`: dừng agent khi đang chạy.
  - `user.custom_tool_result`: phản hồi cho lệnh gọi công cụ tùy chỉnh từ agent.
  - `user.tool_confirmation`: phê duyệt hoặc từ chối lệnh gọi công cụ agent/MCP khi permission policy yêu cầu xác nhận.
  - `user.define_outcome`: định nghĩa một outcome để agent hướng tới.
  - `user.tool_result`: dành cho session có environment `self_hosted`.
- **Worker tự lưu trữ:** các cờ CLI.
- **Các loại MCP server được hỗ trợ.**
- **Giới hạn tốc độ** và **hướng dẫn về thương hiệu.**

## Các mục trong trang gốc

Các loại sự kiện · Worker tự lưu trữ · Các loại MCP server được hỗ trợ · Giới hạn tốc độ · Hướng dẫn về thương hiệu.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/reference)
- [Session event stream](events-and-streaming.md)
- [Session operations](session-operations.md)
- [Tổng quan Claude Managed Agents](overview.md)

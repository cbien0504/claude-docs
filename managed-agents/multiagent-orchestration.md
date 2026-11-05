---
title: Điều phối multiagent (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/multiagent-orchestration
description: Điều phối nhiều agent trong cùng một session.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/multiagent-orchestration). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang mô tả cách điều phối nhiều agent trong một session duy nhất: giao việc cho các agent khác, dùng agent định nghĩa sẵn và agent nội tuyến, ủy quyền cho subagent, workflow động, và gắn advisor cho session.

## Các điểm chính

- **Giao việc cho agent khác;** **agent định nghĩa sẵn và agent nội tuyến** (predefined và inline).
- **Ủy quyền cho subagent:** nên ủy quyền việc gì; cách hoạt động; liệt kê subagent; tạo session; kết nối agent với MCP server; threads.
- **Workflow động (dynamic workflows):** bật workflow động và cho agent biết khi nào nên dùng một lần chạy (run).
- **Cho session một advisor:** cách các lần tham vấn hoạt động, advisor thread, gỡ advisor. Advisor được đặt trong khối `multiagent` của agent (không có tùy chọn `max_uses` hay `max_tokens`).
- **Chuyển từ kiểu `coordinator`.**

## Các mục trong trang gốc

Giao việc cho agent khác · Agent định nghĩa sẵn và nội tuyến · Ủy quyền cho subagent · Workflow động · Cho session một advisor · Chuyển từ kiểu `coordinator` · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/multiagent-orchestration)
- [Session threads](session-threads.md)
- [Workflow runs](workflow-runs.md)
- [Advisor tool](../agents-and-tools/tool-use/advisor-tool.md)

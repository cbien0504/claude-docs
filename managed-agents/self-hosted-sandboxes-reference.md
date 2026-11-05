---
title: Tham chiếu worker tự lưu trữ (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-reference
description: Tham chiếu cho các worker của sandbox tự lưu trữ: cờ CLI ant, biến môi trường, yêu cầu về host, đường dẫn hệ thống file và các tùy chọn helper của SDK.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-reference). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang ghi lại các worker dựng sẵn phục vụ một environment `self_hosted`. Với hướng dẫn theo tác vụ, hãy bắt đầu từ trang sandbox tự lưu trữ và trang triển khai worker.

## Các điểm chính

- **Lệnh CLI:**
  - `ant beta:worker poll`: nhận work item từ hàng đợi của environment và chạy mỗi session trong cùng tiến trình; với `--on-work`, gọi script của bạn cho mỗi work item.
  - `ant beta:worker run`: xử lý một session đã nhận rồi thoát; dùng làm entrypoint của sandbox theo từng session.
  - Trang gốc còn có bảng các cờ (flag).
- **Biến môi trường, yêu cầu về host và hệ thống file của sandbox.**
- **Helper của SDK:** `EnvironmentWorker`, work poller, session tool runner, và `AgentToolContext` cùng toolset của agent.

## Các mục trong trang gốc

Lệnh CLI và cờ · Biến môi trường · Yêu cầu về host · Hệ thống file của sandbox · Helper SDK (EnvironmentWorker, work poller, session tool runner, AgentToolContext và agent toolset).

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-reference)
- [Sandbox tự lưu trữ](self-hosted-sandboxes.md)
- [Triển khai worker](self-hosted-sandboxes-workers.md)
- [Giám sát và xử lý sự cố](self-hosted-sandboxes-operations.md)

---
title: Session threads (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/session-threads
description: Liệt kê, ngắt và lưu trữ các thread của một session multiagent, đọc sự kiện của chúng và xử lý quyền công cụ giữa các thread.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/session-threads). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trong một session multiagent, mỗi agent làm việc trong **session thread** riêng. Trang này nói về cách liệt kê, ngắt và lưu trữ các thread, các sự kiện chúng gửi và cách quyền công cụ hoạt động giữa các thread.

## Các điểm chính

- **Thread chính và session thread:** luồng sự kiện cấp session (`/v1/sessions/{session_id}/events/stream`) được coi là **thread chính**, chứa cái nhìn cô đọng về mọi hoạt động trên tất cả thread; bạn không thấy toàn bộ hoạt động của các subagent ở đó. **Session thread** là nơi bạn xem hoạt động của một agent cụ thể.
- **Trạng thái session** là tổng hợp mọi hoạt động của agent: nếu có ít nhất một thread đang `running` thì trạng thái chung của session cũng là `running`.
- **Ngân sách session** là một trần chung cho mọi thread của session; khi chạm trần, các thread tạm dừng độc lập, và chi phí của mỗi thread được tính theo mô hình mà thread đó dùng.
- Trang cũng nói về liệt kê thread, ngắt thread, lưu trữ thread, sự kiện của thread chính và của session thread, và quyền công cụ cùng công cụ tùy chỉnh.

## Các mục trong trang gốc

Thread chính và session thread · Liệt kê thread · Ngắt session thread · Lưu trữ session thread · Sự kiện của thread chính · Sự kiện của session thread · Quyền công cụ và công cụ tùy chỉnh · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/session-threads)
- [Điều phối multiagent](multiagent-orchestration.md)
- [Session budgets](budgets.md)
- [Workflow runs](workflow-runs.md)

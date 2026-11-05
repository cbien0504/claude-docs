---
title: Session operations (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/session-operations
description: Lấy, liệt kê, cập nhật, lưu trữ và xóa các session Claude Managed Agents.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/session-operations). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Khi một session đã tồn tại, dùng các thao tác này để đọc, cập nhật, lưu trữ (archive) hoặc xóa nó. Để tạo session và gửi việc cho nó, xem trang "Bắt đầu một session".

## Các điểm chính

- **Trạng thái của session:** các trạng thái bao gồm:
  - `idle`: agent đang chờ đầu vào, gồm tin nhắn người dùng hoặc xác nhận công cụ. Session tạo mà không có `initial_events` bắt đầu ở trạng thái `idle`.
  - `running`: agent đang thực thi.
  - `rescheduling`: đã xảy ra lỗi tạm thời và hệ thống đang tự thử lại.
  - (Các trạng thái khác được liệt kê trong trang gốc.)
- **Cập nhật cấu hình agent** và **cập nhật ngân sách của session.**
- **Lấy một session, liệt kê session, lưu trữ session và xóa session.**

## Các mục trong trang gốc

Trạng thái session · Cập nhật cấu hình agent · Cập nhật ngân sách session · Lấy session · Liệt kê session · Lưu trữ session · Xóa session.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/session-operations)
- [Bắt đầu một session](sessions.md)
- [Session budgets](budgets.md)

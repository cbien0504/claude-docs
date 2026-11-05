---
title: Di chuyển sang Managed Agents (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/migration
description: Chuyển một agent hiện có xây dựng trên Messages API hoặc Claude Agent SDK sang Claude Managed Agents.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/migration). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Claude Managed Agents thay vòng lặp agent bạn tự viết bằng hạ tầng được quản lý. Trang này nói về những gì thay đổi khi bạn chuyển từ một vòng lặp tùy chỉnh xây trên Messages API, hoặc từ Claude Agent SDK, sang Managed Agents.

## Các điểm chính

- **Từ vòng lặp agent của Messages API** (agent gọi `client.messages.create()` trong một vòng lặp): trang có bảng "Trước/Sau". Ví dụ, trước đây bạn tự duy trì mảng lịch sử hội thoại và truyền lại ở mọi lượt; sau khi chuyển, session lưu lịch sử phía máy chủ, còn bạn gửi và nhận sự kiện. Trang cũng nói về những thứ bạn thôi phải quản lý, so sánh code và những gì bạn vẫn kiểm soát.
- **Từ Claude Agent SDK:** những gì thay đổi, so sánh code, và các tính năng chuyển sang phía client của bạn.
- **Danh sách kiểm tra khi di chuyển** và phần **di chuyển giữa các phiên bản mô hình.**

## Các mục trong trang gốc

Từ vòng lặp agent của Messages API (những gì bạn thôi quản lý, so sánh code, những gì bạn vẫn kiểm soát) · Từ Claude Agent SDK (những gì thay đổi, so sánh code, tính năng chuyển sang client) · Danh sách kiểm tra di chuyển · Di chuyển giữa các phiên bản mô hình.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/migration)
- [Tổng quan Claude Managed Agents](overview.md)
- [Quickstart](quickstart.md)
- [Sử dụng Messages API](../build-with-claude/working-with-messages.md)

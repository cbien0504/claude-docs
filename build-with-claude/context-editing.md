---
title: Context editing (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/context-editing
description: Tự động quản lý ngữ cảnh hội thoại khi nó lớn dần bằng context editing.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/context-editing). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Context editing giúp tự động quản lý ngữ cảnh hội thoại khi nó lớn dần. Trang mô tả các chiến lược phía máy chủ, cách cấu hình, định dạng phản hồi và cách dùng cùng các tính năng khác; phần cuối nói về compaction phía client trong SDK.

## Các điểm chính

- **Hai chiến lược phía máy chủ:** xóa kết quả công cụ (tool result clearing) và xóa thinking block (thinking block clearing). Context editing diễn ra phía máy chủ; trang cũng giải thích tương tác với prompt caching và danh sách mô hình được hỗ trợ.
- **Cấu hình:** có mục cấu hình nâng cao cho tool result clearing, các tùy chọn cấu hình cho thinking block clearing và cách kết hợp hai chiến lược.
- **Phản hồi và đếm token:** có mục về định dạng phản hồi của context editing và về đếm token.
- **Dùng với memory tool.**
- **Compaction phía client (SDK):** cách hoạt động, cách dùng (điều gì diễn ra khi compaction), các tùy chọn (chọn ngưỡng token, dùng mô hình khác để tóm tắt, prompt tóm tắt tùy chỉnh), prompt tóm tắt mặc định, hạn chế (server tool, các trường hợp biên của tool use), theo dõi compaction và khi nào nên dùng.

## Các mục trong trang gốc

Tổng quan · Chiến lược phía máy chủ (tool result clearing, thinking block clearing, context editing diễn ra phía máy chủ, context editing và prompt caching) · Mô hình được hỗ trợ · Cách dùng tool result clearing · Cách dùng thinking block clearing · Tùy chọn cấu hình tool result clearing · Phản hồi của context editing · Đếm token · Dùng với memory tool · Compaction phía client (SDK).

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/context-editing)
- [Cửa sổ ngữ cảnh](context-windows.md)
- [Tổng quan compaction](compaction.md)
- [Memory tool](../agents-and-tools/tool-use/memory-tool.md)

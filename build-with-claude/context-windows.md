---
title: Cửa sổ ngữ cảnh (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/context-windows
description: Hiểu cách cửa sổ ngữ cảnh hoạt động, extended thinking và tool use được tính vào đó thế nào, và cách quản lý ngữ cảnh khi hội thoại dài ra.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/context-windows). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Khi hội thoại dài ra, bạn sẽ dần tiến sát giới hạn cửa sổ ngữ cảnh (context window). Với hội thoại chạy lâu và workflow agent, compaction phía máy chủ là chiến lược chính để quản lý ngữ cảnh.

## Các điểm chính

- **Cửa sổ ngữ cảnh là gì:** toàn bộ văn bản mà mô hình có thể tham chiếu khi sinh phản hồi, bao gồm cả chính phản hồi đó. Nó khác với kho dữ liệu huấn luyện lớn của mô hình; có thể hiểu là "bộ nhớ làm việc" của mô hình. Kích thước cửa sổ lên tới 1M token, tùy mô hình.
- **Hành vi chuẩn của request API:** token tích lũy dần qua các lượt, các lượt trước được giữ nguyên hoàn toàn; mỗi lượt gồm pha đầu vào (toàn bộ lịch sử cộng message hiện tại của người dùng) và pha đầu ra (phản hồi văn bản trở thành một phần đầu vào của lượt sau). Giao diện chat như claude.ai cũng có thể quản lý cửa sổ theo kiểu "vào trước ra trước".
- **Những gì được tính:** mọi thứ trong request đều tính vào cửa sổ ngữ cảnh: system prompt, mọi message trong `messages` (gồm kết quả công cụ, hình ảnh và tài liệu) và định nghĩa công cụ. Đầu ra Claude sinh ra trong lượt đó, kể cả extended thinking, cũng được tính.

## Các mục trong trang gốc

Cách cửa sổ ngữ cảnh hoạt động · Kích thước cửa sổ theo mô hình · Cửa sổ ngữ cảnh với thinking · Cửa sổ ngữ cảnh với thinking và tool use · Nhận biết ngữ cảnh (context awareness) · Quản lý ngữ cảnh bằng compaction · Hành vi khi cửa sổ ngữ cảnh bị tràn · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/context-windows)
- [Tổng quan compaction](compaction.md)
- [Context editing](context-editing.md)
- [Extended thinking](extended-thinking.md)

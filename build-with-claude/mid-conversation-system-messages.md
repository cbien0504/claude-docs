---
title: System message giữa hội thoại và thay đổi công cụ (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/mid-conversation-system-messages
description: Thay đổi chỉ dẫn hệ thống hoặc tính khả dụng của công cụ giữa chừng một cuộc hội thoại mà không làm mất hiệu lực tiền tố đã được cache phía trước.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/mid-conversation-system-messages). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Chỉ dẫn hệ thống thường nằm ở trường `system` cấp cao nhất, đứng trước mọi message trong hội thoại. Vị trí đó rất tốt cho prompt caching vì system prompt là một phần của tiền tố ổn định. Nhưng khi cần đổi chỉ dẫn giữa chừng, sửa trường `system` sẽ làm mất hiệu lực cache. System message giữa hội thoại giải quyết khoảng trống này: bạn chèn một message `{"role": "system"}` tại điểm trong hội thoại mà chỉ dẫn mới bắt đầu có liên quan, thay vì sửa trường `system`. Tiền tố đã cache không đổi, nên request kế tiếp vẫn đọc được từ cache.

## Các điểm chính

- **Cách dùng theo bề mặt:** trong Messages API, thêm một message có `role` là `"system"` vào `messages` tại điểm chỉ dẫn bắt đầu áp dụng; trong Managed Agents, gửi sự kiện `system.message`: nó áp dụng cho lượt đó và mọi lượt sau, còn trường `system` của chính agent không thể thay đổi trong một session.
- **Mô hình hỗ trợ:** khả dụng trên nhiều mô hình mới (ví dụ Claude Fable 5.1, Claude Mythos 5.1, Claude Fable 5, Claude Mythos 5, Claude Opus 5.5…); danh sách đầy đủ có trong trang gốc.
- **Thay đổi công cụ giữa hội thoại (beta):** định nghĩa công cụ trong một message, và thêm MCP server giữa hội thoại, trên cùng các mô hình.
- **System message theo lượt (turn-scoped):** dùng `clear_at`, đang ở dạng beta và cần beta header.

## Các mục trong trang gốc

Thay đổi công cụ giữa hội thoại (định nghĩa công cụ trong message (beta), thêm MCP server giữa hội thoại (beta)) · Khi nào dùng system message giữa hội thoại · Cách hoạt động (vị trí sau kết quả công cụ, system message theo lượt) · Kết hợp với prompt caching · Hạn chế · Liên quan · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/mid-conversation-system-messages)
- [Prompt caching](prompt-caching.md)
- [Preserved thinking](preserved-thinking.md)
- [Xây dựng chế độ orchestration](mid-conversation-effort-example.md)

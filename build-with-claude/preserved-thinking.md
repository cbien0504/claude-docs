---
title: Preserved thinking (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/preserved-thinking
description: Preserved thinking cho phép một mô hình dùng thinking block từ lượt trước chỉ khi chính mô hình đó, hoặc một trong tập mô hình cố định khác, đã tạo ra nó và không có gì phía trước block bị thay đổi.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/preserved-thinking). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Với preserved thinking, mô hình chỉ dùng lại một thinking block từ lượt trước nếu block đó do chính mô hình ấy (hoặc một trong tập mô hình cố định khác) tạo ra và mọi thứ phía trước block không bị thay đổi. Phép kiểm tra "tiền tố" (prefix check) này quyết định thinking cũ còn hợp lệ hay không.

## Các điểm chính

- **Điều gì ảnh hưởng đến phép kiểm tra tiền tố:** đổi mô hình giữa hội thoại; thinking block gắn với tài khoản đã tạo ra chúng; mọi chỉnh sửa trong tiền tố.
- **Khi block không hợp lệ:** hành vi phụ thuộc vào tham số `prefix_mismatch_behavior`. Khi không đặt, request trả lỗi 400; có chế độ `"drop_block"` (kèm lưu ý về chi phí token đầu ra) và trường `input_transformations` trong phản hồi để biết API đã làm gì. Trang có phần hướng dẫn xử lý lỗi trong code.
- **Thế nào là "chỉnh sửa"** và cách kiểm tra code của bạn có sửa tiền tố hay không.
- **Thay đổi mà không sửa tiền tố:** gửi lại các lượt assistant đúng như đã nhận; thêm chỉ dẫn bằng system message giữa hội thoại; đặt ngữ cảnh thay đổi vào lượt mới nhất; gửi lời nhắc theo lượt bằng system message theo lượt; thêm/bớt công cụ với `tool_addition` và `tool_removal`; đổi effort bằng `output_config` theo từng message; cắt bớt ngữ cảnh phía máy chủ; compact phía client (cách đơn giản được khuyến nghị).

## Các mục trong trang gốc

Ai chịu ảnh hưởng của phép kiểm tra tiền tố · Đổi mô hình giữa hội thoại · Thinking block gắn với tài khoản đã tạo ra chúng · Giữ tiền tố không đổi (API làm gì với block không hợp lệ, đặt hành vi khi không khớp và đọc `input_transformations`, thế nào là chỉnh sửa, kiểm tra code có sửa tiền tố không) · Thay đổi mà không sửa tiền tố (các cách nêu trên).

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/preserved-thinking)
- [Giữ thinking block hợp lệ khi compaction](compaction-thinking-blocks.md)
- [System message giữa hội thoại](mid-conversation-system-messages.md)
- [Tổng quan thinking](thinking.md)

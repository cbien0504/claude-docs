---
title: Thinking – tổng quan (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/thinking
description: Hiểu cách thinking của Claude hoạt động: bật nó, đọc đầu ra thinking, điều hướng độ sâu bằng effort, và dùng thinking với công cụ, caching và streaming.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/thinking). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang tổng quan về thinking của Claude: cách thinking hoạt động, cách cấu hình (kể cả tắt), cách đọc đầu ra thinking, mối quan hệ với effort, và cách dùng thinking với tool use, prompt caching, cửa sổ ngữ cảnh và streaming.

## Các điểm chính

- **Đọc đầu ra thinking:** điều khiển cách hiển thị thinking, thinking dạng tóm tắt (summarized), streaming thinking.
- **Thinking và effort:** effort là cách được khuyến nghị để điều hướng độ sâu thinking ở nơi có adaptive thinking.
- **Thinking với tool use:** giữ nguyên thinking block, interleaved thinking, cập nhật tiến độ giữa các lệnh gọi công cụ, và việc bảo toàn thinking block theo từng mô hình.
- **Preserved thinking** và mối quan hệ giữa **thinking với prompt caching** và **thinking với cửa sổ ngữ cảnh**.
- **Mã hóa thinking** và **các thinking block bị che (redacted)**.
- **Giới hạn và tương thích tính năng:** gồm các tham số lấy mẫu.

## Các mục trong trang gốc

Cách thinking hoạt động · Cấu hình thinking (tắt thinking) · Đọc đầu ra thinking · Thinking và effort · Thinking với tool use · Preserved thinking · Thinking và prompt caching · Thinking và cửa sổ ngữ cảnh · Mã hóa thinking · Thinking block bị che · Giới hạn và tương thích tính năng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/thinking)
- [Điều hướng thinking](thinking-steering-and-cost.md)
- [Thinking trong workflow công cụ và nhiều lượt](thinking-tool-workflows.md)
- [Xử lý sự cố thinking](thinking-troubleshooting.md)
- [Preserved thinking](preserved-thinking.md)

---
title: Fast mode (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/fast-mode
description: Đạt tới 2,5 lần số token đầu ra mỗi giây từ các mô hình Claude được hỗ trợ.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/fast-mode). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Fast mode mang lại tới 2,5 lần số token đầu ra mỗi giây với mức giá cao cấp (premium). Bạn bật bằng `speed: "fast"` trên request. Tính năng khả dụng trên Claude Opus 5.5, và ở dạng research preview trên Claude Opus 5 và Claude Opus 4.8.

## Các điểm chính

- **Cách dùng theo bề mặt:** trong Messages API, đặt `speed: "fast"` trên request; trong Managed Agents, đặt `speed` trên đối tượng model của agent, ví dụ `{"id": "claude-opus-5-5", "speed": "fast"}`.
- **Cách hoạt động:** chạy cùng một mô hình với cấu hình suy luận nhanh hơn; trí tuệ và khả năng không thay đổi. Lợi ích tập trung vào số token đầu ra mỗi giây (OTPS), không phải thời gian tới token đầu tiên (TTFT). Tương thích với streaming, nơi mức tăng OTPS thể hiện rõ nhất.
- Trang gốc còn có các mục về giới hạn tốc độ, kiểm tra tốc độ thực tế đã dùng, thử lại tự động và quay về tốc độ tiêu chuẩn, lưu ý, giá.

## Các mục trong trang gốc

Cách fast mode hoạt động · Cách dùng cơ bản · Giới hạn tốc độ · Kiểm tra tốc độ đã dùng · Thử lại và dự phòng (thử lại tự động, quay về tốc độ tiêu chuẩn) · Lưu ý · Giá · Tính khả dụng · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/fast-mode)
- [Streaming Messages](streaming.md)
- [Effort](effort.md)

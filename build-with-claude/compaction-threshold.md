---
title: Compaction theo ngưỡng token (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/compaction-threshold
description: Để API tự động tóm tắt ngữ cảnh cũ, ngay trong một request thông thường, khi hội thoại đạt ngưỡng token do bạn đặt.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/compaction-threshold). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Với compaction theo ngưỡng token, API tự động tóm tắt ngữ cảnh cũ ngay trong một request thông thường khi hội thoại đạt ngưỡng token bạn đặt. Cách dùng khác nhau theo sản phẩm: trong Messages API, bạn chọn tham gia bằng một chỉnh sửa (edit) `compact_20260112`, và compaction mặc định bắt đầu ở 150.000 token đầu vào.

## Các điểm chính

- **Tham số:** cấu hình điều kiện kích hoạt (trigger), hướng dẫn tóm tắt tùy chỉnh, tạm dừng sau compaction, và áp một ngân sách token tổng.
- **Làm việc với block compaction:** truyền block compaction ngược lại cho các request sau, streaming, prompt caching (kể cả cách tối đa hóa số lần trúng cache bằng system prompt).
- **Hiểu mức sử dụng (usage)** và kết hợp với các tính năng khác (server tool, đếm token).
- **Hạn chế hiện tại** và các ví dụ được nêu ở các mục riêng.
- Tính năng cần beta header; tham khảo mục "Tính khả dụng" của trang gốc.

## Các mục trong trang gốc

Cách compaction hoạt động · Cách dùng cơ bản · Tham số (cấu hình trigger, hướng dẫn tóm tắt tùy chỉnh, tạm dừng sau compaction, áp ngân sách token tổng) · Làm việc với block compaction (truyền lại block, streaming, prompt caching) · Hiểu mức sử dụng · Kết hợp với tính năng khác (server tool, đếm token) · Ví dụ · Hạn chế hiện tại · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/compaction-threshold)
- [Tổng quan compaction](compaction.md)
- [Compaction theo yêu cầu](compaction-on-demand.md)
- [Prompt caching](prompt-caching.md)
- [Đếm token](token-counting.md)

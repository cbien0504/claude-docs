---
title: Tổng quan về compaction (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/compaction
description: Tìm hiểu compaction làm gì, compaction theo yêu cầu khác compaction theo ngưỡng token ra sao, và trang nào phù hợp với tác vụ của bạn.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/compaction). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Compaction thay các lượt cũ của một cuộc hội thoại bằng một bản tóm tắt do Claude viết ngay trên máy chủ, nên bạn không cần tự viết code tóm tắt. Nó giữ một cuộc hội thoại dài hoặc một tác vụ agent nằm trong cửa sổ ngữ cảnh (context window) và giữ cho ngữ cảnh đang hoạt động ở mức nhỏ.

## Các điểm chính

- **Hai cách compact:**
  - **Compaction theo yêu cầu (on demand):** ứng dụng của bạn quyết định khi nào tóm tắt bằng cách gửi một request. Trang gốc khuyên dùng cách này ở bất cứ nơi nào nó khả dụng.
  - **Compaction theo ngưỡng token (at a token threshold):** API tự tóm tắt khi hội thoại đạt ngưỡng bạn đặt.
- Trang gốc có bảng so sánh hai cách (ai quyết định thời điểm, v.v.) và mục "các tùy chọn compaction theo yêu cầu" dẫn tới các trang chuyên sâu: giữ các lượt gần nhất, compaction ở chế độ nền, và giữ thinking block hợp lệ.
- Nếu muốn bỏ qua phần tổng quan, bắt đầu từ trang compaction theo yêu cầu để thêm compaction vào ứng dụng.

## Các mục trong trang gốc

Chọn cách compact · Các tùy chọn compaction theo yêu cầu.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/compaction)
- [Compaction theo yêu cầu](compaction-on-demand.md)
- [Compaction theo ngưỡng token](compaction-threshold.md)
- [Compaction giữ lại các lượt gần nhất](compaction-keep-recent-turns.md)
- [Compaction ở chế độ nền](compaction-background.md)
- [Giữ thinking block hợp lệ](compaction-thinking-blocks.md)
- [Cửa sổ ngữ cảnh](context-windows.md)

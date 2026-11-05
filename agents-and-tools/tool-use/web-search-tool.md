---
title: Web search tool (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/web-search-tool
description: Cho Claude quyền truy cập nội dung web hiện tại kèm nguồn được trích dẫn, dynamic filtering tùy chọn và kiểm soát domain.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/web-search-tool). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Web search tool là một server tool cho Claude truy cập nội dung web hiện tại, kèm nguồn được trích dẫn, dynamic filtering tùy chọn và các kiểm soát theo domain. Công cụ có các phiên bản theo ngày (ví dụ `web_search_20260318`, `web_search_20260209`, `web_search_20250305`).

## Các điểm chính

- **Cách hoạt động:** Claude tìm kiếm khi nào; dynamic filtering.
- **Định nghĩa công cụ:** số lần dùng tối đa (max uses), lọc domain, bản địa hóa (localization) và những gì đưa vào phản hồi.
- **Phản hồi:** kết quả tìm kiếm, trích dẫn, lỗi, và stop reason `pause_turn`.
- **Khác:** prompt caching, streaming, batch request, mức sử dụng và giá.
- Thực thi code miễn phí khi đi cùng web search hoặc web fetch từ các phiên bản `20260209` trở lên (xem trang Code execution tool).

## Các mục trong trang gốc

Cách web search hoạt động (khi nào Claude tìm kiếm, dynamic filtering) · Cách dùng web search · Định nghĩa công cụ · Phản hồi · Prompt caching · Streaming · Batch request · Sử dụng và giá.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/web-search-tool)
- [Web fetch tool](web-fetch-tool.md)
- [Server tools](server-tools.md)
- [Code execution tool](code-execution-tool.md)

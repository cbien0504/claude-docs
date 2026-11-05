---
title: Web fetch tool (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/web-fetch-tool
description: Tải và đọc nội dung từ các URL cụ thể để bổ sung ngữ cảnh của Claude bằng nội dung web trực tiếp.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/web-fetch-tool). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Web fetch tool là một server tool giúp Claude tải và đọc nội dung từ các URL cụ thể, bổ sung ngữ cảnh bằng nội dung web trực tiếp. Công cụ có các phiên bản theo ngày (ví dụ `web_fetch_20260318`, `web_fetch_20260309`, `web_fetch_20260209`, `web_fetch_20250910`).

## Các điểm chính

- **Cách hoạt động:** Claude tải nội dung khi nào; có dynamic filtering (kết hợp với code execution).
- **Định nghĩa công cụ** có các tùy chọn: số lần dùng tối đa (max uses), lọc domain, giới hạn nội dung, bỏ qua cache, những gì đưa vào phản hồi, và trích dẫn.
- **Phản hồi:** kết quả tải và các lỗi.
- **Kiểm tra URL hợp lệ:** có mục về nguồn của URL.
- **Kết hợp tìm kiếm và tải** (web search + web fetch), **prompt caching**, và các mục còn lại của trang gốc.

## Các mục trong trang gốc

Cách web fetch hoạt động (khi nào Claude tải, dynamic filtering) · Cách dùng web fetch · Định nghĩa công cụ (max uses, lọc domain, giới hạn nội dung, bỏ qua cache, đưa vào phản hồi, trích dẫn) · Phản hồi (kết quả tải, lỗi) · Kiểm tra URL (nguồn URL) · Kết hợp tìm kiếm và tải · Prompt caching · và các mục còn lại của trang gốc.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/web-fetch-tool)
- [Web search tool](web-search-tool.md)
- [Server tools](server-tools.md)
- [Tham chiếu công cụ](tool-reference.md)

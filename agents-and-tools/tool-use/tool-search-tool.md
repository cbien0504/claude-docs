---
title: Tool search tool (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-search-tool
description: Mở rộng tới hàng trăm hoặc hàng nghìn công cụ bằng cách để Claude tìm trong danh mục công cụ của bạn và chỉ nạp những công cụ nó cần.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-search-tool). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Tool search tool cho phép mở rộng tới hàng trăm hoặc hàng nghìn công cụ: Claude tìm trong danh mục công cụ của bạn và chỉ nạp những công cụ cần thiết, thay vì nạp sẵn mọi định nghĩa vào ngữ cảnh.

## Các điểm chính

- **Định nghĩa công cụ:** có hai biến thể tìm kiếm (`tool_search_tool_regex_20251119` và `tool_search_tool_bm25_20251119`) và cơ chế nạp trì hoãn công cụ (`defer_loading`).
- **Định dạng phản hồi:** cách hiểu phản hồi và cách tiếp tục hội thoại.
- **Tích hợp MCP** và **tự triển khai tool search** (custom implementation).
- **Xử lý lỗi:** lỗi HTTP (400) và lỗi trong kết quả công cụ (200), cùng các sai lầm thường gặp.
- **Khác:** prompt caching, streaming, batch request, giới hạn và thực hành tốt, tương thích mô hình.

## Các mục trong trang gốc

Tương thích mô hình · Cách tool search hoạt động · Quick start · Định nghĩa công cụ (nạp trì hoãn) · Định dạng phản hồi · Tích hợp MCP · Triển khai tool search tùy chỉnh · Xử lý lỗi · Prompt caching · Streaming · Batch request · Giới hạn và thực hành tốt.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-search-tool)
- [Quản lý ngữ cảnh của công cụ](manage-tool-context.md)
- [Tool use với prompt caching](tool-use-with-prompt-caching.md)
- [MCP connector](../mcp-connector.md)

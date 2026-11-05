---
title: Tham chiếu công cụ (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-reference
description: Danh mục các server tool, client tool và client toolset do Anthropic cung cấp, cùng tham chiếu cho các thuộc tính tùy chọn của định nghĩa công cụ.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-reference). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang tham chiếu cho các công cụ Anthropic cung cấp và các thuộc tính tùy chọn bạn có thể đặt trên bất kỳ định nghĩa công cụ nào. Anthropic cung cấp hai loại công cụ: **server tool** chạy trên hạ tầng của Anthropic, và **client tool** mà Anthropic định nghĩa schema còn ứng dụng của bạn lo phần thực thi. Cả hai đều xuất hiện trong mảng `tools` của request, cạnh các công cụ do bạn định nghĩa.

## Các điểm chính

Bảng trong trang liệt kê từng công cụ cùng giá trị `type` (có phiên bản theo ngày), cách thực thi và beta header. Một số ví dụ:

| Công cụ | `type` | Thực thi | Beta header |
| --- | --- | --- | --- |
| Web search tool | `web_search_20260318`, `web_search_20260209`, `web_search_20250305` | Server | Không |
| Web fetch tool | `web_fetch_20260318`, `web_fetch_20260309`, `web_fetch_20260209`, `web_fetch_20250910` | Server | Không |
| Code execution tool | `code_execution_20260521`, `code_execution_20260120`, `code_execution_20250825` | Server | Không |
| Advisor tool | `advisor_20260301` | Server | `advisor-tool-2026-03-01` |
| Tool search tool | `tool_search_tool_regex_20251119`, `tool_search_tool_bm25_20251119` | Server | Không |
| MCP connector | `mcp_toolset` | Server | (xem trang gốc) |

Bảng đầy đủ còn có các client tool và client toolset (có mục "Client toolset" và "Phiên bản công cụ" riêng). Phần thuộc tính định nghĩa công cụ nói về các giá trị của `allowed_callers` và quan hệ giữa `defer_loading` với prompt caching.

## Các mục trong trang gốc

Công cụ do Anthropic cung cấp (đánh phiên bản công cụ, client toolset) · Thuộc tính định nghĩa công cụ (giá trị `allowed_callers`, `defer_loading` và prompt caching).

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-reference)
- [Tổng quan sử dụng công cụ](overview.md)
- [Tool search tool](tool-search-tool.md)
- [Tool use với prompt caching](tool-use-with-prompt-caching.md)

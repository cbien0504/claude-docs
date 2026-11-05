---
title: Tool use với prompt caching (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-use-with-prompt-caching
description: Cache các định nghĩa công cụ qua các lượt và hiểu điều gì làm mất hiệu lực cache của bạn.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-use-with-prompt-caching). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang nói về prompt caching cho các định nghĩa công cụ: đặt breakpoint `cache_control` ở đâu, `defer_loading` giữ nguyên cache của bạn như thế nào, và điều gì làm mất hiệu lực cache. Về prompt caching nói chung, xem trang Prompt caching.

## Các điểm chính

- **`cache_control` trên định nghĩa công cụ:** đặt `cache_control: {"type": "ephemeral"}` trên công cụ cuối cùng trong mảng `tools`; việc này cache toàn bộ tiền tố định nghĩa công cụ, từ công cụ đầu tiên tới điểm đánh dấu. Với `mcp_toolset`, breakpoint rơi vào công cụ cuối của bộ; bạn không kiểm soát thứ tự công cụ trong một MCP toolset, nên đặt breakpoint trên chính mục `mcp_toolset` và API sẽ áp dụng cho công cụ cuối sau khi mở rộng. Các mục toolset của computer use và browser use cũng theo cùng quy tắc.
- **`defer_loading` và việc giữ cache:** công cụ nạp trì hoãn không nằm trong tiền tố system prompt. Khi mô hình khám phá một công cụ trì hoãn qua tool search, định nghĩa được nối thêm tại chỗ dưới dạng `tool_reference`. Nhờ đó thêm công cụ động qua tool search không phá cache: bạn có thể bắt đầu với tập nhỏ các công cụ luôn nạp (được cache), để mô hình khám phá thêm khi cần và vẫn giữ cùng một lần trúng cache qua mọi lượt. `defer_loading` cũng hoạt động độc lập với việc xây dựng ngữ pháp cho strict mode.
- **Điều gì làm mất hiệu lực cache:** cache theo thứ bậc tiền tố (`tools` → `system` → `messages`), nên một thay đổi ở một cấp làm mất hiệu lực cấp đó và mọi thứ sau nó.
- **Kết quả server tool được cache tự động**, kèm bảng tương tác theo từng công cụ.

## Các mục trong trang gốc

`cache_control` trên định nghĩa công cụ · `defer_loading` và giữ cache · Điều gì làm mất hiệu lực cache · Kết quả server tool được cache tự động · Bảng tương tác theo từng công cụ · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-use-with-prompt-caching)
- [Prompt caching](../../build-with-claude/prompt-caching.md)
- [Tool search tool](tool-search-tool.md)

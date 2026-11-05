---
title: Quản lý ngữ cảnh của công cụ (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/manage-tool-context
description: Chọn giữa tool search, programmatic tool calling, prompt caching và context editing để xử lý tình trạng ngữ cảnh phình to.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/manage-tool-context). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Định nghĩa công cụ và các block `tool_result` tích lũy chiếm cửa sổ ngữ cảnh. Agent chạy lâu với nhiều công cụ hoặc nhiều lượt có thể dùng cạn ngữ cảnh trước khi xong tác vụ. Bốn cách tiếp cận xử lý vấn đề này ở các điểm khác nhau trong pipeline; hãy chọn cách khớp với nơi token của bạn đang bị tiêu tốn.

## Các điểm chính

| Cách tiếp cận | Giảm cái gì | Khi nào phù hợp | Tìm hiểu thêm |
| --- | --- | --- | --- |
| Tool search | Định nghĩa công cụ nạp sẵn từ đầu | Bộ công cụ lớn (20+ công cụ) mà phần lớn không cần ở mỗi lượt | [Tool search tool](tool-search-tool.md) |
| Programmatic tool calling | Số vòng `tool_result` | Chuỗi lệnh gọi công cụ có thể chạy như một script duy nhất | [Programmatic tool calling](programmatic-tool-calling.md) |
| Prompt caching | Chi phí token của các định nghĩa công cụ lặp lại | Bộ công cụ ổn định qua nhiều request | [Tool use với prompt caching](tool-use-with-prompt-caching.md) |
| Context editing | Các block `tool_result` cũ trong lịch sử | Hội thoại dài mà kết quả đầu không còn liên quan | [Context editing](../../build-with-claude/context-editing.md) |

- **Tool search** giữ định nghĩa công cụ ngoài cửa sổ ngữ cảnh cho đến khi Claude yêu cầu: thay vì gửi sẵn 50 schema, bạn chỉ gửi một công cụ `tool_search` và để Claude tự khám phá phần còn lại khi cần, đánh đổi một chút độ trễ (thêm một lượt để tra cứu công cụ).
- **Programmatic tool calling** gộp một chuỗi lệnh gọi công cụ thành một khối code duy nhất do Claude viết và sandbox thực thi code của Anthropic chạy; thay vì năm vòng `tool_use` và `tool_result`, Claude phát ra một script gọi cả năm hàm từ trong sandbox.
- **Prompt caching** không giảm số token trong ngữ cảnh nhưng giảm chi phí trả cho chúng ở các request sau; nếu định nghĩa công cụ ổn định thì cache một lần và dùng lại tiền tố đã cache qua hàng nghìn request.

## Các mục trong trang gốc

Bốn cách tiếp cận (tool search, programmatic tool calling, prompt caching, context editing) · Kết hợp các cách tiếp cận · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/manage-tool-context)
- [Tool search tool](tool-search-tool.md)
- [Programmatic tool calling](programmatic-tool-calling.md)
- [Context editing](../../build-with-claude/context-editing.md)

---
title: Streaming Messages (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/streaming
description: Stream phản hồi của Messages API theo từng phần bằng server-sent events, gồm các delta văn bản, tool use và thinking.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/streaming). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang mô tả cách stream phản hồi của Messages API từng phần bằng server-sent events (SSE), gồm các delta của văn bản, tool use và thinking, cùng cách khôi phục khi gặp lỗi.

## Các điểm chính

- **Dùng SDK:** có ví dụ streaming bằng SDK, và cách lấy message cuối cùng mà không phải tự xử lý từng sự kiện.
- **Các loại sự kiện:** gồm ping, lỗi và các sự kiện khác (ví dụ `message_start`).
- **Các loại delta của content block:** delta văn bản, delta JSON đầu vào (input JSON delta) và delta thinking.
- **Phản hồi stream HTTP đầy đủ:** ví dụ cho request streaming cơ bản, có tool use, có thinking và có web search tool use.
- **Khôi phục lỗi:** có hướng dẫn riêng cho Claude 4.5 trở xuống và Claude 4.6 trở lên, cùng các thực hành tốt.

## Các mục trong trang gốc

Streaming với SDK · Lấy message cuối mà không xử lý sự kiện · Các loại sự kiện · Các loại delta của content block · Phản hồi stream HTTP đầy đủ · Khôi phục lỗi · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/streaming)
- [Fine-grained tool streaming](../agents-and-tools/tool-use/fine-grained-tool-streaming.md)
- [Stop reason và dự phòng](handling-stop-reasons.md)

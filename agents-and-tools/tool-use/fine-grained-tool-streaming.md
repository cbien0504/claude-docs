---
title: Fine-grained tool streaming (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/fine-grained-tool-streaming
description: Stream đầu vào của công cụ mà không cần máy chủ đệm JSON, dành cho ứng dụng nhạy với độ trễ.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/fine-grained-tool-streaming). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Fine-grained tool streaming chuyển đầu vào của công cụ tới client ngay khi Claude sinh ra, không đệm phía máy chủ và không kiểm tra hợp lệ JSON. Bỏ bước đệm giúp giảm thời gian tới mảnh đầu tiên của một tham số lớn (như tài liệu hay khối code).

> **Lưu ý:** vì API không đệm hay kiểm tra đầu vào của công cụ trước khi stream, bạn có thể nhận JSON không đầy đủ hoặc không hợp lệ. Một phản hồi kết thúc với stop reason `max_tokens` cũng có thể cắt ngang một tham số. Ứng dụng cần xử lý các trường hợp này.

## Các điểm chính

- **Phạm vi hỗ trợ:** mọi mô hình đều hỗ trợ fine-grained tool streaming trên Claude API, Amazon Bedrock, Claude Platform on AWS, Claude Models on Google Cloud…
- **Cách bật:** trường `eager_input_streaming` là tùy chọn; đặt `true` để bật fine-grained streaming cho công cụ đó, bỏ qua thì dùng streaming tiêu chuẩn, trong đó API đệm và kiểm tra từng giá trị tham số trước khi stream lại.
- **Ví dụ trong trang:** bật cho công cụ `make_file` và yêu cầu Claude viết một bài thơ dài để quan sát đầu vào lớn được stream.
- **Cộng dồn các delta của đầu vào công cụ** và **xử lý JSON không hợp lệ** có mục riêng trong trang gốc.

## Các mục trong trang gốc

Cách dùng fine-grained tool streaming · Cộng dồn các delta đầu vào công cụ · Xử lý JSON không hợp lệ trong phản hồi công cụ · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/fine-grained-tool-streaming)
- [Streaming Messages](../../build-with-claude/streaming.md)
- [Stop reason và dự phòng](../../build-with-claude/handling-stop-reasons.md)

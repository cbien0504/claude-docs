---
title: Sử dụng công cụ với Claude (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview
description: Kết nối Claude với công cụ và API bên ngoài; xem công cụ chạy ở đâu, khi nào Claude gọi chúng và công cụ nào phù hợp với tác vụ của bạn.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Sử dụng công cụ (tool use, còn gọi là function calling) cho phép Claude gọi các hàm do bạn định nghĩa hoặc do Anthropic cung cấp. Claude quyết định khi nào gọi công cụ dựa trên yêu cầu của người dùng và mô tả của công cụ, rồi trả về một lệnh gọi có cấu trúc để ứng dụng của bạn chạy (client tool) hoặc để Anthropic chạy (server tool).

## Các điểm chính

- **Khác biệt chính là nơi code chạy:**
  - **Client tool** (gồm công cụ do bạn định nghĩa và công cụ có schema do Anthropic định nghĩa như `bash`, `text_editor`) chạy trong ứng dụng của bạn. Claude trả về `stop_reason: "tool_use"` kèm một hoặc nhiều block `tool_use`; code của bạn thực hiện thao tác rồi gửi lại `tool_result`.
  - **Server tool** (như `web_search`, `web_fetch`, `code_execution`, `tool_search`) chạy trên hạ tầng của Anthropic; bạn nhận kết quả trực tiếp mà không phải xử lý việc thực thi, trừ khi Claude gọi nó cùng nhóm lệnh gọi song song với một client tool của bạn.
- **Ví dụ tối thiểu:** dùng server tool Web search; Claude chạy tìm kiếm trên hạ tầng Anthropic và trả kết quả có trích dẫn trong cùng một phản hồi.
- **Công cụ do bạn định nghĩa:** truyền một công cụ có `input_schema`, rồi chạy lệnh gọi khi Claude trả về block `tool_use`. Ví dụ đầy đủ (công cụ `get_weather`) gồm hai request: request đầu định nghĩa công cụ và nhận block `tool_use`; request thứ hai gửi `tool_result` để Claude trả lời. Quy trình này cần nhiều logic hơn một lệnh shell nên dùng SDK.
- **Trang gốc phân loại công cụ để chọn:** công cụ của riêng bạn, client tool với schema do Anthropic định nghĩa, và server tool; có thêm phần về giá và các bước tiếp theo.

## Các mục trong trang gốc

Cách sử dụng công cụ hoạt động · Khi nào Claude dùng công cụ · Chọn công cụ (công cụ của bạn, client tool theo schema Anthropic, server tool) · Giá · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview)
- [Định nghĩa công cụ](define-tools.md)
- [Xử lý lệnh gọi công cụ](handle-tool-calls.md)
- [Cách tool use hoạt động](how-tool-use-works.md)
- [Parallel tool use](parallel-tool-use.md)

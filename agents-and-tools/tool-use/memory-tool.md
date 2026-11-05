---
title: Memory tool (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/memory-tool
description: Cho Claude lưu và truy xuất thông tin xuyên suốt các cuộc hội thoại bằng cách triển khai các thao tác file của memory tool trong ứng dụng của bạn.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/memory-tool). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Memory tool cho phép Claude lưu và truy xuất thông tin xuyên suốt các cuộc hội thoại trong một thư mục các file bộ nhớ. Claude có thể tạo, đọc, cập nhật và xóa các file tồn tại giữa các session, dần dần tích lũy kiến thức mà không phải giữ mọi thứ trong cửa sổ ngữ cảnh. Memory hỗ trợ truy xuất ngữ cảnh đúng lúc (just-in-time): thay vì nạp trước mọi thông tin liên quan, agent ghi lại những gì nó học được vào file bộ nhớ rồi đọc lại khi cần, giữ ngữ cảnh đang hoạt động tập trung vào tác vụ hiện tại.

Memory tool chạy phía client: Claude chỉ yêu cầu các thao tác file, ứng dụng của bạn thực thi chúng, và bạn kiểm soát nơi và cách dữ liệu được lưu trên hạ tầng của mình. Công cụ khả dụng trên mọi mô hình Claude 4 trở lên.

## Các điểm chính

- **Trường hợp sử dụng:** duy trì ngữ cảnh dự án qua nhiều session agent; áp dụng bài học từ các tương tác, quyết định và phản hồi trước đó cho tác vụ mới; xây dựng cơ sở kiến thức theo thời gian.
- **Cách hoạt động:** khi bật, Claude tự động kiểm tra thư mục bộ nhớ trước khi bắt đầu tác vụ, lưu những gì học được vào các file dưới `/memories` và đọc lại trong các cuộc hội thoại sau. Đường dẫn `/memories` là tiền tố mà trình xử lý của bạn ánh xạ vào kho lưu trữ thật (ví dụ thư mục theo từng người dùng hoặc khóa trong cơ sở dữ liệu); mỗi yêu cầu được chạy trên kho do bạn kiểm soát và kết quả trả về trong block `tool_result`.
- **Bắt đầu:** thêm vào request mục `tools` `{"type": "memory_20250818", "name": "memory"}`; đó là toàn bộ cấu hình (`name` phải là `memory` và không cần định nghĩa input schema cho công cụ do Anthropic cung cấp).
- **Các lệnh của công cụ:** `view`, `create`, `str_replace`, `insert`, `delete` (mỗi lệnh có mục giá trị trả về và xử lý lỗi; các lệnh liên quan thư mục có phần xử lý riêng).

## Các mục trong trang gốc

Trường hợp sử dụng · Cách hoạt động (ví dụ về các lệnh gọi memory tool) · Bắt đầu · Cách dùng cơ bản · Triển khai trình xử lý bộ nhớ · Các lệnh của công cụ (`view`, `create`, `str_replace`, `insert`, `delete`) · và các mục còn lại của trang gốc.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/memory-tool)
- [Xử lý lệnh gọi công cụ](handle-tool-calls.md)
- [Tham chiếu công cụ](tool-reference.md)
- [Context editing](../../build-with-claude/context-editing.md)

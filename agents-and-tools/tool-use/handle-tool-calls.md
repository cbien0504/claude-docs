---
title: Xử lý lệnh gọi công cụ (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/handle-tool-calls
description: Phân tích block tool_use, định dạng phản hồi tool_result và xử lý lỗi bằng is_error.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/handle-tool-calls). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang này nói về vòng đời của một lệnh gọi công cụ: đọc các block `tool_use` trong phản hồi của Claude, định dạng các block `tool_result` trong câu trả lời của bạn và báo hiệu lỗi. Tool Runner (SDK) tự động xử lý toàn bộ việc này; chỉ dùng trang này khi cần kiểm soát tùy chỉnh việc thực thi công cụ. Phản hồi của Claude khác nhau tùy công cụ là client hay server.

## Các điểm chính

- **Với client tool:** phản hồi có `stop_reason` là `tool_use` và một hoặc nhiều block nội dung `tool_use` gồm: `id` (định danh duy nhất để khớp kết quả sau này), `name` (tên công cụ) và `input` (đối tượng đầu vào theo `input_schema`). Block `tool_use` của một thành viên toolset computer use hoặc browser use còn có trường `toolset_name`.
- **Việc cần làm khi nhận phản hồi tool use của client tool:**
  1. Lấy `name`, `id` và `input` từ block `tool_use`.
  2. Chạy công cụ tương ứng trong code của bạn với `input` đó.
  3. Tiếp tục hội thoại bằng một message `user` có block nội dung kiểu `tool_result` gồm: `tool_use_id` (`id` của yêu cầu mà kết quả này trả lời), `content` (tùy chọn; chuỗi, danh sách content block lồng nhau hoặc danh sách block tài liệu) và `is_error` (tùy chọn; đặt `true` nếu việc thực thi công cụ gây lỗi).
- Một `tool_result` trả lời block thành viên của computer use hoặc browser use phải lặp lại cùng giá trị `toolset_name` với block `tool_use`.

## Các mục trong trang gốc

Xử lý kết quả từ client tool · Xử lý kết quả từ server tool · Xử lý lỗi bằng `is_error` · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/handle-tool-calls)
- [Tool runner (SDK)](tool-runner.md)
- [Cách tool use hoạt động](how-tool-use-works.md)
- [Parallel tool use](parallel-tool-use.md)

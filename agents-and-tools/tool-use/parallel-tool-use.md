---
title: Parallel tool use (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/parallel-tool-use
description: Bật, định dạng và tắt các lệnh gọi công cụ song song, kèm hướng dẫn về lịch sử message và xử lý sự cố.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/parallel-tool-use). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Theo mặc định, Claude có thể gọi nhiều công cụ trong một phản hồi. Trang này nói về cách chạy các lệnh gọi đó, cách định dạng lịch sử message để việc song song tiếp tục hoạt động và cách tắt parallel tool use khi cần.

## Các điểm chính

- **Ngữ nghĩa thực thi:** khi Claude gọi công cụ, phản hồi có `stop_reason` là `tool_use` và có thể chứa nhiều block `tool_use` trong một lượt assistant. Cách chạy các lệnh gọi do bạn quyết định, API không quy định thứ tự: có thể chạy đồng thời hoặc tuần tự. Thao tác độc lập, chỉ đọc thường chạy song song được để giảm độ trễ; công cụ có tác dụng phụ, trạng thái chia sẻ hoặc yêu cầu thứ tự có thể nên chạy tuần tự.
- **Định dạng kết quả:** dù chọn cách nào, trả về một `tool_result` cho mỗi block `tool_use`, tất cả cùng nhau trong message người dùng kế tiếp; khớp mỗi kết quả với lệnh gọi bằng `tool_use_id`, và đặt mọi block `tool_result` trước bất kỳ nội dung văn bản nào trong message đó.
- **Computer use và browser use** có quy định chặt chẽ hơn khi Claude trả về nhiều thao tác.
- **Tool Runner (SDK)** xử lý các phản hồi có nhiều lệnh gọi công cụ và định dạng kết quả giúp bạn; dùng trang này khi cần xử lý thủ công.
- **Tắt parallel tool use:** hai chế độ là tối đa một lệnh gọi công cụ, hoặc đúng một lệnh gọi công cụ.

## Các mục trong trang gốc

Ngữ nghĩa thực thi · Kiểm thử lệnh gọi công cụ song song · Tối đa hóa parallel tool use · Tắt parallel tool use (tối đa một lệnh gọi, đúng một lệnh gọi) · Xử lý sự cố · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/parallel-tool-use)
- [Xử lý lệnh gọi công cụ](handle-tool-calls.md)
- [Tool runner (SDK)](tool-runner.md)

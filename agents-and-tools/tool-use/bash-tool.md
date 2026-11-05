---
title: Bash tool (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/bash-tool
description: Cho phép Claude yêu cầu các lệnh shell mà ứng dụng của bạn chạy trong một bash session liên tục và trả về dưới dạng kết quả công cụ.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/bash-tool). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Bash tool là một client tool: Claude không tự chạy lệnh. Khi bạn đưa công cụ vào request, Claude trả về block `tool_use` nêu lệnh cần chạy; ứng dụng của bạn chạy lệnh đó trong một bash session do bạn sở hữu rồi trả đầu ra trong block `tool_result`. Ứng dụng giữ một tiến trình bash sống qua các lần gọi, nên trạng thái (thư mục làm việc, biến môi trường, file đã tạo) được giữ lại giữa các lệnh. Phiên bản hiện tại của công cụ là `bash_20250124`.

## Các điểm chính

- **Trường hợp sử dụng:** quy trình phát triển (build, test), tự động hóa hệ thống (chạy script, quản lý file), xử lý dữ liệu, và thiết lập môi trường (cài gói, cấu hình).
- **Một vòng gọi công cụ gồm 4 bước:** Claude trả `tool_use` chứa `command`; ứng dụng chạy lệnh trong bash session; ứng dụng trả đầu ra (stdout và stderr gộp) trong `tool_result`; Claude yêu cầu lệnh khác trong cùng session hoặc trả lời bằng văn bản.
- **Nhiều `tool_use` trong một phản hồi:** chạy lần lượt trong cùng session và trả tất cả kết quả trong một message `user`.
- **API không lưu trạng thái (stateless):** trạng thái shell không đi cùng request, nên ứng dụng quyết định khi nào bắt đầu, duy trì bao lâu và khi nào khởi động lại session.
- **Tham số:** định nghĩa công cụ có hai trường bắt buộc là `type` và `name` (`name` phải là `bash`). Công cụ không cần `input_schema` vì schema đã được tích hợp trong mô hình.

## Các mục trong trang gốc

Trường hợp sử dụng · Quick start · Cách hoạt động · Tham số · Phiên bản công cụ · Ví dụ: tự động hóa nhiều bước · Triển khai bash tool (xử lý lỗi, thực hành tốt khi triển khai) · Bảo mật · Giá · Các mẫu thường gặp (quy trình phát triển, thao tác file, tác vụ hệ thống) · Hạn chế · Kết hợp với công cụ khác · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/bash-tool)
- [Cách tool use hoạt động](how-tool-use-works.md)
- [Xử lý lệnh gọi công cụ](handle-tool-calls.md)
- [Parallel tool use](parallel-tool-use.md)
- [Tham chiếu công cụ](tool-reference.md)

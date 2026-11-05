---
title: Browser use tool (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/browser-use-tool
description: Cho phép Claude điều hướng, đọc và tương tác với trang web trong môi trường trình duyệt của bạn bằng browser use tool.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/browser-use-tool). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Browser use tool cho phép Claude điều hướng, đọc và tương tác với trang web trong một trình duyệt do ứng dụng của bạn chạy. Claude làm việc với trang vừa qua cấu trúc (cây trợ năng, phần tử, biểu mẫu, tab) vừa qua ảnh chụp màn hình và tọa độ viewport. Công cụ này là một **client toolset** do Anthropic định nghĩa: chỉ cần một mục `browser_toolset_20260801` trong `tools` là Claude có sẵn 27 công cụ thành viên (ví dụ `navigate`, `read_page`, `left_click`, `screenshot`), cộng thêm bốn thành viên tùy chọn khi bạn bật.

## Các điểm chính

- **Khi nào chọn browser use:** khi tác vụ nằm trọn trong các trang web và cần thao tác trên chúng, hoặc khi trang dựng nội dung bằng JavaScript. Nếu tác vụ cần cả desktop, dùng computer use tool (chỉ làm việc qua ảnh chụp và tọa độ).
- **Bắt đầu nhanh:** thêm một mục có type `browser_toolset_20260801`, không có `name`, vào mảng `tools` của request Messages API. Nên bắt đầu từ toolset trong SDK (Python và TypeScript, đang beta) hoặc từ tích hợp của đối tác.
- **Bảo mật:** Claude đọc và hành động trên trang web thật, nên mọi thứ trang cung cấp đều là đầu vào không đáng tin và các hành động của Claude có thể gây tác động thật. Cần đọc phần cân nhắc bảo mật trước khi triển khai.
- **Các nhóm công cụ thành viên:** điều hướng và chụp, con trỏ, bàn phím và thời gian, đọc trang, biểu mẫu và file, chẩn đoán và scripting, quản lý tab.

## Các mục trong trang gốc

Quick start · Cách browser use hoạt động (thao tác theo lô, đích tác động và tọa độ) · Cân nhắc bảo mật · Các công cụ thành viên · Cấu hình toolset (bật/tắt công cụ thành viên, kết hợp với công cụ khác) · Bật các thành viên tùy chọn (tải file lên, chạy JavaScript trong trang, đọc console và hoạt động mạng) · Theo dõi tab bằng `browser_state` (kết quả quản lý tab, ngữ cảnh tab trên kết quả khác, báo cáo tải xuống) · Xử lý lỗi (trả lỗi từ executor, lỗi request) · Hạn chế · Giá và lưu giữ dữ liệu · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/browser-use-tool)
- [Browser và computer use với bộ công cụ SDK](browser-use-sdk.md)
- [Computer use tool](computer-use-tool.md)
- [Tham chiếu công cụ](tool-reference.md)

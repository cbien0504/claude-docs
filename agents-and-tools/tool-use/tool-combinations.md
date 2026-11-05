---
title: Kết hợp công cụ (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-combinations
description: Các cặp công cụ Anthropic thường dùng cho agent nghiên cứu, agent lập trình và agent chạy dài.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-combinations). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Các công cụ do Anthropic cung cấp được thiết kế để hoạt động cùng nhau. Các mẫu agent phổ biến ghép những công cụ bổ trợ cho các giai đoạn khác nhau của workflow: một công cụ thu thập hoặc khám phá, một công cụ khác xử lý hoặc hành động. Các tổ hợp dưới đây là điểm khởi đầu chứ không phải quy định bắt buộc. Mỗi đoạn mã trong trang chỉ hiển thị mảng `tools`.

## Các điểm chính

- **Agent nghiên cứu – `web_search` + `code_execution`:** tìm kiếm tìm ra nguồn, thực thi code phân tích và tổng hợp. Claude tìm dữ liệu rồi viết Python để xử lý, lập bảng hoặc trực quan hóa; hợp với câu hỏi cần cả thông tin cập nhật lẫn tính toán không tầm thường. Luồng thường là tìm kiếm, rồi chạy code, rồi có thể tìm kiếm lại nếu lần đầu lộ ra chỗ thiếu. Code execution chạy phía máy chủ nên không có sandbox phía client để quản lý.
- **Agent lập trình – `text_editor` + `bash`:** text editor đọc và sửa file; bash chạy kiểm thử và lệnh build. Đây là vòng lặp phát triển phần mềm kinh điển: xem code, sửa, chạy test, lặp lại. Cả hai là client tool nên ứng dụng của bạn kiểm soát file và lệnh nào chạy được; nên kết hợp với thư mục làm việc bị ràng buộc và danh sách lệnh được phép (allowlist) nếu agent làm việc trên code không đáng tin.
- **Trích dẫn rồi tải – `web_search` + `web_fetch`:** tìm kiếm cho ra các URL ứng viên; fetch lấy toàn bộ nội dung trang của những URL liên quan, tránh tải mọi thứ ngay từ đầu.
- **Agent chạy dài – `memory` + công cụ khác.**
- **Tất cả trong một – `computer_use`.**
- **Agent trình duyệt – `browser_use`.**

## Các mục trong trang gốc

Agent nghiên cứu · Agent lập trình · Trích dẫn rồi tải · Agent chạy dài · Tất cả trong một: computer_use · Agent trình duyệt: browser_use · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-combinations)
- [Text editor tool](text-editor-tool.md)
- [Bash tool](bash-tool.md)
- [Memory tool](memory-tool.md)
- [Tham chiếu công cụ](tool-reference.md)

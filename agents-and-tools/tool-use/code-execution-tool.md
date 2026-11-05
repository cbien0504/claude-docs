---
title: Code execution tool (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/code-execution-tool
description: Chạy code Python và Bash trong container sandbox để phân tích dữ liệu, tạo file và lặp lại cách giải.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/code-execution-tool). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Với code execution tool, Claude có thể phân tích dữ liệu, tạo biểu đồ, tính toán phức tạp, chạy lệnh hệ thống, tạo và chỉnh sửa file, cũng như xử lý file được tải lên ngay trong cuộc hội thoại API. Công cụ cho phép Claude chạy lệnh Bash và thao tác file (kể cả viết code) trong một môi trường sandbox an toàn.

## Các điểm chính

- **Chi phí:** thực thi code miễn phí khi dùng cùng web search hoặc web fetch (`web_search_20260209`, `web_fetch_20260209` hoặc mới hơn). Khi một trong các công cụ đó có trong request, không phát sinh phí thực thi code bổ sung ngoài chi phí token tiêu chuẩn, gồm cả phần thực thi code đằng sau dynamic filtering.
- **Làm việc với file:** tải lên và phân tích file của bạn, lấy file do Claude tạo ra (có mục giải thích cách các file được ghi nhận), và Content Credentials trên file được tạo.
- **Định dạng phản hồi:** phản hồi lệnh Bash, phản hồi thao tác file, kết quả, lỗi, và stop reason `pause_turn`.
- **Container:** môi trường chạy, giới hạn tài nguyên, mạng và bảo mật, thư viện cài sẵn; có thể tái sử dụng container giữa các request.
- **Khác:** kết hợp với các công cụ thực thi khác, streaming, batch request, sử dụng và giá; hướng dẫn nâng cấp lên phiên bản công cụ mới nhất (thay đổi, tương thích ngược, các bước nâng cấp).

## Các mục trong trang gốc

Phiên bản công cụ · Quick start · Cách thực thi code hoạt động · Làm việc với file · Định nghĩa công cụ · Định dạng phản hồi · Container · Tái sử dụng container · Dùng với công cụ thực thi khác · Streaming · Batch request · Sử dụng và giá · Nâng cấp lên phiên bản mới nhất · Lưu giữ dữ liệu · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/code-execution-tool)
- [Web search tool](web-search-tool.md)
- [Web fetch tool](web-fetch-tool.md)
- [Batch processing](../../build-with-claude/batch-processing.md)

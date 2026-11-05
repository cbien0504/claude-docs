---
title: Files API (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/files
description: Tải file lên một lần, tham chiếu bằng file_id trong request Messages, và tải về các đầu ra do skill hoặc code execution tool tạo ra.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/files). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Files API cho phép tải file lên một lần rồi dùng lại bằng `file_id` trong các request Messages, thay vì gửi lại nội dung file mỗi lần. API cũng dùng để tải về các file do skill hoặc code execution tool tạo ra.

## Các điểm chính

- **Cách sử dụng:** tải file lên; dùng file trong message thông qua các block phù hợp (block tài liệu, block hình ảnh, block container upload); làm việc với các định dạng file khác.
- **Quản lý file:** liệt kê file, lấy metadata, xóa file và tải file về.
- **Lưu trữ và giới hạn:** giới hạn lưu trữ, vòng đời file, hạn dùng file, ghi log kiểm toán (audit).
- **Di chuyển:** có hướng dẫn chuyển từ `files-api-2025-04-14` (gồm namespace beta của SDK).
- **Khác:** xử lý lỗi, sử dụng và thanh toán, giới hạn tốc độ.

## Các mục trong trang gốc

Các loại file được hỗ trợ · Cách Files API hoạt động · Cách dùng Files API (tải lên, dùng trong message, các loại file và content block, định dạng file khác, quản lý file, tải xuống) · Lưu trữ và giới hạn file · Di chuyển từ `files-api-2025-04-14` · Xử lý lỗi · Sử dụng và thanh toán · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/files)
- [Hỗ trợ PDF](pdf-support.md)
- [Vision](vision.md)
- [Code execution tool](../agents-and-tools/tool-use/code-execution-tool.md)
- [Đính kèm và tải file trong Managed Agents](../managed-agents/files.md)

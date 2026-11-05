---
title: Search results (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/search-results
description: Có trích dẫn tự nhiên cho ứng dụng RAG bằng cách cung cấp kết quả tìm kiếm kèm ghi nguồn.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/search-results). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Tính năng search results cho phép đưa kết quả tìm kiếm kèm thông tin nguồn vào Claude để nhận được trích dẫn tự nhiên cho ứng dụng RAG. Có hai cách cung cấp kết quả tìm kiếm.

## Các điểm chính

- **Phương pháp 1 – Kết quả tìm kiếm từ lệnh gọi công cụ:** công cụ của bạn (ví dụ công cụ cơ sở tri thức) trả về kết quả tìm kiếm.
- **Phương pháp 2 – Kết quả tìm kiếm là nội dung cấp cao nhất:** đưa kết quả tìm kiếm trực tiếp vào nội dung message.
- **Schema kết quả tìm kiếm** gồm các trường bắt buộc và tùy chọn; phản hồi của Claude có trích dẫn với các trường trích dẫn riêng, và có thể có nhiều content block.
- **Cách dùng nâng cao:** kết hợp cả hai phương pháp, trộn với các loại nội dung khác, điều khiển cache và điều khiển trích dẫn.
- Trang cũng có phần thực hành tốt cho từng phương pháp, các thực hành chung và các hạn chế.

## Các mục trong trang gốc

Cách hoạt động (schema, trường bắt buộc, trường tùy chọn) · Phương pháp 1 · Phương pháp 2 · Phản hồi của Claude kèm trích dẫn · Nhiều content block · Cách dùng nâng cao · Thực hành tốt · Hạn chế · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/search-results)
- [Citations](citations.md)
- [Prompt caching](prompt-caching.md)

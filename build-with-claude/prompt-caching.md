---
title: Prompt caching (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/prompt-caching
description: Cache các tiền tố prompt bằng cache_control để giảm chi phí và độ trễ, dùng caching tự động hoặc các breakpoint tường minh với TTL 5 phút hoặc 1 giờ.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/prompt-caching). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Prompt caching cho phép cache các tiền tố của prompt bằng `cache_control` để giảm chi phí và độ trễ. Có hai cách: **caching tự động** hoặc **breakpoint tường minh**, đều dùng được với thời gian sống (TTL) 5 phút hoặc 1 giờ. Cache chỉ trúng khi phần đầu prompt giống hệt từng byte so với request gần đây.

## Các điểm chính

- **Caching tự động:** có phần giải thích cách hoạt động trong hội thoại nhiều lượt, hỗ trợ TTL, kết hợp với caching ở mức block, những thứ giữ nguyên và các trường hợp biên.
- **Breakpoint tường minh:** cách cấu trúc prompt, cách API tự động kiểm tra tiền tố, khi nào dùng nhiều breakpoint, và chi phí của breakpoint.
- **Chiến lược và cân nhắc:** giới hạn của cache, điều gì có và không thể cache, điều gì làm mất hiệu lực cache, theo dõi hiệu quả cache, caching với thinking block, lưu trữ và chia sẻ cache.
- Trang gốc còn có các mục về giá, mô hình được hỗ trợ và nhiều ví dụ.
- Muốn tìm nguyên nhân khi cache bị trượt, xem Cache diagnostics.

## Các mục trong trang gốc

Cách prompt caching hoạt động · Giá · Mô hình được hỗ trợ · Caching tự động · Breakpoint tường minh · Chiến lược và cân nhắc khi cache · và các mục còn lại của trang gốc.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/prompt-caching)
- [Cache diagnostics](cache-diagnostics.md)
- [Tool use với prompt caching](../agents-and-tools/tool-use/tool-use-with-prompt-caching.md)
- [Batch processing](batch-processing.md)

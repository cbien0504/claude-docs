---
title: Text watermark (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/text-watermark
description: Text watermark của Anthropic giữ nguyên những gì, tìm danh sách mô hình và nền tảng được áp dụng ở đâu, và nên bỏ tham số lấy mẫu nào nếu bạn dựa vào nó.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/text-watermark). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Văn bản do các mô hình Claude được hỗ trợ sinh ra mang text watermark của Anthropic. Watermark không thay đổi ý nghĩa, chất lượng hay độ dễ đọc của đầu ra; nó không thêm token hay ký tự ẩn và không chứa thông tin về bạn hay tổ chức của bạn. Bạn không cần thay đổi request hay cách xử lý phản hồi vì nó. Danh sách mô hình và nền tảng được áp dụng nằm ở bài viết trong trung tâm hỗ trợ về cách Claude đánh dấu nội dung do AI tạo ra.

## Các điểm chính

- **Cài đặt lấy mẫu (sampling):** trên Claude Sonnet 4.6, văn bản sinh ra cho request đặt `temperature`, `top_p` hoặc `top_k` khác giá trị mặc định có thể không mang watermark. Nếu bạn dựa vào watermark, hãy bỏ cả ba tham số khỏi request, kể cả những tham số mà framework hoặc thư viện client có thể tự thêm.

## Các mục trong trang gốc

Cài đặt lấy mẫu.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/text-watermark)

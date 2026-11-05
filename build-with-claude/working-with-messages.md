---
title: Sử dụng Messages API (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/working-with-messages
description: Các mẫu và ví dụ thực tế để dùng Messages API hiệu quả.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/working-with-messages). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Hướng dẫn này nói về các mẫu thường gặp khi làm việc với Messages API: request cơ bản, hội thoại nhiều lượt, kỹ thuật prefill và khả năng vision. Với đặc tả API đầy đủ, xem tài liệu tham chiếu Messages API. Trang cũng nhắc lại hai cách xây dựng với Claude: Messages API (truy cập mô hình trực tiếp, phù hợp khi cần vòng lặp agent tùy chỉnh và kiểm soát chi tiết) và Claude Managed Agents (harness agent dựng sẵn, phù hợp tác vụ chạy dài và công việc bất đồng bộ).

## Các điểm chính

- **Request và phản hồi cơ bản:** các tham số lấy mẫu `temperature`, `top_p` và `top_k` không được hỗ trợ trên Claude 4.7 trở lên và Claude Mythos Preview, hay trên bất kỳ mô hình nào kể từ API version `2026-10-21`.
- **Nhiều lượt hội thoại**, trong đó có vai trò `system` trong messages.
- **Prefill phản hồi của Claude** và **vision** có mục riêng.

## Các mục trong trang gốc

Request và phản hồi cơ bản · Nhiều lượt hội thoại (vai trò system trong messages) · Prefill phản hồi của Claude · Vision · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/working-with-messages)
- [Tổng quan Claude Managed Agents](../managed-agents/overview.md)
- [Vision](vision.md)
- [Streaming Messages](streaming.md)

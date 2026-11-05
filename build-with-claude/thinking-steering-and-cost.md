---
title: Điều hướng thinking – steering và chi phí (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/thinking-steering-and-cost
description: Điều hướng tần suất và độ sâu suy nghĩ của Claude bằng mức effort, chỉ dẫn trong system prompt và điều hướng theo từng message, đồng thời hiểu chi phí và giá của thinking.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/thinking-steering-and-cost). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Thinking của Claude có tính thích ứng (adaptive): mô hình đánh giá từng request và quyết định có suy nghĩ hay không và suy nghĩ bao nhiêu. Bạn đặt ý định, tùy chọn chỉ định effort, và mô hình phân bổ suy luận ở nơi suy luận có khả năng giúp ích. Vì vậy thinking rất hợp với workload trộn lẫn request đơn giản và phức tạp, và với workflow agent dài hạn nơi lượng suy luận cần thiết thay đổi từng bước. Trang này nói về cách Claude quyết định khi nào suy nghĩ, cách điều hướng, và các vấn đề về caching, chi phí, giá. Về cách bật thinking và đọc đầu ra, xem trang tổng quan Thinking.

## Các điểm chính

- **Claude quyết định khi nào suy nghĩ:** thinking là tùy chọn với mô hình. Ở mỗi request, Claude đánh giá độ phức tạp của đầu vào và quyết định liệu suy luận sâu hơn có cải thiện câu trả lời hay không; một câu hỏi thực tế đơn giản có thể được trả lời thẳng không có thinking block. Quyết định này diễn ra cho từng request, nên cùng một hội thoại có thể có lượt có và lượt không có thinking; đừng xây logic ứng dụng giả định mọi lượt assistant đều bắt đầu bằng một thinking block.
- **Điều hướng tần suất suy nghĩ:** bằng mức effort, chỉ dẫn trong system prompt và điều hướng theo từng message; nên kiểm chứng việc điều hướng trên workload của bạn.
- **Cơ chế:** kiểm tra hợp lệ của lượt, prompt caching, kiểm soát chi phí; và mục về giá.
- Về tính áp dụng của zero data retention (ZDR) với tính năng này, xem trang API và lưu giữ dữ liệu.

## Các mục trong trang gốc

Claude quyết định khi nào suy nghĩ · Điều hướng tần suất suy nghĩ (mức effort, chỉ dẫn system prompt, điều hướng theo message, kiểm chứng trên workload) · Cơ chế (kiểm tra lượt, prompt caching, kiểm soát chi phí) · Giá · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/thinking-steering-and-cost)
- [Tổng quan thinking](thinking.md)
- [Effort](effort.md)
- [Extended thinking (bản cũ)](extended-thinking.md)

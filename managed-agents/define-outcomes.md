---
title: Định nghĩa outcome (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/define-outcomes
description: Cho agent biết thế nào là "xong", và để nó lặp lại cho đến khi đạt.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/define-outcomes). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Một outcome cho session biết kết quả cuối cùng nên trông như thế nào và cách đo chất lượng của nó. Agent làm việc hướng tới mục tiêu đó, tự đánh giá và lặp lại cho đến khi outcome được đạt. Khi bạn định nghĩa outcome, harness tự động cấp một **grader** để đánh giá sản phẩm theo một rubric. Grader dùng một cửa sổ ngữ cảnh riêng để không bị ảnh hưởng bởi các lựa chọn triển khai của agent chính, rồi trả về lời giải thích tóm tắt tiêu chí nào đạt hay không đạt (hoặc xác nhận sản phẩm thỏa rubric). Phản hồi đó được đưa lại cho agent ở lần lặp tiếp theo.

## Các điểm chính

- **Tạo rubric** và **tạo session có outcome.**
- **Sự kiện outcome:** sự kiện người dùng định nghĩa outcome; bắt đầu đánh giá outcome; đang đánh giá; kết thúc đánh giá.
- **Kiểm tra trạng thái outcome** và **lấy sản phẩm bàn giao (deliverables).**

## Các mục trong trang gốc

Tạo rubric · Tạo session có outcome · Sự kiện outcome (định nghĩa outcome, bắt đầu đánh giá, đang đánh giá, kết thúc đánh giá) · Kiểm tra trạng thái outcome · Lấy sản phẩm bàn giao · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/define-outcomes)
- [Bắt đầu một session](sessions.md)
- [Session event stream](events-and-streaming.md)

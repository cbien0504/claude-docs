---
title: Giữ thinking block hợp lệ – Compaction và preserved thinking (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/compaction-thinking-blocks
description: Khi nào các thinking block ở những lượt được giữ lại sau compaction theo yêu cầu vẫn hợp lệ trên mô hình có preserved thinking, và cách kiểm tra.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/compaction-thinking-blocks). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang này chỉ cần đọc nếu bạn gửi thinking block ngược lại cho một mô hình có preserved thinking **và** giữ lại các lượt sau block compaction. "Lượt được giữ" là những lượt đi sau block, ví dụ các lượt gần nhất bạn không đưa vào request compaction. Mô hình có preserved thinking kiểm tra các thinking block cũ với cuộc hội thoại đã tạo ra chúng. Bản tóm tắt thay thế một phần hội thoại, nhưng phép kiểm tra chấp nhận sự thay thế khi chính API viết bản tóm tắt, nên thinking trong các lượt được giữ có thể vẫn hợp lệ.

## Các điểm chính

Thinking block trong các lượt được giữ vẫn hợp lệ khi **tất cả** điều kiện sau đúng:
- **Request compaction chạy trên mô hình có preserved thinking.** Điều kiện này áp dụng cho mọi request compaction kể từ khi thinking block được tạo, không chỉ lần gần nhất. Một cách đáp ứng là gửi mọi request compaction tới đúng mô hình mà cuộc hội thoại đang dùng.
- **Các lượt được giữ nằm liền sau các message đã tóm tắt và được gửi nguyên vẹn.** Gửi từng message được giữ đúng như trong lịch sử, không bỏ qua hay chèn message giữa message tóm tắt cuối cùng và message được giữ đầu tiên. Message được giữ đầu tiên cũng phải có vai trò khác với message tóm tắt cuối cùng.
- **`system` và các `tools` không đánh dấu `defer_loading: true` không thay đổi.** Chúng phải giống nhau ở request compaction và ở các request đã tạo ra thinking được giữ, và vẫn giữ nguyên ở các request sau đó.

Nếu một điều kiện không đúng, việc compact không gây lỗi và API vẫn chấp nhận block compaction ở các request sau; thứ bị lỗi là thinking được giữ, ở request đầu tiên sau đó gửi nó.

## Các mục trong trang gốc

Điều kiện để thinking được giữ vẫn hợp lệ · Compact lại mà không làm hỏng thinking cũ · Đổi system prompt hoặc công cụ · Kiểm tra thinking được giữ có còn hiệu lực · Tính khả dụng (hỗ trợ API, beta header bắt buộc).

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/compaction-thinking-blocks)
- [Compaction](compaction.md)
- [Preserved thinking](preserved-thinking.md)
- [Compaction giữ lại các lượt gần nhất](compaction-keep-recent-turns.md)

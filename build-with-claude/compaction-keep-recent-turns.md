---
title: Compaction giữ lại các lượt gần nhất (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/compaction-keep-recent-turns
description: Tóm tắt các lượt cũ của hội thoại bằng compaction theo yêu cầu và gửi các lượt gần nhất nguyên văn sau bản tóm tắt.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/compaction-keep-recent-turns). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Compaction kiểu giữ đuôi (keep-tail) giữ nguyên văn vài lượt cuối của hội thoại sau bản tóm tắt. Nó thay đổi hai điều trong vòng lặp compaction: những message nào đi vào request compaction, và những gì bạn gửi sau đó.

## Các điểm chính

- **Chọn lượt cần giữ:** không có tham số nào quy định lượt nào được giữ. Bạn chọn một điểm cắt trong lịch sử: các message trước điểm cắt đi vào request compaction, từ điểm cắt trở đi được giữ. Lượt được giữ quay lại Claude đủ độ dài, nên giữ càng nhiều thì compaction giải phóng càng ít chỗ.
- **Đặt điểm cắt ở nơi không có lệnh gọi công cụ bị bỏ ngỏ:** mỗi lệnh gọi công cụ và kết quả của nó phải nằm cùng một phía. Nếu các message gửi đi kết thúc bằng lượt `assistant` có lệnh gọi công cụ chưa có kết quả, API từ chối request compaction.
- **Compact các lượt cũ và gửi phần còn lại sau block:** để request compaction chỉ chứa các lượt cũ (vì API tóm tắt mọi message nó nhận), rồi đặt block trước các lượt được giữ. Gửi các lượt được giữ đúng như trong lịch sử, kể cả thinking block. Cả hai request mang beta header của compaction theo yêu cầu.
- **Chương trình ví dụ** (vòng lặp được chỉnh để giữ hai lượt cuối) khác vòng lặp gốc ở bốn điểm: cách chọn điểm cắt (tách lịch sử cách cuối bốn message để các lượt được giữ bắt đầu bằng message `user`), cách quyết định khi nào compact (số lượt phải nhiều hơn số lượt giữ), request compaction (chỉ gửi các message cũ) và bước hoán đổi (lịch sử mới là message trả về rồi tới các lượt được giữ).

## Các mục trong trang gốc

Chọn lượt cần giữ · Compact các lượt cũ và gửi phần còn lại sau block · Giữ thinking hợp lệ trong các lượt được giữ · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/compaction-keep-recent-turns)
- [Compaction theo yêu cầu](compaction-on-demand.md)
- [Giữ thinking block hợp lệ](compaction-thinking-blocks.md)

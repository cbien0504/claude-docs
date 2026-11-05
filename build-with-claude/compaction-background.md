---
title: Compaction ở chế độ nền (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/compaction-background
description: Yêu cầu bản tóm tắt compaction theo yêu cầu trong khi hội thoại tiếp tục trên toàn bộ lịch sử, rồi hoán đổi block vào khi nó đến.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/compaction-background). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Compaction ở chế độ nền (thường gọi là async compaction) thay đổi hai điều so với vòng lặp compaction theo yêu cầu: request compaction chạy trong khi hội thoại vẫn tiếp tục trên toàn bộ lịch sử, và việc hoán đổi (swap) block vào lịch sử chờ đến khi bản tóm tắt về tới.

## Các điểm chính

Cách hoán đổi hoạt động khi công việc vẫn tiếp diễn:
1. Gửi request compaction với lịch sử hiện có và ghi lại nó chứa bao nhiêu message.
2. Trong lúc request chạy, tiếp tục hội thoại trên toàn bộ lịch sử: chỉ thêm lượt mới, không sửa gì đã có trong lịch sử và không bắt đầu request compaction khác cho tới khi cái này được hoán đổi hoặc thất bại.
3. Khi phản hồi về với `stop_reason` là `"compaction"`, bỏ đúng những message đã gửi ở đầu lịch sử và đặt message trả về vào chỗ đó. Mọi lượt thêm từ bước 1 vẫn nằm sau nó. (Ví dụ: nếu request chứa message 1–5 và hội thoại thêm message 6–8, sau khi hoán đổi lịch sử là block rồi đến message 6–8.)
4. Gửi lịch sử đã hoán đổi ở request đầu tiên sau khi block đến, để thinking sinh ra trong lúc viết bản tóm tắt vẫn hợp lệ.

- Nếu phản hồi có `stop_reason` khác thì không có bản tóm tắt, tính là thất bại ở bước 2: giữ nguyên toàn bộ lịch sử.
- Request compaction tính vào giới hạn tốc độ như mọi request khác, và trong lúc chạy ứng dụng có hai request mở cùng lúc. Vì hội thoại tiếp tục lớn lên đến khi hoán đổi, hãy bắt đầu request khi cửa sổ ngữ cảnh còn đủ chỗ cho các lượt sẽ thêm vào.

## Các mục trong trang gốc

Cách hoán đổi hoạt động khi công việc tiếp diễn · Yêu cầu bản tóm tắt ở chế độ nền · Giữ thinking hợp lệ trong lúc bản tóm tắt được tạo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/compaction-background)
- [Compaction theo yêu cầu](compaction-on-demand.md)
- [Giữ thinking block hợp lệ](compaction-thinking-blocks.md)

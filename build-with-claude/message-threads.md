---
title: Message threads (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/message-threads
description: Giúp agent chạy dài có thời gian tới token đầu tiên nhanh hơn, đặc biệt trong hội thoại dài, bằng cách chỉ gửi các message mới ở mỗi request.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/message-threads). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Với message thread, request nhỏ hơn và thời gian tới token đầu tiên thấp và ổn định hơn khi hội thoại dài ra. Thread hữu ích nhất trong các vòng lặp agent dài: không dùng thread thì mỗi lượt đều tải lên toàn bộ hội thoại, và API phải kiểm tra rồi tokenize lại toàn bộ; với thread, phần lớn công việc đó chỉ áp dụng cho lượt mới. Bạn chỉ thêm một tham số `thread` vào request Messages API.

> **Lưu ý:** message thread khác với session thread trong Claude Managed Agents.

## Các điểm chính

- **Cách hoạt động:** một message thread giữ hội thoại trên máy chủ trong thời gian ngắn.
  - **Tạo (create):** gửi request đầu tiên với toàn bộ hội thoại, `system` và `tools`, thêm `"thread": {"type": "create"}`. API lưu hội thoại, gồm cả câu trả lời của Claude, theo `id` của phản hồi.
  - **Tiếp tục (continue):** chỉ gửi các message kể từ phản hồi trước, thêm `"thread": {"type": "continue", "previous_message_id": "<id trước>"}`; bỏ `system` và `tools` ra khỏi request vì thread giữ các giá trị từ request tạo. Dùng `id` của mỗi phản hồi mới cho lượt kế tiếp.
  - **Phát lại (replay):** thread chỉ là nỗ lực tốt nhất (best-effort): hết hạn 5 phút sau request cuối cùng, và API xóa nó không quá 1 giờ sau lần dùng cuối. Nếu API không còn tiếp tục được thread thì request continue trả lỗi 404; khi đó gửi lại toàn bộ hội thoại trong một request create mới.
- **Ứng dụng của bạn vẫn là nguồn sự thật** về hội thoại: hãy giữ bản sao của mọi message và xây đường phát lại ngay từ đầu. Không phản hồi nào cho biết API đã lưu lượt đó hay chưa; bạn chỉ biết ở request continue kế tiếp.
- **SDK có thread helper** dựng các request thread giúp bạn, giữ toàn bộ hội thoại trong bộ nhớ và tự thêm beta header; `cache_control` cấp cao nhất là tùy chọn để bật prompt caching cho từng lượt.

## Các mục trong trang gốc

Cách message thread hoạt động · Dùng thread với SDK · Tự gửi trường `thread` · Gửi gì ở mỗi request · Prompt caching trên thread · Streaming · Khôi phục khi không tiếp tục được thread (sau refusal, dùng fallback với thread) · Compact một hội thoại · Cách helper của SDK hoạt động · Lỗi · Tính năng thread không hỗ trợ · Hạn chế · Giá và giới hạn tốc độ · Lưu giữ dữ liệu · Xem thêm · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/message-threads)
- [Session thread trong Managed Agents](../managed-agents/session-threads.md)
- [Prompt caching](prompt-caching.md)
- [Sử dụng Messages API](working-with-messages.md)

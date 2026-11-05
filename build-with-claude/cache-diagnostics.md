---
title: Cache diagnostics (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/cache-diagnostics
description: Chẩn đoán các lần trượt cache prompt ngoài ý muốn bằng cách so sánh hai request liên tiếp và chỉ ra chính xác nơi tiền tố prompt bị lệch.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/cache-diagnostics). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Prompt caching giảm đáng kể độ trễ và chi phí, nhưng chỉ khi phần đầu prompt giống hệt từng byte so với một request gần đây. Một công cụ bị đổi thứ tự, dấu thời gian chèn vào system prompt hoặc một chỉnh sửa ở message trước đó đều có thể làm vô hiệu cache mà không báo gì. Cache diagnostics giúp lấp khoảng trống này: bạn truyền `id` của phản hồi trước, API so sánh hai request và cho biết chúng lệch nhau ở đâu (mô hình, system prompt, công cụ hay lịch sử message), để bạn sửa đúng nguyên nhân gốc thay vì đoán.

## Các điểm chính

- **Cách hoạt động:** với mỗi request có đối tượng `diagnostics`, API lưu một "dấu vân tay" gọn nhẹ theo `id` của phản hồi (request không có đối tượng này thì không lưu gì). Ở request kế tiếp, truyền `id` của phản hồi trước vào `diagnostics.previous_message_id`; API dựng lại dấu vân tay, so với bản đã lưu và đính kèm kết quả vào phản hồi.
- **Quyền riêng tư:** dấu vân tay chỉ chứa giá trị băm và ước lượng số token (không bao giờ chứa nội dung prompt thô), được giữ trong thời gian giới hạn, gắn với tổ chức và workspace của bạn, và không dùng cho mục đích nào khác.
- **Cách dùng cơ bản:** đưa `diagnostics` vào mọi lượt. Lượt đầu truyền `"previous_message_id": null` để tham gia mà chưa có message trước để so sánh; các lượt sau truyền `id` của phản hồi trước. Beta header `cache-diagnosis-2026-04-07` không còn bắt buộc.
- **Streaming:** `diagnostics` xuất hiện trong sự kiện `message_start`.
- **Đọc cùng với usage:** phép so sánh xét cấu trúc request, độc lập với việc cache có trúng thật hay không; kết hợp kết quả `diagnostics` với `usage.cache_read_input_tokens`.

## Các mục trong trang gốc

Cách cache diagnostics hoạt động · Cách dùng cơ bản · Streaming · Truyền diagnostics qua vòng lặp hội thoại · Định dạng phản hồi · Các loại lý do trượt cache · Đọc diagnostics cùng với usage · Hạn chế · Lưu giữ dữ liệu · Xem thêm · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/cache-diagnostics)
- [Prompt caching](prompt-caching.md)

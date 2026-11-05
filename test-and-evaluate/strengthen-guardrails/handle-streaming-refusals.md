---
title: Xử lý refusal khi streaming (tóm tắt)
source: https://platform.claude.com/docs/en/test-and-evaluate/strengthen-guardrails/handle-streaming-refusals
description: Phát hiện và xử lý stop reason refusal trong phản hồi streaming, và thử lại request bị từ chối trên mô hình dự phòng.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/test-and-evaluate/strengthen-guardrails/handle-streaming-refusals). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Từ các mô hình Claude 4 trở đi, phản hồi streaming của Claude API trả về `stop_reason` là `"refusal"` khi các bộ phân loại streaming (streaming classifiers) can thiệp để xử lý các vi phạm chính sách tiềm ẩn. Tính năng an toàn này giúp duy trì tuân thủ nội dung trong lúc streaming theo thời gian thực. Trang này nói về cách refusal xuất hiện trong phản hồi streaming.

## Các điểm chính

- **Cách dùng theo bề mặt:** trong Messages API, stream kết thúc với `stop_reason` là `"refusal"`, và `stop_details` (gồm `category` và `explanation`) đến trong sự kiện `message_delta`. Trong Managed Agents, lượt bị từ chối kết thúc và session chuyển sang trạng thái idle; coi lượt là bị từ chối nếu `stop_details.type` hoặc `stop_reason.type` là `"refusal"`.
- **Định dạng phản hồi:** đối tượng `stop_details` luôn có mặt khi bị từ chối, nhưng `category` và `explanation` có thể là `null` (ví dụ khi từ chối không thuộc loại nào có tên). Hãy rẽ nhánh theo `stop_reason` hoặc `stop_details.type` thay vì giả định hai trường này luôn có giá trị.
- **Đặt lại ngữ cảnh sau refusal:** khi nhận `stop_reason` là `refusal`, bạn phải đặt lại ngữ cảnh hội thoại trước khi tiếp tục: xóa hoặc diễn đạt lại lượt gây ra refusal, hoặc xóa hoàn toàn lịch sử hội thoại. Tiếp tục mà không đặt lại sẽ tiếp tục bị từ chối.

## Các mục trong trang gốc

Định dạng phản hồi API · Đặt lại ngữ cảnh sau refusal · Hướng dẫn triển khai · Các loại refusal hiện tại · Thực hành tốt · Ghi chú di chuyển · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/test-and-evaluate/strengthen-guardrails/handle-streaming-refusals)
- [Stop reason và dự phòng](../../build-with-claude/handling-stop-reasons.md)
- [Refusals và fallback](../../build-with-claude/refusals-and-fallback.md)

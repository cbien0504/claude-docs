---
title: Refusal và fallback (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/refusals-and-fallback
description: Cách các mô hình Claude Fable, Claude Opus, Claude Sonnet 5.5 và Claude Haiku 5.5 trả về refusal do bộ phân loại, và cách thử lại request bị từ chối trên mô hình dự phòng.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/refusals-and-fallback). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang này mô tả một refusal trông như thế nào, cách tính phí refusal, và ba cách thử lại một request bị từ chối trên mô hình dự phòng (fallback): fallback phía máy chủ, fallback phía client bằng middleware của SDK, hoặc tự viết phần thử lại.

## Các điểm chính

- **Server-side fallback:** gửi request, có thể đặt tên các mô hình dự phòng của riêng bạn; phản hồi chứa kết quả; có mục về tiếp tục hội thoại, streaming, phản hồi không streaming, thanh toán và giới hạn tốc độ, và định tuyến cố định (sticky routing).
- **Fallback phía client bằng middleware SDK:** cách thiết lập và hành vi của nó.
- **Tự viết phần thử lại** cho trường hợp dùng HTTP thô hoặc logic retry tùy chỉnh (xem thêm Fallback credit để tránh trả phí ghi cache hai lần).
- Trang cũng có mục về giữ phần suy luận trong thinking block, cách tính phí refusal, refusal trong Message Batches và các lỗi thường gặp.

## Các mục trong trang gốc

Refusal trông như thế nào (giữ suy luận trong thinking block) · Cách tính phí refusal · Chọn cách fallback · Server-side fallback · Fallback phía client với middleware SDK · Tự viết phần thử lại · Refusal trong Message Batches · Các lỗi thường gặp · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/refusals-and-fallback)
- [Fallback credit](fallback-credit.md)
- [Xử lý refusal khi streaming](../test-and-evaluate/strengthen-guardrails/handle-streaming-refusals.md)
- [Stop reason và dự phòng](handling-stop-reasons.md)

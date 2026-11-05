---
title: Fallback credit (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/fallback-credit
description: Tránh trả chi phí prompt cache hai lần khi bạn thử lại một request bị từ chối trên mô hình khác.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/fallback-credit). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Prompt cache gắn với từng mô hình. Khi một mô hình từ chối request và bạn thử lại trên mô hình khác, phần tiền tố hội thoại đã được cache cho mô hình đầu phải được ghi đầy đủ vào cache của mô hình mới. Ghi cache tốn kém hơn đọc cache; fallback credit loại bỏ chi phí phát sinh thêm đó. Bạn chỉ cần trang này khi tự xây phần thử lại, qua HTTP thô hoặc logic retry tùy chỉnh; server-side fallback và client-side fallback bằng middleware của SDK đã xử lý sẵn.

## Các điểm chính

Luồng cơ bản gồm ba bước:
1. **Chọn tham gia bằng beta header:** gửi request có thể bị từ chối với header `anthropic-beta: fallback-credit-2026-07-01`. Header `server-side-fallback-2026-07-01` cũng cấp các trường tương tự, trừ trên Claude Models on Google Cloud (Google managed) và Amazon Bedrock, nơi header đó trả lỗi 400.
2. **Đọc hai trường từ lần từ chối:** `stop_details` chứa `fallback_credit_token` (chuỗi mờ đại diện cho khoản tín dụng) và `fallback_has_prefill_claim` (giá trị boolean cho biết nên dùng dạng body thử lại nào). Cả hai là `null` khi không có tín dụng cho lần từ chối đó.
3. **Dựng request thử lại:** xuất phát từ body request bị từ chối, đặt `model` là mô hình dự phòng và thêm token vào tham số cấp cao nhất `fallback_credit_token`; chọn dạng body theo bảng trong trang gốc.

## Các mục trong trang gốc

Luồng cơ bản · Ví dụ · Nơi áp dụng được · Kiểm tra khoản tín dụng đã được áp dụng · Khi request thử lại bị từ chối · Tham chiếu · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/fallback-credit)
- [Refusals và fallback](refusals-and-fallback.md)
- [Prompt caching](prompt-caching.md)

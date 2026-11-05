---
title: Claude Models on Google Cloud – tổng quan (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/claude-models-on-google-cloud/overview
description: So sánh Claude Models on Google Cloud (Anthropic managed) và (Google managed), và cách xác định bạn đang dùng cái nào.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/claude-models-on-google-cloud/overview). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Bạn có thể dùng Claude thông qua dự án Google Cloud theo hai cách:

- **Anthropic managed:** Anthropic vận hành Claude API.
- **Google managed:** Google vận hành các mô hình Claude như một phần của Agent Platform trên Google Cloud.

## Các điểm khác biệt chính

| Khía cạnh | Anthropic managed | Google managed |
| --- | --- | --- |
| Bề mặt API | Các endpoint Claude API `/v1/{endpoint}` | Các endpoint prediction của Agent Platform |
| Định dạng request | Giống Claude API: `model` trong body, header `anthropic-version` | `model` nằm trong URL, `anthropic_version` nằm trong body |
| Streaming | `"stream": true` trong body | Endpoint riêng `:streamRawPredict` |
| Vị trí (location) | `global` | Endpoint global, đa vùng hoặc theo vùng |
| Model ID cho mô hình trước Claude 4.6 | ID của Claude API, ví dụ `claude-haiku-4-5-20251001` | ID của Claude API nhưng dùng `@` thay cho dấu gạch nối trước ngày snapshot, ví dụ `claude-haiku-4-5@20251001` |
| Dịch vụ cần bật trên dự án | Xem phần thiết lập tài khoản của trang Anthropic managed | Xem trang Google managed |

## Các mục trong trang gốc

Hai gói dịch vụ Google Cloud khác nhau thế nào · Điểm chung của cả hai · Chuyển đổi giữa hai gói · Bạn đang dùng gói nào? · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/claude-models-on-google-cloud/overview)
- [Anthropic managed](anthropic-managed.md)
- [Google managed](google-managed.md)

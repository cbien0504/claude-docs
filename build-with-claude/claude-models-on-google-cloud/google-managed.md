---
title: Claude Models on Google Cloud – Google managed (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/claude-models-on-google-cloud/google-managed
description: Google vận hành Claude Models on Google Cloud (Google managed) như một phần của Agent Platform trên Google Cloud; bạn có thể gọi Claude bằng các SDK client của Anthropic.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/claude-models-on-google-cloud/google-managed). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trong gói này, Google vận hành các mô hình Claude trong Agent Platform của Google Cloud. Các SDK client của Anthropic hỗ trợ gói này qua `AnthropicVertex` (C#: `AnthropicVertexClient`; Go: `vertex.WithGoogleAuth()`; Java: `VertexBackend`; PHP: `Anthropic\Vertex\Client`; Ruby: `Anthropic::VertexClient`). CLI `ant` không hỗ trợ gói này.

## Các điểm chính

- **Điều kiện trước khi gọi API:**
  1. Một dự án Google Cloud có thể dùng Agent Platform.
  2. gcloud CLI đã cài (cho phát triển cục bộ).
  3. Danh tính thực hiện lệnh gọi có vai trò IAM chứa quyền `aiplatform.endpoints.predict`, ví dụ Agent Platform User (`roles/aiplatform.user`).
  4. Credential Google Cloud cho danh tính đó: với ví dụ SDK có thể cần chạy `gcloud auth application-default login`; ví dụ cURL lấy token bằng `gcloud auth print-access-token`.
- **Gửi request:** request tới URL endpoint của Agent Platform kết thúc bằng `:rawPredict`; request streaming dùng `:streamRawPredict`. Request gần giống request Messages API, khác ở hai điểm: **mô hình** nằm trong URL endpoint (với cURL, bỏ `model` khỏi body), và **phiên bản** truyền bằng `anthropic_version` trong body (không phải header), đặt là `vertex-2023-10-16` hoặc phiên bản API `2026-10-21`.
- Trang có ví dụ SDK cho Python, TypeScript, C#, Go, Java (Gradle/Maven), PHP và Ruby.

## Các mục trong trang gốc

Trước khi gọi API (cài SDK) · Gửi request (model ID của API) · Endpoint global, đa vùng và theo vùng · Hỗ trợ tính năng (tính năng không hỗ trợ, cửa sổ ngữ cảnh) · Thanh toán, giới hạn tốc độ và ghi log · Chuyển từ gói Anthropic managed · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/claude-models-on-google-cloud/google-managed)
- [Tổng quan Claude Models on Google Cloud](overview.md)
- [Anthropic managed](anthropic-managed.md)

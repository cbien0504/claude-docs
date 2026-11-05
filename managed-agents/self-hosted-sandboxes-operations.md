---
title: Giám sát và xử lý sự cố worker tự lưu trữ (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-operations
description: Đọc độ sâu hàng đợi, dừng session và worker mà không mất việc, và sửa các lỗi thường gặp của sandbox tự lưu trữ.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-operations). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Các lệnh gọi giám sát trong trang này chạy từ công cụ giám sát hoặc vận hành của bạn, xác thực bằng Claude API key. Các worker helper xử lý vòng nhận việc (claim) và giữ kết nối (keep-alive) nên bạn không gọi trực tiếp các endpoint đó. Các endpoint này chấp nhận khóa API của tổ chức hoặc khóa environment; hãy gọi từ bên ngoài host của worker bằng khóa API của tổ chức. Đặt `ANTHROPIC_API_KEY` trên host của worker sẽ làm lộ một credential phạm vi tổ chức cho các lệnh gọi công cụ của agent.

## Các điểm chính

- **Đọc độ sâu hàng đợi:** gọi `GET /v1/environments/{environment_id}/work/stats`. Một số trường: `depth` (số mục đang chờ được nhận) và `pending` (số mục đã được worker nhận nhưng chưa xác nhận; worker helper xác nhận từng mục trước khi xử lý nên giá trị này gần bằng 0 khi vận hành bình thường).
- **Dừng session và dừng worker một cách êm** để không mất việc.
- **Xử lý sự cố:** worker không kết nối; session nằm lại trong hàng đợi; memory store không mount được; lệnh gọi công cụ tùy chỉnh không bao giờ trả về; lệnh gọi công cụ MCP được bao bọc bị treo.

## Các mục trong trang gốc

Đọc độ sâu hàng đợi · Dừng session êm · Dừng worker êm · Xử lý sự cố (worker không kết nối, session nằm hàng đợi, memory store không mount, lệnh gọi công cụ tùy chỉnh không trả về, công cụ MCP bao bọc bị treo).

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-operations)
- [Triển khai worker](self-hosted-sandboxes-workers.md)
- [Tham chiếu worker](self-hosted-sandboxes-reference.md)
- [Memory stores trong sandbox tự lưu trữ](self-hosted-sandboxes-memory.md)

---
title: Tool runner – SDK (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-runner
description: Dùng tool runner của SDK để tự động xử lý vòng lặp agent, bao bọc lỗi và an toàn về kiểu.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-runner). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Tool runner xử lý vòng lặp agent, bao bọc lỗi và an toàn về kiểu để bạn không phải tự làm. Thay vì tự xử lý lệnh gọi công cụ, kết quả công cụ và quản lý hội thoại, tool runner tự động chạy các công cụ khi Claude gọi, xử lý chu trình request/response và quản lý trạng thái hội thoại. Khi cần phê duyệt có người tham gia (human-in-the-loop), ghi log tùy chỉnh hoặc thực thi có điều kiện, hãy dùng vòng lặp thủ công.

## Các điểm chính

- **Cách dùng cơ bản** và **lặp qua tool runner.**
- **Cách dùng nâng cao:** tiếp quản lịch sử message; quản lý ngữ cảnh tự động; gỡ lỗi việc thực thi công cụ; chặn lỗi công cụ; sửa kết quả công cụ.
- **Streaming** có mục riêng.

## Các mục trong trang gốc

Cách dùng cơ bản · Lặp qua tool runner · Cách dùng nâng cao (tiếp quản lịch sử message, quản lý ngữ cảnh tự động, gỡ lỗi, chặn lỗi, sửa kết quả) · Streaming · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-runner)
- [Xử lý lệnh gọi công cụ](handle-tool-calls.md)
- [Parallel tool use](parallel-tool-use.md)

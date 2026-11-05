---
title: Permission policies (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/permission-policies
description: Kiểm soát khi nào các công cụ của agent và MCP được chạy.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/permission-policies). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Permission policy kiểm soát việc các công cụ do server thực thi (toolset agent dựng sẵn và MCP toolset) chạy tự động, chờ bạn phê duyệt, hay được máy chủ đánh giá từng lệnh gọi. Công cụ tùy chỉnh do ứng dụng của bạn chạy và do bạn kiểm soát nên policy không áp dụng cho chúng.

## Các điểm chính

- **Các loại policy:** trang gốc có bảng liệt kê từng loại và hành vi (ví dụ MCP toolset mặc định là `always_ask`, yêu cầu người dùng duyệt trước mỗi lệnh gọi công cụ). Có chế độ `auto` để máy chủ tự đánh giá từng lệnh gọi.
- **Đặt policy cho một toolset:** quyền của toolset agent và quyền của MCP toolset.
- **Ghi đè policy cho từng công cụ.**
- **Xem từng lệnh gọi đã được đánh giá ra sao.**
- **Phản hồi các yêu cầu xác nhận** (liên quan sự kiện `user.tool_confirmation`).

## Các mục trong trang gốc

Các loại permission policy · Đặt policy cho một toolset · Ghi đè policy của từng công cụ · Để máy chủ đánh giá từng lệnh gọi bằng `auto` · Xem từng lệnh gọi được đánh giá thế nào · Phản hồi yêu cầu xác nhận · Công cụ tùy chỉnh · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/permission-policies)
- [Công cụ](tools.md)
- [MCP connector](mcp-connector.md)
- [Tham chiếu](reference.md)

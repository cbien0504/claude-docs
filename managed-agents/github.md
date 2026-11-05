---
title: Truy cập GitHub (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/github
description: Kết nối agent của bạn với các repository GitHub để clone, đọc và tạo pull request.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/github). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Bạn có thể mount một repository GitHub vào sandbox của session và kết nối GitHub MCP để tạo pull request. Các repository GitHub được cache, nên những session sau dùng cùng repository sẽ khởi động nhanh hơn.

## Các điểm chính

- **GitHub MCP và tài nguyên của session:** trước tiên tạo agent khai báo GitHub MCP server (định nghĩa agent chứa URL server nhưng không chứa token xác thực); sau đó tạo session mount repository. Với environment ở chế độ mạng `limited`, việc tạo session thất bại với lỗi 400 khi agent khai báo một MCP server có host không được cho phép. Tài nguyên `github_repository` nhận một số trường được liệt kê trong bảng của trang gốc.
- Trang cũng nói về quyền của token, nhiều repository, quản lý repository trên session đang chạy và cách tạo pull request.

## Các mục trong trang gốc

GitHub MCP và tài nguyên session · Quyền của token · Nhiều repository · Quản lý repository trên session đang chạy · Tạo pull request · Các bước tiếp theo · Tính khả dụng (hỗ trợ API, beta header bắt buộc, xử lý dữ liệu).

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/github)
- [MCP connector](mcp-connector.md)
- [Xác thực bằng vault](vaults.md)
- [Cài đặt môi trường đám mây](environments.md)

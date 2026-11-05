---
title: Quickstart MCP tunnels (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/quickstart
description: Kết nối Claude với một MCP server riêng bằng triển khai Docker Compose cục bộ.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/quickstart). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Bài quickstart dẫn bạn từ việc tạo tunnel đến việc Claude gọi được một MCP server riêng thông qua tunnel đó. Bài dùng Docker Compose với cách cấp credential thủ công (manual provisioning), là đường ngắn nhất để thử cục bộ. Với môi trường production, xem hướng dẫn triển khai bằng Helm hoặc Docker Compose. MCP tunnels đang ở dạng research preview và cần gửi yêu cầu truy cập.

## Các điểm chính

- **Bạn sẽ dựng gì:** một tunnel stack gồm hai container (proxy và cloudflared) cùng một MCP server mẫu chạy bên cạnh. Khi mọi thứ chạy, server mẫu truy cập được từ Claude tại địa chỉ dạng `https://echo.<tunnel-domain>/mcp` dù không có cổng công khai nào đang lắng nghe.
- **Cần có:**
  - Docker và Docker Compose trên máy có kết nối internet outbound.
  - Một vai trò trong Claude Console có quyền quản lý MCP tunnels.
  - OpenSSL phiên bản 1.1.1 trở lên (đã cài sẵn trên macOS và hầu hết bản phân phối Linux; trên Windows cần cài riêng và có trong `PATH`).
- **Các bước chính (7 bước, có lệnh cho bash và PowerShell):**
  1. **Tạo tunnel:** trong Claude Console, vào trang MCP tunnels, chọn **New tunnel** (mỗi tunnel thuộc một workspace) và để tắt tùy chọn thiết lập truy cập theo chương trình. Sau khi tạo, sao chép hai giá trị ở mục Connection: **Domain** (dạng `abcd1234.tunnel.anthropic.com`) và **Token**.
  2. **Chuẩn bị thư mục triển khai.**
  3. **Tạo CA và chứng chỉ máy chủ:** proxy kết thúc inner TLS bằng chứng chỉ do một CA bạn kiểm soát ký. Sau đó, trên trang chi tiết tunnel, chọn **Add certificate** và tải `data/ca.crt` lên; huy hiệu **Needs certificate** sẽ biến mất.
  4. **Viết MCP server mẫu.**
  5. **Viết cấu hình proxy và file compose.**
  6. **Khởi động:** chạy `docker compose up -d` rồi kiểm tra log; bạn sẽ thấy một dòng `route configured` cho `echo` và bốn dòng `Registered tunnel connection`. Container cần vài giây để khởi động, nếu lệnh xem log trả về rỗng thì chạy lại.
  7. **Gọi từ Claude:** trong Console, vào trang Sessions, chọn **Create session**, tạo agent mới và thêm MCP server từ tunnel của bạn (đặt **Subdomain** là `echo` và **Path** là `mcp`), chọn một environment, rồi tạo session và yêu cầu Claude dùng công cụ `hello` để chào tunnel. Bạn sẽ thấy một lệnh gọi công cụ kèm kết quả.

## Các mục trong trang gốc

Bạn sẽ dựng gì · Bạn cần gì · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/quickstart)
- [Tổng quan MCP tunnels](overview.md)
- [Kiến trúc và thành phần](concepts.md)
- [Quản lý trong Console](console.md)

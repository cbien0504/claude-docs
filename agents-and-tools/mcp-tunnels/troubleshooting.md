---
title: Xử lý sự cố MCP tunnels (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/troubleshooting
description: Chẩn đoán các sự cố về kết nối, TLS, kiểm tra IP và định tuyến OAuth trong một tunnel stack.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/troubleshooting). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Một request đi qua tunnel có thể thất bại ở một trong ba lớp; hãy chẩn đoán theo thứ tự: kết nối outbound tới tunnel edge, inner TLS, và kiểm tra IP upstream. MCP tunnels đang ở dạng research preview.

## Các điểm chính

Bảng tham khảo nhanh ghép triệu chứng với nguyên nhân. Một số ví dụ:
- **Tunnel không xuất hiện trong bộ chọn MCP server của agent:** bộ chọn chỉ liệt kê các tunnel thuộc workspace của session có ít nhất một chứng chỉ đang hoạt động.
- **Phía gọi thấy HTTP 500; log cloudflared ghi `No ingress rules were defined`:** cloudflared không có đích cục bộ.
- **Proxy ghi log `no route for host`:** `tunnel_domain` không khớp với domain được gán, hoặc `config.yaml` bị sửa mà không khởi động lại.
- **Proxy ghi log `IP validation failed: <ip> is not a private address`:** địa chỉ upstream không nằm trong dải cho phép.

## Các mục trong trang gốc

Tham khảo nhanh · OAuth lỗi khi đứng sau danh sách cho phép IP nguồn · Lỗi xác thực của thành phần setup · Tunnel không kết nối được · Lỗi chứng chỉ · Kiểm tra IP upstream.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/troubleshooting)
- [Tổng quan MCP tunnels](overview.md)
- [Tham chiếu](reference.md)
- [Bảo mật](security.md)

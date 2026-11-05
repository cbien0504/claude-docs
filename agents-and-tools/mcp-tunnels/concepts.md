---
title: Kiến trúc và thành phần của MCP tunnels (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/concepts
description: Tên chuẩn của các thành phần trong một triển khai MCP tunnel, hai chế độ cấp credential và mô hình kết nối.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/concepts). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang này thống nhất thuật ngữ dùng trong toàn bộ tài liệu MCP tunnels. Nhiều thành phần xuất hiện dưới các tên khác nhau trong file cấu hình, container image và văn bản; các bảng trong trang đưa ra một tên chuẩn cho mỗi thành phần cùng các biệt danh bạn có thể gặp. MCP tunnels đang ở dạng research preview.

## Các điểm chính

- **Tunnel stack:** hai container bạn chạy trong mạng của mình để gắn vào một tunnel (proxy và cloudflared). Một stack phục vụ một tunnel và có thể nhân bản trên nhiều host để đảm bảo tính sẵn sàng. Với truy cập theo chương trình, thành phần setup chạy cạnh stack để cấp credential.
- **Proxy:** thành phần định tuyến của Anthropic; kết thúc inner TLS, kiểm tra IP upstream nằm trong dải cho phép và định tuyến request tới MCP server upstream theo hostname. Còn xuất hiện dưới tên `mcp-proxy` (tên image, service Compose, container Helm) và `mcp-gateway` (đường dẫn cấu hình `/etc/mcp-gateway/config.yaml` và tiền tố giá trị Helm `gateway.config.*`).
- **cloudflared:** trình kết nối tunnel mã nguồn mở của Cloudflare; mở các kết nối chỉ outbound từ mạng của bạn tới tunnel edge và mang lưu lượng đã mã hóa giữa edge và proxy. Không liên quan đến Managed Agent.
- **Hai chế độ cấp credential:** truy cập theo chương trình (programmatic access, khuyến nghị) và cấp thủ công (manual).

## Các mục trong trang gốc

Các thành phần · Cấp credential · Mô hình kết nối · Xem thêm.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/concepts)
- [Tổng quan MCP tunnels](overview.md)
- [Quickstart](quickstart.md)

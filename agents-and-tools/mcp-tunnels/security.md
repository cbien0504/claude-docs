---
title: Bảo mật MCP tunnels (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/security
description: Hướng dẫn gia cố, xoay vòng credential, ứng phó khi nghi ngờ bị xâm phạm và gỡ bỏ cho các triển khai MCP tunnel.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/security). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Kiến trúc tunnel có các mặc định an toàn mạnh (kết nối chỉ outbound, mã hóa đầu-cuối và kiểm tra IP), nhưng độ an toàn tổng thể của tunnel stack còn phụ thuộc vào cách bạn cấu hình và vận hành nó. MCP tunnels đang ở dạng research preview.

## Các điểm chính

Thực hành tốt:
- **Yêu cầu OAuth trên mọi MCP server** theo đặc tả MCP authorization.
- **Bật SSO cho tổ chức:** tunnel, federation rule và service account được quản lý trong Claude Console; SSO áp dụng kiểm soát phiên của nhà cung cấp danh tính lên các quản trị viên có thể thay đổi chúng.
- **Giới hạn `upstream.allowed_ips`** bằng các dải CIDR nhỏ nhất bao phủ MCP server của bạn; đây là biện pháp phòng thủ SSRF chính của proxy.
- **Giám sát log:** cảnh báo khi có warning, lỗi hoặc mẫu lưu lượng bất thường từ tunnel stack.
- **Xoay vòng credential:** định kỳ xoay vòng chứng chỉ máy chủ và tunnel token, và ngay lập tức nếu nghi ngờ bị lộ.
- **Cập nhật image:** theo dõi các bản phát hành proxy mới và ghim image theo SHA-256 digest.
- **Giới hạn phạm vi mạng:** proxy và cloudflared chỉ nên tới được các đích liệt kê trong yêu cầu mạng.
- **Giới hạn phạm vi MCP server:** mỗi server chỉ nên lộ ra các công cụ và dữ liệu cần cho mục đích của nó.
- **Bảo vệ credential khi lưu trữ:** áp dụng quy trình quản lý bí mật của tổ chức cho khóa riêng và tunnel token.

Khi nghi ngờ bị xâm phạm (token của tunnel, khóa TLS hoặc host proxy): dừng tunnel stack (có hướng dẫn cho Helm và Docker Compose), gỡ các MCP server upstream khỏi mọi session Managed Agents đang dùng chúng và ngừng truyền URL của chúng trong khối `mcp_servers` của request Messages API, rồi lưu trữ (archive) tunnel.

## Các mục trong trang gốc

Thực hành tốt · Ứng phó khi nghi ngờ bị xâm phạm · Gỡ bỏ một tunnel.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/security)
- [Tổng quan MCP tunnels](overview.md)
- [Tham chiếu](reference.md)

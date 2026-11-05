---
title: MCP tunnels (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/overview
description: Kết nối Claude an toàn với các MCP server chạy trong mạng riêng của bạn mà không cần mở cổng inbound hay đưa dịch vụ ra internet công cộng.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/overview). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

MCP tunnels cho phép Claude kết nối tới các Model Context Protocol (MCP) server nằm trong mạng riêng của bạn. Lưu lượng đi qua một kết nối chỉ có chiều outbound, nên bạn không cần mở cổng firewall inbound, không cần đưa dịch vụ ra internet công cộng và không cần thêm dải IP của Anthropic vào danh sách cho phép (allowlist) ở máy chủ gốc.

> **Lưu ý:** MCP tunnels đang ở dạng research preview, được cung cấp "nguyên trạng" (as-is) và không cam kết về thời gian hoạt động, hỗ trợ hay tính liên tục. Dịch vụ phụ thuộc vào nhà cung cấp mạng bên thứ ba (Cloudflare), bên không cam kết về tính khả dụng của lớp truyền tải. Anthropic có thể thay đổi hoặc ngừng MCP tunnels bất kỳ lúc nào. Cần gửi yêu cầu để được cấp quyền truy cập.

## Các điểm chính

- **Cách hoạt động:** "tunnel stack" gồm hai thành phần chạy trong mạng của bạn:
  - **cloudflared:** trình kết nối tunnel mã nguồn mở của Cloudflare; chủ động mở các kết nối chỉ outbound tới tunnel edge và mang lưu lượng đã mã hóa từ Anthropic tới proxy.
  - **Proxy:** thành phần định tuyến của Anthropic; kết thúc inner TLS, kiểm tra IP upstream nằm trong dải cho phép và định tuyến mỗi request tới đúng MCP server upstream theo hostname.
- Mỗi MCP server bạn công bố có một hostname dưới tunnel domain của bạn (dạng `docs.<tunnel-domain>`). Bạn gắn các hostname này cho một agent trong Claude Console, hoặc truyền chúng vào Messages API qua MCP connector.
- **Điều kiện tiên quyết:** một nơi triển khai (cụm Kubernetes, hoặc máy ảo có Docker và Docker Compose); một tunnel (tạo trong Claude Console hoặc qua API; Helm chart cũng có thể tạo giúp khi cài); và cách để stack xác thực với Tunnels API. Cách khuyến nghị là truy cập theo chương trình (programmatic access) với Workload Identity Federation, khi đó stack tự cấp token ngắn hạn, lấy token của tunnel, và tự tạo, đăng ký chứng chỉ CA.
- **Dùng các MCP server qua tunnel:** trong Managed Agents (qua Console) hoặc trong Messages API.

## Các mục trong trang gốc

Cách hoạt động · Điều kiện tiên quyết (yêu cầu mạng) · Mô hình bảo mật (các lớp bảo mật, mô hình trách nhiệm chia sẻ, những gì nhà cung cấp truyền tải có thể quan sát) · Triển khai một tunnel · Dùng các MCP server qua tunnel (Managed Agents/Console, Messages API) · Các bước tiếp theo · Tính khả dụng (hỗ trợ API, beta header bắt buộc, xử lý dữ liệu).

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/overview)
- [Kiến trúc và thành phần](concepts.md)
- [Quickstart](quickstart.md)
- [Triển khai bằng Helm](deploy-helm.md) · [Triển khai bằng Docker Compose](deploy-compose.md)
- [Bảo mật](security.md)

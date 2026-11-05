---
title: Triển khai MCP tunnels bằng Helm (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/deploy-helm
description: Cài đặt tunnel stack trên cụm Kubernetes bằng Helm chart của Anthropic.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/deploy-helm). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Helm chart của Anthropic cài tunnel stack dưới dạng một Deployment duy nhất và gắn nó vào tunnel của bạn: tunnel do setup hook của chart tạo giúp, hoặc tunnel có sẵn bạn đã tạo trong Claude Console. MCP tunnels đang ở dạng research preview.

## Các điểm chính

Điều kiện cần có:
- **Một tunnel:** với truy cập theo chương trình, setup hook của chart tạo giúp khi bạn không cung cấp tunnel ID; muốn gắn vào tunnel có sẵn thì tạo trong Console và ghi lại tunnel ID.
- **Cách để chart xác thực với Tunnels API:** truy cập theo chương trình (khuyến nghị, qua Workload Identity Federation) hoặc thủ công (lấy tunnel token từ Console, tự tạo CA và chứng chỉ rồi đăng ký CA).
- **Một cụm Kubernetes** triển khai được bằng `helm` và `kubectl`; tab "không có truy cập theo chương trình" cần thêm `openssl` 1.1.1 trở lên.
- **Kết nối outbound** từ cụm tới `api.anthropic.com` (443 TCP) và tunnel edge (7844 TCP và UDP).
- **Một hoặc nhiều MCP server** truy cập được từ cụm tại các địa chỉ cấu hình trong `gateway.config.routes`.

## Các mục trong trang gốc

Trước khi bắt đầu · Tùy chọn: dùng MCP server mẫu · Cài đặt · Xác minh triển khai · Cấu hình tùy chọn (giới hạn egress bằng NetworkPolicy, tinh chỉnh proxy, tự cung cấp OIDC token) · Nâng cấp (từ chart 1.x, đổi cấu hình, xoay vòng tunnel token, gia hạn chứng chỉ) · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/deploy-helm)
- [Tổng quan MCP tunnels](overview.md)
- [Kiến trúc và thành phần](concepts.md)
- [Triển khai bằng Docker Compose](deploy-compose.md)

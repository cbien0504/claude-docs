---
title: Triển khai MCP tunnels bằng Docker Compose (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/deploy-compose
description: Cài đặt MCP tunnel stack trên một máy ảo bằng Docker Compose.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/deploy-compose). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Hướng dẫn triển khai tunnel stack dưới dạng các container được gia cố (hardened) trên một host duy nhất; cùng cấu hình có thể nhân bản trên nhiều host để tăng tính sẵn sàng. Đây là một cách tham chiếu dùng Docker Compose, bạn chịu trách nhiệm điều chỉnh cho phù hợp yêu cầu bảo mật của tổ chức. MCP tunnels đang ở dạng research preview.

## Các điểm chính

Điều kiện cần có:
- **Một tunnel:** với truy cập theo chương trình, thành phần setup tự tạo nếu bạn không cung cấp tunnel ID; muốn gắn vào tunnel có sẵn thì tạo trong Claude Console.
- **Cách để host xác thực với Tunnels API:**
  - *Truy cập theo chương trình (khuyến nghị):* bật **Set up programmatic access** khi tạo tunnel để thành phần setup xác thực qua Workload Identity Federation.
  - *Thủ công:* lấy tunnel token từ Console, tự tạo CA và chứng chỉ máy chủ rồi đăng ký CA trong Console.
- **Một host có Docker và Docker Compose**; luồng thủ công cần thêm `openssl` 1.1.1 trở lên.
- **Kết nối outbound** từ host tới `api.anthropic.com` (443 TCP) và tunnel edge (7844 TCP và UDP).
- **Một hoặc nhiều MCP server** chạy và truy cập được từ host tại các địa chỉ bạn cấu hình trong `routes`; nếu chưa có, dùng MCP server mẫu tối giản (tùy chọn).

## Các mục trong trang gốc

Trước khi bắt đầu · Tùy chọn: dùng MCP server mẫu · Cài đặt (có tab cho trường hợp có và không có truy cập theo chương trình) · Xác minh triển khai · Nâng cấp (xoay vòng tunnel token, gia hạn chứng chỉ) · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/deploy-compose)
- [Tổng quan MCP tunnels](overview.md)
- [Kiến trúc và thành phần](concepts.md)
- [Triển khai bằng Helm](deploy-helm.md)

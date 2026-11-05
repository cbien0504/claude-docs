---
title: Tham chiếu MCP tunnels (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/reference
description: Các trường cấu hình proxy, Tunnels REST API, yêu cầu về chứng chỉ và thành phần setup.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/reference). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang tham chiếu cho MCP tunnels (đang ở dạng research preview), gồm cấu hình proxy, Tunnels REST API, yêu cầu chứng chỉ và thành phần setup.

## Các điểm chính

- **Cấu hình proxy:** proxy đọc cấu hình từ `/etc/mcp-gateway/config.yaml` (Compose) hoặc ConfigMap đã dựng (Helm, điền từ `gateway.config.*`). Một số trường chính:

| Trường | Mô tả | Mặc định |
| --- | --- | --- |
| `listen_addr` | Địa chỉ và cổng lắng nghe | Bắt buộc |
| `log_level` | Mức chi tiết của log: `debug`, `info`, `warn` hoặc `error` | `info` |
| `shutdown_timeout` | Thời gian chờ các request đang xử lý khi tắt êm (graceful shutdown) | `30s` |
| `tunnel_domain` | Domain gốc gán cho tunnel; khi đặt, việc tra cứu route sẽ bỏ hậu tố này khỏi hostname đến để khóa của `routes` có thể là subdomain trần (ví dụ `wiki`); khi để trống, khóa của `routes` phải là hostname đầy đủ chính xác | Bắt buộc khi khóa `routes` là subdomain trần |
| `tls.cert_file` | Đường dẫn tới chứng chỉ TLS của máy chủ | Bắt buộc |
| `tls.key_file` | Đường dẫn tới khóa riêng TLS của máy chủ | Bắt buộc |
| `routes` | Ánh xạ từ subdomain hoặc hostname đầy đủ tới URL upstream | — |

## Các mục trong trang gốc

Cấu hình proxy (khớp route) · Tunnels API · Yêu cầu chứng chỉ (chứng chỉ CA, chứng chỉ máy chủ) · Thành phần setup (`setup init`, `setup renew-cert`).

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/mcp-tunnels/reference)
- [Kiến trúc và thành phần](concepts.md)
- [Bảo mật](security.md)

---
title: Claude trên Microsoft Foundry (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/claude-in-microsoft-foundry
description: Truy cập các mô hình Claude qua Microsoft Foundry với endpoint và xác thực theo chuẩn Azure.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/claude-in-microsoft-foundry). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Hướng dẫn thiết lập và gọi API tới Claude trên Microsoft Foundry bằng SDK của Anthropic hoặc HTTP request trực tiếp. Khi truy cập Claude qua Microsoft Foundry, bạn được tính phí sử dụng Claude trong Azure Marketplace. Claude có sẵn ở loại triển khai Global Standard và US Data Zone Standard trong tài nguyên Foundry, tính phí bằng Claude Consumption Units. Anthropic đóng vai trò bên xử lý độc lập (independent processor) cho Microsoft; khách hàng dùng Claude qua Foundry chịu điều khoản sử dụng dữ liệu của Anthropic.

## Các điểm chính

Có hai tùy chọn lưu trữ (hosting), chọn khi cấu hình triển khai:

| | Hosted on Azure | Hosted on Anthropic |
| --- | --- | --- |
| Nơi suy luận chạy | Dịch vụ do Anthropic vận hành, chạy trên hạ tầng Azure | Dịch vụ do Anthropic vận hành, chạy trên hạ tầng của Anthropic |
| Mô hình khả dụng | Các mô hình mới nhất của họ Opus, Sonnet, Haiku | Tất cả mô hình Claude có trên Microsoft Foundry |
| Loại triển khai | Global Standard, US Data Zone Standard | Global Standard |
| Khuyến nghị cho | Đa số workload | Truy cập tính năng hoặc mô hình chưa được lưu trữ trên Azure |

Claude Sonnet 5.5 chỉ hỗ trợ triển khai Global Standard.

## Các mục trong trang gốc

Tùy chọn lưu trữ · Điều kiện tiên quyết · Cài SDK · Cấp phát (tài nguyên Foundry, triển khai Foundry) · Xác thực (API key, Microsoft Entra) · ID request tương quan · Hỗ trợ tính năng (cửa sổ ngữ cảnh, tính năng Claude không hỗ trợ trên Foundry, tính năng không hỗ trợ khi lưu trữ trên Azure) · Phản hồi API · Model ID và triển khai · Thanh toán · Chuyển đổi giữa các tùy chọn lưu trữ · Giám sát và ghi log · Xử lý sự cố (lỗi xác thực, giới hạn tốc độ, lỗi mô hình và triển khai) · Các bước tiếp theo · Tài nguyên bổ sung.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/claude-in-microsoft-foundry)
- [Tổng quan Agent Skills](../agents-and-tools/agent-skills/overview.md)

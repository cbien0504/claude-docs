---
title: Bảo mật triển khai Managed Agents (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/secure-deployment
description: Các cài đặt giới hạn những gì agent của bạn có thể truy cập và làm, theo thứ tự quan trọng giảm dần.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/secure-deployment). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Hướng dẫn liệt kê các cài đặt giới hạn những gì một agent trên Claude Managed Agents có thể truy cập và làm, theo thứ tự quan trọng từ cao xuống thấp. Mỗi mục liên kết tới trang trình bày đầy đủ cài đặt đó.

## Các điểm chính

Bảng đầu trang ghép mỗi mục với cài đặt hoặc quyết định tương ứng:

| Mục | Cài đặt hoặc quyết định |
| --- | --- |
| Chọn nơi agent chạy | Sandbox đám mây hay tự lưu trữ |
| Giới hạn mạng | `networking.type` của environment |
| Giữ credential trong vault | `injection_location` và `networking` trên mỗi environment; cách ứng dụng xác thực với Claude API |

Các mục còn lại trong trang: giới hạn web search và web fetch; phê duyệt hành động rủi ro; cho agent bộ công cụ nhỏ nhất; giữ đầu vào không tin cậy tránh xa công cụ mạnh; đặt giới hạn và cách để dừng.

## Các mục trong trang gốc

Chọn nơi agent chạy · Giới hạn mạng · Giữ credential trong vault · Giới hạn web search và web fetch · Phê duyệt hành động rủi ro · Cho agent bộ công cụ nhỏ nhất · Giữ đầu vào không tin cậy tránh xa công cụ mạnh · Đặt giới hạn và cách để dừng · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/secure-deployment)
- [Rủi ro bảo mật và ranh giới sandbox](secure-deployment-risks.md)
- [Rà soát và giám sát session](secure-deployment-monitoring.md)
- [Permission policies](permission-policies.md)
- [Xác thực bằng vault](vaults.md)

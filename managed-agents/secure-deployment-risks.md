---
title: Rủi ro bảo mật và ranh giới sandbox (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/secure-deployment-risks
description: Vì sao các cài đặt của agent quan trọng đối với bảo mật, và sandbox của Managed Agents làm được và không làm được gì.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/secure-deployment-risks). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang giải thích vì sao các cài đặt trong "Bảo mật triển khai Managed Agents" quan trọng, và sandbox có thể và không thể làm gì.

## Các điểm chính

- **Vì sao quan trọng:**
  - Chỉ dẫn ẩn trong nội dung mà agent đọc có thể điều khiển agent; đây gọi là prompt injection. Claude vốn có khả năng chống chịu, nhưng hành vi của mô hình không phải lớp phòng thủ duy nhất nên cần các cài đặt giới hạn.
  - Claude cũng có thể thực hiện một bước bạn không lường trước khi nó cố hoàn thành tác vụ được giao, chẳng hạn dùng công cụ hay credential nó chạm tới được để vượt chướng ngại. Chính các cài đặt đó giới hạn phạm vi của một bước như vậy, và một người rà soát ngoại tuyến có thể phát hiện.
- **Bảng "điều gì có thể sai":** ví dụ đầu vào không tin cậy điều khiển agent (một ticket yêu cầu agent hủy mọi đơn hàng đang mở) hoặc code trong sandbox dùng credential (một script mà agent bị lừa chạy gửi khóa của agent ra ngoài); mỗi hàng nêu kiểm soát tương ứng.
- **Sandbox làm được và không làm được gì.**

## Các mục trong trang gốc

Vì sao điều này quan trọng · Sandbox làm được và không làm được gì.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/secure-deployment-risks)
- [Bảo mật triển khai](secure-deployment.md)
- [Rà soát và giám sát session](secure-deployment-monitoring.md)

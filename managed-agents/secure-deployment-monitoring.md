---
title: Rà soát và giám sát session của agent (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/secure-deployment-monitoring
description: Tùy chọn rà soát sự kiện của mỗi session bằng một job ngoại tuyến; theo dõi webhook cho các session cần chú ý, và xem Managed Agents lưu giữ gì và trong bao lâu.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/secure-deployment-monitoring). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Bạn có thể tùy chọn rà soát sự kiện của từng session bằng một job ngoại tuyến, theo dõi webhook cho các session cần chú ý, và xóa những session không còn cần. Để giới hạn những gì agent làm được trước khi nó chạy, xem trang "Bảo mật triển khai Managed Agents".

## Các điểm chính

- **Người rà soát ngoại tuyến (offline reviewer):** là một job bạn chạy, tách biệt khỏi các session nó rà soát, đọc sự kiện của từng session sau khi chúng được ghi. Vì session dài có quá nhiều sự kiện để con người đọc, job này dùng Claude để đọc; việc rà soát đánh dấu những hành vi vượt ngoài phạm vi tác vụ.
- **Giám sát session và xem lại việc lưu giữ:** đăng ký các webhook cho biết khi nào một session cần chú ý, và xóa session không còn cần; xác minh chữ ký ở mỗi lần gửi. Bảng "cần theo dõi gì, xem ở đâu" gồm:
  - Session chuyển sang idle (ví dụ chờ phê duyệt): webhook `session.status_idled`.
  - Session đạt ngân sách hoặc kết thúc: các webhook `session.budget_reached` và `session.status_terminated`.
  - Lần chạy theo lịch không khởi động được session: các webhook `deployment_run.failed` và `deployment.paused`.
  - Credential OAuth của MCP không làm mới được: webhook `vault_credential.refresh_failed`.

## Các mục trong trang gốc

Tùy chọn dùng người rà soát ngoại tuyến đọc mọi bản ghi · Giám sát session và xem lại việc lưu giữ.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/secure-deployment-monitoring)
- [Bảo mật triển khai](secure-deployment.md)
- [Đăng ký webhook](webhooks.md)
- [Session operations](session-operations.md)

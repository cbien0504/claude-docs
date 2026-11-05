---
title: Scheduled deployments (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/scheduled-deployments
description: Tạo và quản lý deployment bằng Claude API: chạy agent theo lịch cron định kỳ và xem lịch sử chạy.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/scheduled-deployments). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Một **scheduled deployment** cho phép một agent tự động bắt đầu các session, để agent hoàn thành tác vụ theo nhịp có thể dự đoán.

## Các điểm chính

- **Tạo scheduled deployment:** ngoài `schedule`, bạn truyền các cấu hình session cần cho việc thực thi. Deployment cần cấu hình agent và cấu hình environment, và tùy chọn nhận file. Deployment cũng cần ít nhất một sự kiện ban đầu, `user.message` hoặc `user.define_outcome`, để khởi động công việc của mỗi session; trong file deployment cho `ant apply`, phần văn bản bên dưới frontmatter trở thành `user.message` đó.
- **Ngữ nghĩa cron và múi giờ**, và **đặt ngân sách cho mỗi lần chạy.**
- **Các lần chạy deployment (deployment runs)**, quản lý vòng đời deployment (gồm hành vi khi lỗi) và **kích hoạt chạy thủ công.**
- Webhook liên quan: `deployment_run.failed` và `deployment.paused`.

## Các mục trong trang gốc

Tạo scheduled deployment (ngữ nghĩa cron và múi giờ, đặt ngân sách cho mỗi lần chạy) · Các lần chạy deployment · Quản lý vòng đời deployment (hành vi khi lỗi) · Kích hoạt chạy thủ công · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/scheduled-deployments)
- [Thiết lập agent](agent-setup.md)
- [Bắt đầu một session](sessions.md)
- [Session budgets](budgets.md)
- [Đăng ký webhook](webhooks.md)

---
title: Session budgets (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/budgets
description: Giới hạn chi tiêu của một session bằng ngân sách đô la cứng, được thực thi theo giá niêm yết công khai.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/budgets). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Session budget là một trần chi tiêu cứng, tùy chọn, bạn đặt khi tạo session. Nền nảng liên tục tính giá mọi thứ session tiêu thụ theo giá niêm yết công khai (gọi là chi phí niêm yết, list cost của session) và áp trần đó.

## Các điểm chính

- **Đặt ngân sách khi tạo session;** cách đo chi phí niêm yết.
- **Khi session chạm ngân sách:** các sự kiện được chấp nhận tại mức trần; có thể **tiếp tục session ở mức ngân sách** bằng cách thay đổi hoặc gỡ ngân sách.
- **Theo dõi chi tiêu;** ngân sách trong session multiagent (một trần chung cho mọi thread, các thread tạm dừng độc lập khi chạm trần); ngân sách trên deployment; mô hình không có giá niêm yết; tham chiếu lỗi.
- Webhook liên quan: `session.budget_reached`.

## Các mục trong trang gốc

Đặt ngân sách khi tạo session · Cách đo chi phí niêm yết · Khi session chạm ngân sách (sự kiện được chấp nhận tại trần) · Tiếp tục session ở mức ngân sách (đổi ngân sách, gỡ ngân sách) · Theo dõi chi tiêu · Ngân sách trong session multiagent · Ngân sách trên deployment · Mô hình không có giá niêm yết · Tham chiếu lỗi · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/budgets)
- [Kiểm tra session và theo dõi mức sử dụng](session-observability.md)
- [Scheduled deployments](scheduled-deployments.md)
- [Session operations](session-operations.md)

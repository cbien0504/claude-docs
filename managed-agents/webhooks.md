---
title: Đăng ký webhook (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/webhooks
description: Nhận thông báo khi có các sự kiện quan trọng xảy ra mà không cần thăm dò.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/webhooks). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Session là các tương tác chạy dài. Dù phần lớn tương tác thời gian thực diễn ra qua luồng sự kiện SSE, webhook thông báo cho bạn về các thay đổi trạng thái lớn. Sự kiện webhook chỉ trả về `type` và `id` của sự kiện chứ không phải toàn bộ đối tượng; khi nhận sự kiện, bạn cần lấy đối tượng trực tiếp bằng lệnh `GET`. Cách này tránh giao dữ liệu cũ khi thử lại và giữ mỗi lần gửi nhỏ gọn.

## Các điểm chính

- **Các loại sự kiện được hỗ trợ:** chia theo tab (ví dụ sự kiện session). Một số sự kiện có tên khác với sự kiện tương ứng trên luồng sự kiện của session (ví dụ `session.status_idle` và `session.status_running` của stream khác với webhook). Ví dụ: `session.status_run_started` kích hoạt khi agent bắt đầu chạy, ở mỗi lần session chuyển sang `running`.
- **Quy trình:** đăng ký endpoint; xác minh chữ ký của mỗi lần gửi; xử lý sự kiện; hành vi gửi (delivery behavior).

## Các mục trong trang gốc

Các loại sự kiện được hỗ trợ · Đăng ký endpoint · Xác minh chữ ký · Xử lý sự kiện · Hành vi gửi · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/webhooks)
- [Session event stream](events-and-streaming.md)
- [Rà soát và giám sát session](secure-deployment-monitoring.md)

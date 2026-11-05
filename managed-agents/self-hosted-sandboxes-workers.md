---
title: Triển khai worker tự lưu trữ (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-workers
description: Chọn cách các worker của sandbox tự lưu trữ nhận việc và nơi các session chạy: luôn bật hoặc kích hoạt bằng webhook, trong một tiến trình hoặc một sandbox cho mỗi session.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-workers). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Quickstart chạy một worker CLI `ant` thăm dò liên tục và chạy mọi session trong một tiến trình. Trang này nói về những cách khác để chạy worker và cách chọn giữa chúng. Khi triển khai worker, bạn cần đưa ra hai lựa chọn: worker nhận việc bằng cách nào, và mỗi session chạy ở đâu.

## Các điểm chính

- **Các mẫu triển khai:**
  - Chạy một worker luôn bật (always-on).
  - Kích hoạt worker từ webhook.
  - Chạy một sandbox cho mỗi session: chuyển tiếp secret của work item; khởi chạy sandbox từ SDK poller; chạy SDK worker bên trong sandbox.
- **Chuẩn bị file cho session** (staging file).

## Các mục trong trang gốc

Chọn mẫu triển khai · Chạy worker luôn bật · Kích hoạt worker từ webhook · Chạy một sandbox cho mỗi session · Chuẩn bị file cho session · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-workers)
- [Sandbox tự lưu trữ – tổng quan và quickstart](self-hosted-sandboxes.md)
- [Đăng ký webhook](webhooks.md)
- [Giám sát và xử lý sự cố](self-hosted-sandboxes-operations.md)

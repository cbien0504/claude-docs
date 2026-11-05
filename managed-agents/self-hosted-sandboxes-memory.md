---
title: Memory stores trong sandbox tự lưu trữ (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-memory
description: Gắn memory store vào các session Claude Managed Agents chạy trong sandbox tự lưu trữ: chuẩn bị host, cấu hình đồng bộ, xử lý store chỉ đọc và xung đột.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-memory). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Các session trên environment tự lưu trữ gắn memory store giống hệt các session trên môi trường đám mây: liệt kê chúng trong `resources` khi tạo session. Khác biệt là ai hiện thực hóa (materialize) store: trên environment tự lưu trữ, worker của bạn (chứ không phải hạ tầng của Anthropic) tải từng store vào sandbox và đồng bộ các thay đổi của agent trở lại.

## Các điểm chính

Yêu cầu:
- **Worker có mount memory store:** dùng CLI `ant` phiên bản 1.33.0 trở lên, hoặc `EnvironmentWorker` từ SDK Python, TypeScript hoặc Go.
- **Hệ thống file POSIX:** không hỗ trợ host Windows vì worker cần `O_NOFOLLOW` khi mở file bộ nhớ. Nên dùng hệ thống file phân biệt hoa thường để các đường dẫn bộ nhớ chỉ khác nhau về chữ hoa/thường không đụng nhau (các volume macOS mặc định không phân biệt).
- **Thư mục `/mnt/memory` có thể ghi.**
- **Secret của work item:** nếu code của bạn tự khởi chạy worker, hãy chuyển tiếp secret của work item cho worker.

Trang cũng nói về chuẩn bị host (kể cả macOS và cách cô lập các session dùng chung một store), cách worker xử lý bộ nhớ, cấu hình đồng bộ (khoảng thời gian đồng bộ, xóa), store chỉ đọc và xung đột, và xử lý sự cố.

## Các mục trong trang gốc

Yêu cầu · Chuẩn bị host (macOS, cô lập các session dùng chung store) · Cách worker xử lý bộ nhớ · Cấu hình đồng bộ (khoảng thời gian, xóa) · Store chỉ đọc và xung đột · Xử lý sự cố.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-memory)
- [Memory stores](memory.md)
- [Triển khai worker](self-hosted-sandboxes-workers.md)

---
title: Kiểm tra session và theo dõi mức sử dụng (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/session-observability
description: Kiểm tra một session trong Claude Console, đọc mức sử dụng token và chi phí theo bảng giá, và gỡ lỗi hành vi bất ngờ của agent.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/session-observability). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Dùng trình xem session (session viewer) trong Claude Console để kiểm tra agent đã làm gì trong một session mà không cần viết code. Dùng các tổng `usage` của session để biết công việc đó đã tiêu tốn bao nhiêu.

## Các điểm chính

- **Kiểm tra session trong Console:** trình xem session chỉ dành cho Developer và Admin. Mở trang Sessions trong Claude Console; danh sách hiện mọi session trong workspace cùng trạng thái. Trình xem hiển thị, chẳng hạn, một **minimap dòng thời gian** có thể phóng to về hoạt động của session theo thời gian, mỗi thread trong các session multiagent có một làn riêng.
- **Theo dõi mức sử dụng:** mức dùng theo từng thread, đọc mức dùng từ stream, áp giới hạn chi tiêu, và tìm mức dùng của session trong toàn tổ chức.
- **Mẹo gỡ lỗi.**

## Các mục trong trang gốc

Kiểm tra session trong Console · Theo dõi mức sử dụng (theo từng thread, đọc từ stream, áp giới hạn chi tiêu, tìm mức dùng toàn tổ chức) · Mẹo gỡ lỗi · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/session-observability)
- [Session threads](session-threads.md)
- [Session budgets](budgets.md)
- [Session event stream](events-and-streaming.md)

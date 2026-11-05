---
title: Giới hạn domain của web search và web fetch (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/tools-web-restrictions
description: Kiểm soát những trang web mà công cụ web search và web fetch của agent có thể truy cập, giới hạn nội dung được tải về và bản địa hóa kết quả tìm kiếm.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/tools-web-restrictions). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang mô tả cách đặt danh sách domain cho công cụ `web_search` và `web_fetch` của một agent, giới hạn lượng nội dung tải về và bản địa hóa kết quả tìm kiếm. Cách dùng khác nhau theo sản phẩm; trang cũng chỉ ra khác biệt so với các công cụ tương ứng trong Messages API.

## Các điểm chính

- **Đặt danh sách domain trên agent** và các cài đặt đi kèm.
- **Khi một domain không được phép:** mô tả hành vi.
- **Quy tắc của danh sách domain:** domain trong danh sách khớp với những gì, định dạng domain, hậu tố đường dẫn cho các domain của web search.
- **Lỗi xác thực**, kể cả trường hợp một cài đặt từng được chấp nhận nay không còn hợp lệ.
- **Session multiagent và session hướng outcome;** **đổi danh sách giữa session.**

## Các mục trong trang gốc

Đặt danh sách domain trên agent · Cài đặt · Khi domain không được phép · Quy tắc danh sách domain · Lỗi xác thực · Session multiagent và hướng outcome · Đổi danh sách giữa session · Khác biệt so với công cụ Messages API · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/tools-web-restrictions)
- [Công cụ](tools.md)
- [Bảo mật triển khai](secure-deployment.md)
- [Web search tool](../agents-and-tools/tool-use/web-search-tool.md)

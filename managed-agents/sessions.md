---
title: Bắt đầu một session (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/sessions
description: Tạo một session để chạy agent của bạn và bắt đầu thực hiện tác vụ.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/sessions). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Session là một thực thể agent trong một environment. Mỗi session tham chiếu một agent và một environment (cả hai tạo riêng trước đó).

## Các điểm chính

- **Tạo session:** cần ID của `agent` và ID của `environment`. Agent là tài nguyên có phiên bản; truyền ID `agent` dưới dạng chuỗi sẽ tạo session với phiên bản agent mới nhất. Để ghim session vào một phiên bản agent cụ thể, truyền một đối tượng; cách này cho phép kiểm soát chính xác phiên bản nào chạy và triển khai dần các phiên bản mới một cách độc lập.
- **Gieo (seed) session bằng sự kiện ban đầu:** `initial_events` là mảng tùy chọn các sự kiện ban đầu gửi tới session, cho phép tạo session và bắt đầu công việc trong một lệnh gọi. Chúng không được lặp lại trong phản hồi tạo; muốn thấy tin nhắn đã gieo, hãy liệt kê sự kiện của session. Không chấp nhận loại sự kiện nào khác: các sự kiện trả lời một lượt của agent (`user.tool_confirmation`, `user.tool_result`, `user.custom_tool_result`) không được chấp nhận vì chưa có lượt agent nào, và `user.interrupt` cũng không.
- **Ghi đè cấu hình agent cho session;** ghim vị trí suy luận (inference geo) cho session; đặt ngân sách session.
- **Xác thực MCP qua vault** và **bắt đầu session.**

## Các mục trong trang gốc

Tạo session (gieo bằng sự kiện ban đầu, ghi đè cấu hình agent, ghim inference geo, đặt ngân sách) · Xác thực MCP qua vault · Bắt đầu session · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/sessions)
- [Thiết lập agent](agent-setup.md)
- [Cài đặt môi trường đám mây](environments.md)
- [Session operations](session-operations.md)
- [Session event stream](events-and-streaming.md)

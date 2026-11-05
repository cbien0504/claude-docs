---
title: Session event stream (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/events-and-streaming
description: Gửi sự kiện, stream phản hồi, và ngắt hoặc chuyển hướng session trong khi nó đang chạy.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/events-and-streaming). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Giao tiếp với Claude Managed Agents dựa trên sự kiện (event-based). Bạn mở một stream để theo dõi session, gửi sự kiện để điều khiển nó, và trả lời khi nó tạm dừng chờ đầu vào.

## Các điểm chính

- **Stream sự kiện** và cách **kết nối lại mà không bỏ lỡ sự kiện.**
- **Gửi sự kiện** và **phản hồi khi session chuyển sang idle.**
- **Trả lời các lệnh gọi công cụ làm tạm dừng session:** trả kết quả công cụ tùy chỉnh và xác nhận một lệnh gọi công cụ.
- **Tiếp tục một session idle** và **ngắt agent.**
- **Liệt kê các sự kiện đã qua.**
- **Gửi system message:** mô hình được hỗ trợ và hành vi khi có lệnh gọi công cụ đang chờ.

## Các mục trong trang gốc

Các loại sự kiện · Stream sự kiện (kết nối lại không bỏ lỡ sự kiện) · Gửi sự kiện · Phản hồi khi session chuyển sang idle · Trả lời lệnh gọi công cụ làm tạm dừng session · Tiếp tục session idle · Ngắt agent · Liệt kê sự kiện đã qua · Gửi system message · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/events-and-streaming)
- [Xem trước phản hồi bằng event delta](event-deltas.md)
- [Tham chiếu](reference.md)
- [Bắt đầu một session](sessions.md)

---
title: Xem trước phản hồi bằng event delta (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/event-deltas
description: Hiển thị văn bản phản hồi của agent dưới dạng bản xem trước trực tiếp trong khi mô hình vẫn đang sinh nội dung.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/event-deltas). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Theo mặc định, văn bản phản hồi của agent đến luồng sự kiện của session dưới dạng các sự kiện `agent.message` đã được đệm; mỗi sự kiện chỉ được phát ra sau khi request mô hình tạo ra nó hoàn tất. Bản xem trước (preview) là công cụ hỗ trợ hiển thị theo nỗ lực tốt nhất (best-effort), còn sự kiện `agent.message` đã đệm luôn là bản ghi có thẩm quyền. Một client bỏ qua preview vẫn nhận được luồng đầy đủ và chính xác.

## Các điểm chính

- **Chọn tham gia preview:** theo từng kết nối stream. Thêm tham số truy vấn `event_deltas[]` vào stream bạn đang đọc, lặp lại một lần cho mỗi loại sự kiện muốn xem trước. Các giá trị được chấp nhận là `agent.message` và `agent.thinking`; giá trị khác bị từ chối. Cả hai endpoint stream đều nhận tham số này.
- **Cộng dồn và đối chiếu:** có các helper accumulator trong SDK.
- **Xem trước sự kiện của session thread.**
- **Hạn chế** và **xử lý sự cố preview.**

## Các mục trong trang gốc

Chọn tham gia preview (các sự kiện preview) · Cộng dồn và đối chiếu (helper accumulator của SDK) · Xem trước sự kiện của session thread · Hạn chế · Xử lý sự cố preview · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/event-deltas)
- [Session event stream](events-and-streaming.md)
- [Tham chiếu](reference.md)

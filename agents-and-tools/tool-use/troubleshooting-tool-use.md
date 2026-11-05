---
title: Xử lý sự cố tool use (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/troubleshooting-tool-use
description: Sửa các lỗi tool use phổ biến nhất bằng bảng chẩn đoán từ triệu chứng đến cách khắc phục.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/troubleshooting-tool-use). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Các bảng "triệu chứng → cách sửa" cho những lỗi tool use phổ biến nhất. Mỗi cách sửa đều tham chiếu chéo tới trang sở hữu tính năng liên quan.

## Các điểm chính

- **Claude gọi sai công cụ:**
  - Claude gọi công cụ A trong khi bạn muốn B: do mô tả mơ hồ; hãy làm rõ mô tả, phân biệt công cụ theo KHI NÀO dùng chứ không chỉ theo việc nó LÀM GÌ.
  - Claude không bao giờ gọi công cụ của bạn: có thể do trùng tên công cụ hoặc schema quá chung chung; kiểm tra tên trùng và thêm `input_examples` để cụ thể hóa cách dùng.
  - Claude gọi với sai kiểu tham số: do schema mơ hồ; thêm `strict: true` (nếu schema nằm trong tập con được hỗ trợ) hoặc thêm `input_examples`.
- **Các nhóm sự cố khác:** Claude tự bịa tham số công cụ; parallel tool call không hoạt động; cache liên tục bị mất hiệu lực; lỗi ở thời điểm request; lỗi "thinking blocks cannot be modified"; Claude đánh dấu kết quả công cụ là prompt injection; khác biệt về escape JSON giữa các phiên bản mô hình.

## Các mục trong trang gốc

Claude gọi sai công cụ · Claude bịa tham số công cụ · Gọi công cụ song song không hoạt động · Cache liên tục mất hiệu lực · Lỗi ở thời điểm request · Lỗi thinking block không được sửa · Claude gắn cờ kết quả công cụ là prompt injection · Khác biệt escape JSON giữa các phiên bản mô hình · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/troubleshooting-tool-use)
- [Định nghĩa công cụ](define-tools.md)
- [Parallel tool use](parallel-tool-use.md)
- [Strict tool use](strict-tool-use.md)

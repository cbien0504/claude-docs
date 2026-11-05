---
title: Tọa độ và bounding box (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/vision-coordinates
description: Cách Claude thay đổi kích thước ảnh, và cách làm việc với tọa độ pixel mà Claude trả về cho bounding box, điểm và thành phần giao diện.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/vision-coordinates). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Claude có thể xác định và gắn nhãn các vùng của một bức ảnh (ví dụ trả về bounding box cho bảng, trường biểu mẫu, thành phần biểu đồ hoặc thành phần giao diện). Hướng dẫn này nói về cách Claude thay đổi kích thước ảnh trước khi xử lý và cách làm việc với tọa độ pixel nó trả về, để các hộp và điểm khớp đúng với ảnh gốc. Cần dùng cho pipeline OCR, trích xuất biểu mẫu, phân tích biểu đồ, định vị thành phần UI và mọi tác vụ thao tác trên một vùng cụ thể của ảnh.

## Các điểm chính

- **Dùng tọa độ pixel tuyệt đối:** Claude hoạt động tốt nhất với tọa độ pixel tuyệt đối; hãy yêu cầu rõ trong prompt, ví dụ trả về bounding box của mỗi bảng dưới dạng `[x1, y1, x2, y2]` (góc trên trái và góc dưới phải). Claude làm việc không tốt khi được yêu cầu dùng tọa độ chuẩn hóa.
- **Quy ước:** gốc `(0, 0)` ở góc trên trái, x tăng sang phải, y tăng xuống dưới. Tọa độ là vị trí pixel trong ảnh mà Claude xử lý, tức ảnh của bạn sau khi Claude đã thay đổi kích thước cho vừa mô hình.
- **Giới hạn:** khả năng suy luận không gian của Claude có giới hạn; độ chính xác tốt nhất khi bạn nêu định dạng tọa độ mong đợi trong prompt và kiểm tra thủ công một số kết quả bằng mắt trước khi xử lý quy mô lớn.

## Các mục trong trang gốc

Cách Claude thay đổi kích thước và đệm ảnh · Thay đổi kích thước ảnh trước khi tải lên · Biến việc resize thành lỗi bằng `transformations` · Chia lại tỷ lệ tọa độ khi không thể resize trước · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/vision-coordinates)
- [Vision](vision.md)

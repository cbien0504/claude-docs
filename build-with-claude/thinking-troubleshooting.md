---
title: Xử lý sự cố thinking (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/thinking-troubleshooting
description: Chẩn đoán và sửa các lỗi thinking phổ biến nhất: lỗi 400 do cấu hình, thinking block rỗng hoặc thiếu, dừng do max_tokens và trượt cache.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/thinking-troubleshooting). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang này giúp chẩn đoán và sửa các sự cố thinking phổ biến nhất. Mỗi mục ứng với một triệu chứng cụ thể; về việc zero data retention (ZDR) áp dụng thế nào cho tính năng này, xem trang API và lưu giữ dữ liệu.

## Các điểm chính

- **Bảng hỗ trợ theo mô hình:** hỗ trợ thinking, giá trị mặc định và các cấu hình bị từ chối theo từng mô hình.
- **Các lỗi 400 thường gặp:** thông báo `thinking.type.enabled` không được hỗ trợ; lỗi sau khi gửi `thinking: {type: "disabled"}`; thông báo `thinking.type.between_tools` không được hỗ trợ; mức effort không được hỗ trợ khi thinking bị tắt; không thể đổi effort khi thinking bị tắt; adaptive thinking không được hỗ trợ; thinking block không được sửa đổi; chữ ký của thinking block không hợp lệ.
- **Hành vi bất thường khác:** trường thinking rỗng trong phản hồi; không có thinking block ở một số lượt; lệnh gọi công cụ hoặc thẻ XML xuất hiện trong văn bản đầu ra; phản hồi dừng với `stop_reason: "max_tokens"`; tỷ lệ trúng cache giảm sau khi đổi cài đặt thinking; đặt effort mà thinking không thay đổi.

## Các mục trong trang gốc

Hỗ trợ thinking, giá trị mặc định và cấu hình bị từ chối theo mô hình · các mục theo từng triệu chứng nêu trên · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/thinking-troubleshooting)
- [Thinking – tổng quan](thinking.md)
- [Điều hướng thinking](thinking-steering-and-cost.md)
- [Effort](effort.md)

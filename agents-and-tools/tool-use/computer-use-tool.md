---
title: Computer use tool (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/computer-use-tool
description: Cho Claude quyền điều khiển ảnh chụp màn hình, chuột và bàn phím của một môi trường desktop bằng computer use tool, client toolset computer_toolset_20260801.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/computer-use-tool). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Computer use tool cho Claude khả năng chụp màn hình, điều khiển chuột và bàn phím của một môi trường desktop. Đây là client toolset `computer_toolset_20260801` do Anthropic định nghĩa: ứng dụng của bạn chạy các hành động và gửi kết quả (kể cả ảnh chụp màn hình) về cho Claude trong một vòng lặp agent.

## Các điểm chính

- **Bảo mật:** trang mở đầu bằng phần cân nhắc bảo mật; cần đọc trước khi triển khai vì Claude hành động trên một môi trường thật.
- **Cách hoạt động:** Claude đề xuất các hành động (có thể theo lô), ứng dụng thực thi trong "môi trường tính toán" (computing environment) rồi trả kết quả.
- **Cách triển khai:** hiểu vòng lặp agent; tối ưu hiệu năng mô hình bằng prompt và system prompt; các hành động khả dụng và tham số công cụ; kết hợp với thinking; bổ sung bằng các công cụ khác; xây dựng môi trường computer use tùy chỉnh; xử lý lỗi; điều chỉnh kích thước ảnh chụp cho vừa giới hạn ảnh; quản lý lịch sử ảnh chụp; chẩn đoán lỗi click; thực hành tốt khi triển khai.
- **Di chuyển và phiên bản cũ:** có hướng dẫn chuyển từ `computer_20251124` và mô tả các phiên bản công cụ trước đó.

## Các mục trong trang gốc

Cân nhắc bảo mật · Quick start · Cách computer use hoạt động (thao tác theo lô, môi trường tính toán) · Cách triển khai computer use · Di chuyển từ `computer_20251124` · Các phiên bản công cụ trước · Hạn chế · Lưu giữ dữ liệu · Giá · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/computer-use-tool)
- [Browser use tool](browser-use-tool.md)
- [Browser và computer use với bộ công cụ SDK](browser-use-sdk.md)
- [Tham chiếu công cụ](tool-reference.md)

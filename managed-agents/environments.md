---
title: Cài đặt môi trường đám mây (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/environments
description: Tùy biến sandbox đám mây cho các session của bạn.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/environments). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Environment định nghĩa cấu hình sandbox nơi agent của bạn chạy. Bạn tạo environment một lần, rồi tham chiếu ID của nó mỗi khi bắt đầu một session. Nhiều session có thể dùng chung một environment, nhưng mỗi session có sandbox cô lập riêng. Trang này nói về environment kiểu `type: cloud`; để chạy sandbox trên hạ tầng của bạn, xem trang sandbox tự lưu trữ.

## Các điểm chính

- **Tạo và dùng:** tạo environment rồi dùng nó trong session.
- **Tùy chọn cấu hình:** gói (packages) và mạng (networking), gồm mục về các host của trình quản lý gói và rủi ro của mạng không hạn chế.
- **Vòng đời environment** và **quản lý environment.**
- **Runtime cài sẵn.**

## Các mục trong trang gốc

Tạo environment · Dùng environment trong session · Tùy chọn cấu hình (gói, mạng: host của trình quản lý gói, rủi ro của mạng không hạn chế) · Vòng đời environment · Quản lý environment · Runtime cài sẵn · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/environments)
- [Chọn môi trường cho agent](choosing-an-environment.md)
- [Tham chiếu sandbox đám mây](cloud-sandboxes-reference.md)
- [Bắt đầu một session](sessions.md)

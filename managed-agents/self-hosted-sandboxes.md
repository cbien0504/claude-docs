---
title: Sandbox tự lưu trữ – tổng quan và quickstart (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes
description: Chạy các session Claude Managed Agents trong sandbox tự lưu trữ, giữ việc thực thi công cụ, file và egress mạng trong hạ tầng của riêng bạn.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Sandbox tự lưu trữ chuyển việc thực thi công cụ của agent từ sandbox đám mây do Anthropic quản lý sang hạ tầng do bạn kiểm soát, trong khi Anthropic vẫn tiếp tục chạy agent. Để hiểu điều đó nghĩa là gì và quyết định có phù hợp với agent của bạn không, xem trang chọn môi trường cho agent.

## Các điểm chính

- **Cách hoạt động:** một environment `self_hosted` đóng vai trò hàng đợi công việc. Bạn chạy một **environment worker**, tiến trình trên hạ tầng của bạn phục vụ hàng đợi đó:
  1. Bạn tạo một session nhắm tới environment; Anthropic đưa session vào hàng đợi như một work item.
  2. Worker của bạn nhận work item và tải về các skill của agent cùng các memory store của session.
  3. Phần còn lại của vòng đời do worker xử lý (xem trang gốc).
- Trang gốc có quickstart (điều kiện tiên quyết, chạy session đầu tiên), tài nguyên của session, quan hệ giữa sandbox tự lưu trữ và MCP tunnels, các hướng dẫn theo nền tảng và các bước tiếp theo.

## Các mục trong trang gốc

Cách hoạt động · Quickstart (điều kiện tiên quyết, chạy session đầu tiên) · Tài nguyên session · Sandbox tự lưu trữ và MCP tunnels · Hướng dẫn theo nền tảng · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes)
- [Chọn môi trường cho agent](choosing-an-environment.md)
- [Triển khai worker](self-hosted-sandboxes-workers.md)
- [Mô hình bảo mật](self-hosted-sandboxes-security.md)
- [Tham chiếu worker](self-hosted-sandboxes-reference.md)

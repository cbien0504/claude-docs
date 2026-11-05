---
title: Bắt đầu với Claude (tóm tắt)
source: https://platform.claude.com/docs/en/get-started
description: Thực hiện lệnh gọi API đầu tiên tới Claude và xây dựng một trợ lý tìm kiếm web đơn giản.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/get-started). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang quickstart hướng dẫn bạn thiết lập tài khoản, xác thực và gửi lệnh gọi Messages API đầu tiên tới Claude. Trang gốc có ví dụ cho CLI, cURL, Python, TypeScript, C#, Go, Java, PHP và Ruby.

## Các điểm chính

- **Trước khi bắt đầu:** đăng ký hoặc đăng nhập tài khoản Claude Console. Có hai cách xác thực:
  - **CLI (khuyến nghị cho phát triển cục bộ):** cài CLI (`ant`), đăng nhập, rồi các SDK và CLI tự nhận thông tin xác thực. Trên Linux có thể tải binary phát hành trực tiếp, hoặc cài từ mã nguồn bằng `go install` (cần Go 1.25 trở lên; binary nằm ở `$(go env GOPATH)/bin`).
  - **API key:** tạo API key trong Claude Console; SDK và CLI đọc khóa từ biến môi trường `ANTHROPIC_API_KEY`.
- **Gọi API:**
  - Bằng CLI sign-in: gửi `POST` tới Messages API với access token từ lần đăng nhập CLI làm bearer token.
  - Bằng API key: gửi `POST` tới Messages API; Claude trả về JSON chứa tin nhắn của assistant.
  - Cũng có thể chạy `ant messages create` từ terminal; CLI in ra phản hồi JSON.
  - Với SDK: tạo file (ví dụ `quickstart.py`, `quickstart.ts`, `main.go`, `QuickStart.java`, `quickstart.php`, `quickstart.rb`), hoặc dự án console cho C#, rồi chạy. Java cần JDK 25 trở lên cùng Gradle hoặc Maven.
- **Bước tiếp theo:** học các mẫu cốt lõi của Messages API (hội thoại nhiều lượt, system prompt, stop reason), so sánh các mô hình theo khả năng và chi phí, duyệt toàn bộ khả năng của Claude (công cụ, quản lý ngữ cảnh, structured outputs…), xem tài liệu thư viện client, và xem phần xác thực (so sánh API key với Workload Identity Federation, đặt thời hạn khóa).

## Các mục trong trang gốc

Trước khi bắt đầu · Gọi API · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/get-started)
- [Sử dụng Messages API](build-with-claude/working-with-messages.md)
- [Tổng quan tính năng](build-with-claude/overview.md)
- [Xác thực](manage-claude/authentication.md)

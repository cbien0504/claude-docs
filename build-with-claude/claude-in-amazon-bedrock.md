---
title: Claude trên Amazon Bedrock – Opus 4.7 trở lên (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/claude-in-amazon-bedrock
description: Truy cập các mô hình Claude qua Amazon Bedrock với xác thực, thanh toán và ranh giới bảo mật theo chuẩn AWS.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/claude-in-amazon-bedrock). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Hướng dẫn thiết lập và gọi API tới Claude trên Amazon Bedrock. Dịch vụ chạy trên hạ tầng do AWS quản lý với "zero operator access" (nhân sự Anthropic không có quyền truy cập hạ tầng suy luận), cho phép xây dựng ứng dụng nhạy cảm hoàn toàn bên trong ranh giới bảo mật của AWS. Trang này nói về tích hợp phục vụ Claude qua Messages API tại `/anthropic/v1/messages`; tích hợp Bedrock trước đây (các API `InvokeModel` và `Converse` với model ID có phiên bản ARN) vẫn còn và được mô tả ở trang "Claude trên Amazon Bedrock (Opus 4.6 trở xuống)".

## Các điểm chính

- **Quyền truy cập:** Amazon Bedrock đặt tiêu chí truy cập riêng cho từng mô hình Claude. Một số mô hình (như Claude Fable 5.1, Fable 5, Opus 4.8, Sonnet 5, Opus 4.7, Haiku 4.5) mở cho mọi khách hàng Bedrock; với mô hình khác, hãy kiểm tra tiêu chí trong Amazon Bedrock model access.
- **Điều kiện tiên quyết:** tài khoản AWS đã bật Amazon Bedrock model access cho các mô hình Claude định dùng; AWS CLI đã cài và cấu hình (tùy chọn, để quản lý credential).
- **Ba cách xác thực:**
  - **Bedrock service role (khuyến nghị):** quản trị viên AWS tạo service role và cấp cho nhà phát triển quyền `iam:PassRole` trên ARN của role; khi gọi API, Bedrock đảm nhiệm role đó thay bạn.
  - **IAM assumed roles:** truy cập liên kết danh tính với phiên tối đa 12 giờ; role IAM giới hạn theo các mô hình Claude, trust policy nêu nhà cung cấp danh tính (SAML, OIDC hoặc AWS Identity Center).
  - **Bearer token.**

## Các mục trong trang gốc

Quyền truy cập · Điều kiện tiên quyết · Xác thực · Cài SDK · Gửi request đầu tiên · Mô hình được hỗ trợ · Hỗ trợ tính năng (tính năng nổi bật được hỗ trợ, tính năng không hỗ trợ) · Vùng (region) · Hạn mức (quota) · Lưu giữ dữ liệu · Giám sát và ghi log · Hỗ trợ.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/claude-in-amazon-bedrock)
- [Claude trên Amazon Bedrock (Opus 4.6 trở xuống)](claude-on-amazon-bedrock-legacy.md)
- [Claude Platform on AWS](claude-platform-on-aws.md)

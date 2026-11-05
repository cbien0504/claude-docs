---
title: Claude trên Amazon Bedrock – Opus 4.6 trở xuống (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/claude-on-amazon-bedrock-legacy
description: Tích hợp Amazon Bedrock cũ cho các mô hình Claude, dùng API InvokeModel và Converse với model ID có phiên bản ARN.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/claude-on-amazon-bedrock-legacy). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang này nói về tích hợp Amazon Bedrock cũ (legacy): API `InvokeModel` và `Converse` với model ID có phiên bản ARN và mã hóa event-stream của AWS. Với các mô hình có trên endpoint Bedrock dùng Messages API, xem trang "Claude trên Amazon Bedrock (Opus 4.7 trở lên)". Gọi Claude qua Bedrock hơi khác so với gọi trực tiếp Claude API; hướng dẫn dẫn bạn hoàn tất một lệnh gọi bằng SDK client của Anthropic, với giả định bạn đã có tài khoản AWS và cấu hình truy cập theo chương trình.

## Các điểm chính

- **Lưu ý về phiên bản API:** SDK mới nhất mặc định gửi API version `2026-10-21`, kể cả qua Amazon Bedrock. Các mô hình dùng ARN trong bảng của trang này không hỗ trợ `2026-10-21` trên Bedrock và request gửi phiên bản đó tới chúng có thể trả lỗi 400. Nếu gọi qua SDK, hãy giữ SDK ở phiên bản tương ứng; lệnh cài trong mục "Cài SDK để truy cập Bedrock" sẽ cài phiên bản major cuối cùng trước API version `2026-10-21`.
- **Cài và cấu hình AWS CLI:** cần AWS CLI từ phiên bản `2.13.23` trở lên; cấu hình credential bằng lệnh aws configure (hoặc lấy trong "Command line or programmatic access" của bảng điều khiển AWS) và kiểm tra credential hoạt động.
- **SDK:** các SDK client của Anthropic hỗ trợ Bedrock; cũng có thể dùng trực tiếp AWS SDK như `boto3`.

## Các mục trong trang gốc

Cài và cấu hình AWS CLI · Cài SDK để truy cập Bedrock · Truy cập Bedrock (đăng ký mô hình Anthropic, model ID của API, liệt kê mô hình, gửi request, xác thực bằng bearer token) · Ghi log hoạt động · Hỗ trợ tính năng (tính năng nổi bật, tính năng không hỗ trợ, toolset computer use và browser use trên Bedrock, hỗ trợ PDF trên Bedrock, system message giữa hội thoại trên Bedrock, cửa sổ ngữ cảnh) · Endpoint toàn cầu so với theo vùng (khi nào dùng, cách triển khai) · Tài nguyên bổ sung.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/claude-on-amazon-bedrock-legacy)
- [Claude trên Amazon Bedrock (Opus 4.7 trở lên)](claude-in-amazon-bedrock.md)

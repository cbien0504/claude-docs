---
title: Claude Platform on AWS (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/claude-platform-on-aws
description: Truy cập đầy đủ khả năng của nền tảng Claude thông qua AWS với hạ tầng do Anthropic quản lý.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/claude-platform-on-aws). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Claude Platform on AWS cho phép truy cập đầy đủ các khả năng của nền tảng Claude thông qua AWS, trong khi hạ tầng do Anthropic quản lý. Trang này là hướng dẫn dài, bao quát cách tích hợp hoạt động, so sánh với Amazon Bedrock, thiết lập tài khoản, xác thực, các tính năng được hỗ trợ và hướng dẫn chuyển từ Amazon Bedrock sang.

## Các điểm chính

- **Xác thực:** hỗ trợ xác thực SigV4 và API key (kể cả API key ngắn hạn); có quy tắc ưu tiên credential và cách xác định region.
- **Trước khi gọi API:** bật outbound web identity federation và lấy workspace ID.
- **Kết nối riêng:** có thể kết nối qua AWS PrivateLink.
- **Claude Managed Agents** được đề cập trong mục hỗ trợ tính năng (cùng danh sách tính năng không hỗ trợ).
- **Workspace và Console:** phạm vi workspace, quản lý workspace, đăng nhập và các trang có trong Claude Console, chuyển đổi giữa các tổ chức.
- **Chi phí và vận hành:** giới hạn tốc độ và hạn mức, thanh toán và giới hạn chi tiêu, giám sát và ghi log (request ID).
- **Chuyển từ Amazon Bedrock:** nêu những gì thay đổi, những gì bạn có thêm, những gì giữ nguyên, các lỗi dễ gặp khi chuyển và cân nhắc về thương mại.

## Các mục trong trang gốc

Cách tích hợp nền tảng hoạt động · Claude Platform on AWS so với Amazon Bedrock · Thiết lập tài khoản (chuyển từ tổ chức Anthropic hiện có, xử lý sự cố thiết lập) · Trước khi gọi API · Xác thực · Cài SDK · Mô hình khả dụng · Gửi request (cửa sổ ngữ cảnh, kết nối qua AWS PrivateLink) · Hỗ trợ tính năng · Lưu trú dữ liệu · Workspace · Dùng Claude Console · Giới hạn tốc độ và hạn mức · Thanh toán · Giám sát và ghi log · Chuyển từ Amazon Bedrock.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/claude-platform-on-aws)
- [Claude trên Amazon Bedrock (Opus 4.7 trở lên)](claude-in-amazon-bedrock.md)
- [Tổng quan Claude Managed Agents](../managed-agents/overview.md)

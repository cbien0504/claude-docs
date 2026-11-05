---
title: Claude Models on Google Cloud – Anthropic managed (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/claude-models-on-google-cloud/anthropic-managed
description: Claude Models on Google Cloud (Anthropic managed) là Claude API do Anthropic vận hành và truy cập qua dự án Google Cloud của bạn.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/claude-models-on-google-cloud/anthropic-managed). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Google Cloud lo phần quyền truy cập và thanh toán cho Claude Models on Google Cloud (Anthropic managed), còn Claude API do Anthropic vận hành. Các bước thiết lập tạo một tổ chức Anthropic mới cho dự án Google Cloud của bạn, tách biệt với mọi tổ chức Anthropic công ty bạn đã có (kể cả tổ chức Claude Enterprise).

## Các điểm chính

- **Thiết lập tài khoản cần:** quyền mua trong Google Cloud Marketplace trên tài khoản thanh toán; quyền bật dịch vụ trên dự án; và một vai trò IAM cho phép mở Claude Console. Nếu đã có mức chiết khấu, liên hệ đại diện tài khoản của Anthropic hoặc Google Cloud trước khi bắt đầu, vì chiết khấu không áp dụng cho mức sử dụng trong quá khứ.
- **Các bước thiết lập:**
  1. **Đăng ký trên Marketplace:** tìm listing Claude Models on Google Cloud (Anthropic managed), chọn **Subscribe** và hoàn tất mua; quay lại listing và chọn **Manage on Console**.
  2. **Bật các dịch vụ:** trên mọi dự án gọi dịch vụ này, bật hai dịch vụ `claude.googleapis.com` (phục vụ API và định nghĩa quyền IAM; thiếu nó thì lệnh gọi thất bại) và `anthropic-managed-claude.cloudpartnerservices.goog` (dịch vụ Marketplace ghi nhận mức sử dụng của dự án vào gói đăng ký). Chỉ cần bật một lần cho mỗi dự án; kiểm tra bằng `gcloud services list --enabled --project=<project-id>`.
  3. **Thiết lập tổ chức Anthropic:** trên trang Claude chọn **Activate**, nhập email liên hệ, mở liên kết thiết lập được gửi tới email đó, điền tên tổ chức, loại thực thể, quốc gia và mục đích sử dụng, rồi chấp nhận các điều khoản của Anthropic.

## Các mục trong trang gốc

Thiết lập tài khoản (xử lý sự cố thiết lập) · Quản lý quyền truy cập (vai trò IAM, dùng Claude Console, workspace) · Trước khi gọi API (tìm workspace ID, cài SDK) · Gửi request (model ID của API) · Xác định project, location và workspace · Xác thực (thứ tự ưu tiên credential) · Hỗ trợ tính năng (Claude Managed Agents, tính năng không hỗ trợ, cửa sổ ngữ cảnh) · Thanh toán, giới hạn tốc độ và ghi log (giới hạn tốc độ, thanh toán, lưu giữ dữ liệu, giám sát và ghi log, request ID) · Chuyển từ tổ chức Anthropic hiện có · Chuyển từ gói Google managed · Hỗ trợ · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/claude-models-on-google-cloud/anthropic-managed)
- [Tổng quan Claude Models on Google Cloud](overview.md)
- [Google managed](google-managed.md)

---
title: Đính kèm và tải file (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/files
description: Tải file lên và mount chúng trong sandbox để đọc và xử lý.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/files). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Bạn có thể cung cấp file cho agent bằng cách tải chúng lên qua Files API rồi mount vào sandbox của session.

## Các điểm chính

- **Tải file lên:** dùng Files API trước.
- **Mount file vào session:** thêm file vào mảng `resources` khi tạo session. `mount_path` là tùy chọn, nhưng nên đặt tên file mô tả rõ để agent nhận diện được. Ví dụ, với `mount_path` đã cho, agent đọc file tại `/mnt/session/uploads/data.csv`.
- **Bản sao trong session:** một `file_id` mới được tạo để tham chiếu thể hiện của file trong session. Các bản sao này không tính vào giới hạn lưu trữ.
- **Nhiều file:** mount nhiều file bằng cách thêm các mục vào mảng `resources`.
- Trang còn có mục về quản lý file trên session đang chạy, liệt kê và tải file của session, các loại file được hỗ trợ và đường dẫn file.

## Các mục trong trang gốc

Tải file lên · Mount file trong session · Nhiều file · Quản lý file trên session đang chạy · Liệt kê và tải file của session · Các loại file được hỗ trợ · Đường dẫn file.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/files)
- [Files API](../build-with-claude/files.md)
- [Bắt đầu một session](sessions.md)

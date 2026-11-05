---
title: Lấy API key của Claude (tóm tắt)
source: https://platform.claude.com/docs/en/get-api-key
description: Tìm, tạo và quản lý API key cho Claude API trong Claude Console.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/get-api-key). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

API key của Claude API (còn gọi là Anthropic API key) nằm trong Claude Console, tại trang API keys (`platform.claude.com/settings/keys`).

## Các điểm chính

- **Chọn loại khóa:** loại khóa quyết định khóa làm được gì, dùng ở đâu và hết hiệu lực khi nào. **Khóa cá nhân** hoạt động như chính bạn và ngừng hoạt động nếu bạn rời tổ chức. **Khóa service account** đại diện cho một service account. **Khóa workspace** là loại cũ không có chủ sở hữu: thuộc workspace tạo ra nó và vẫn hoạt động sau khi người tạo rời đi. Nên ưu tiên khóa cá nhân hoặc service account vì chúng tự ngừng hoạt động khi tài khoản liên kết bị gỡ.
- **Tạo khóa:**
  1. Đăng nhập Claude Console (hoặc tạo tài khoản).
  2. Mở trang API keys.
  3. Chọn **Create key**, đặt tên, chọn thời hạn (expiration) và đặt **Linked account** là bạn hoặc một service account; có thể chọn workspace.
  4. Sao chép và lưu khóa: khóa đầy đủ (bắt đầu bằng `sk-ant-`) chỉ hiển thị một lần khi tạo; nên lưu ở nơi an toàn như secrets manager. Nếu mất khóa thì không xem lại được, hãy tạo khóa mới.
- Nếu nút **Create key** bị vô hiệu hóa, vai trò của bạn có thể không cho phép tạo khóa; hãy nhờ quản trị viên tổ chức đổi vai trò hoặc tạo khóa service account cho workload của bạn.
- **Dùng khóa:** đặt khóa vào biến môi trường `ANTHROPIC_API_KEY`; SDK client tự đọc biến này. Với HTTP trực tiếp, gửi khóa dưới dạng `Authorization: Bearer <key>`. Nếu khóa không giới hạn theo workspace, bạn cũng phải gửi header `anthropic-workspace-id` trong mỗi request.

## Các mục trong trang gốc

Chọn loại khóa · Tạo API key · Dùng API key · API key và Admin API.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/get-api-key)
- [Xác thực](manage-claude/authentication.md)
- [Bắt đầu với Claude](get-started.md)

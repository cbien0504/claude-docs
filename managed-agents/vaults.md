---
title: Xác thực bằng vault (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/vaults
description: Đăng ký credential theo từng người dùng khi tạo session.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/vaults). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Vault và credential là các thành phần xác thực cho phép bạn đăng ký credential của dịch vụ bên thứ ba một lần và tham chiếu chúng bằng ID khi tạo session. Nhờ đó bạn không phải tự vận hành kho bí mật hay truyền token ở mỗi lệnh gọi. Tham chiếu vault là tham số theo từng session, nên bạn quản lý sản phẩm của mình ở mức tài nguyên `agent` và quản lý người dùng của mình ở mức tài nguyên `session`.

## Các điểm chính

- **Vault** là tập hợp các `credentials` gắn với một người dùng cuối. Bạn đặt `display_name` và có thể gắn `metadata` để ánh xạ về bản ghi người dùng của mình.
- **Phạm vi workspace:** vault và credential thuộc phạm vi workspace, nghĩa là mọi API key có quyền truy cập workspace đều có thể tham chiếu chúng khi tạo session. Để thu hồi quyền truy cập, hãy xóa vault hoặc credential.
- **Các thao tác chính:** tạo vault, thêm credential, tham chiếu vault khi tạo session, xoay vòng credential; trang cũng nêu vòng đời credential (kể cả cách chẩn đoán lỗi làm mới OAuth) và các thao tác khác.
- Có thể tạo vault bằng `ant apply` từ file YAML; lệnh in ra ID và ghi vào `claude-lock.json`.

## Các mục trong trang gốc

Tạo vault · Thêm credential · Tham chiếu vault khi tạo session · Xoay vòng credential · Vòng đời credential (chẩn đoán lỗi làm mới OAuth) · Các thao tác khác · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/vaults)
- [MCP connector](mcp-connector.md)
- [Truy cập GitHub](github.md)
- [Bắt đầu một session](sessions.md)

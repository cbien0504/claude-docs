---
title: Agent Skills trong Managed Agents (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/skills
description: Gắn skill dựng sẵn hoặc tùy chỉnh vào agent trong Claude Managed Agents để cung cấp chuyên môn dựa trên hệ thống file, có thể tái sử dụng, cho các workflow theo lĩnh vực.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/skills). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Skill là tài nguyên dựa trên hệ thống file, có thể tái sử dụng, cho agent chuyên môn theo lĩnh vực: workflow, ngữ cảnh và thực hành tốt biến một agent đa dụng thành chuyên gia. Mỗi skill bạn thêm tốn một chi phí khiêm tốn trên cửa sổ ngữ cảnh của session. Skill tới agent theo hai cách: gắn vào mảng `skills` của agent, hoặc nạp từ một repository GitHub được mount vào session.

## Các điểm chính

- **Skill dựng sẵn của Anthropic:** xử lý tài liệu phổ biến như PowerPoint, Excel, Word và PDF (`pptx`, `xlsx`, `docx`, `pdf`).
- **Skill tùy chỉnh:** skill do bạn viết và tải lên workspace. Một skill tùy chỉnh là một thư mục chứa file `SKILL.md` cùng các file hỗ trợ, tải lên dưới dạng file zip hoặc từng file riêng. Tạo skill trả về ID dạng `skill_*` để tham chiếu khi gắn vào agent. Trường `display_name` là tùy chọn; nếu bỏ qua, tên hiển thị lấy từ trường `name` trong `SKILL.md`.
- **Với `ant apply`:** lệnh tải lên thư mục `skills/pr-summary`, in ID của skill mới và ghi vào `claude-lock.json`; nên commit `claude-lock.json` để lần `ant apply` sau tải lên các chỉnh sửa của bạn.
- **Liệt kê, lấy, xóa và đánh phiên bản skill tùy chỉnh** được nói trong trang hướng dẫn Skills.

## Các mục trong trang gốc

Tạo skill tùy chỉnh · Gắn skill vào agent · Nạp skill từ repository GitHub · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/skills)
- [Tổng quan Agent Skills](../agents-and-tools/agent-skills/overview.md)
- [Thực hành tốt khi viết Skill](../agents-and-tools/agent-skills/best-practices.md)
- [Dùng Agent Skills với API](../build-with-claude/skills-guide.md)
- [Thiết lập agent](agent-setup.md)

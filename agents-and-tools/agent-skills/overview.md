---
title: Agent Skills (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview
description: Agent Skills là các khả năng dạng mô-đun giúp mở rộng chức năng của Claude; mỗi Skill đóng gói hướng dẫn, metadata và tài nguyên tùy chọn mà Claude tự động dùng khi phù hợp.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Skill là tài nguyên có thể tái sử dụng, nằm trên hệ thống file, giúp Claude có chuyên môn theo lĩnh vực: quy trình làm việc, ngữ cảnh và thực hành tốt biến một agent đa dụng thành chuyên gia. Khác với prompt (chỉ dẫn ở cấp hội thoại cho một tác vụ đơn lẻ), Skill được nạp theo nhu cầu nên bạn không phải lặp lại cùng một hướng dẫn qua nhiều cuộc hội thoại.

## Các điểm chính

- **Lợi ích:** chuyên biệt hóa Claude cho tác vụ theo lĩnh vực, giảm lặp lại (tạo một lần, dùng tự động), kết hợp nhiều Skill cho tác vụ phức tạp nhiều bước.
- **Skill dựng sẵn và Skill tùy chỉnh:** Anthropic cung cấp Agent Skills dựng sẵn cho tài liệu PowerPoint, Excel, Word và PDF. Skill tùy chỉnh dùng để đóng gói chuyên môn và kiến thức của tổ chức.
- **Cách dùng theo từng bề mặt:**
  - Messages API: liệt kê `skill_ids` trong tham số `container` và kèm công cụ thực thi code (code execution tool), nơi container chạy các skill.
  - Managed Agents: gắn skill vào mảng `skills` của agent, hoặc nạp từ một repository GitHub được mount vào session.
- **Nơi dùng được:** Claude API, Claude Code và claude.ai. Skill dựng sẵn cũng có trên Claude Platform on AWS và Microsoft Foundry (trên Foundry cần triển khai kiểu "Hosted on Anthropic"). Trên AWS và Foundry, tải Skill tùy chỉnh lên qua Skills API.
- **Nạp thông tin theo từng mức (progressive disclosure):** Claude chạy trong một máy ảo có hệ thống file, Skill là thư mục chứa hướng dẫn, code thực thi và tài liệu tham khảo. Ba mức nội dung được nạp ở các thời điểm khác nhau:
  1. **Mức 1 – Metadata (luôn được nạp):** phần YAML frontmatter (tên và `description`) nằm trong system prompt. `description` là thứ Claude dùng để quyết định có kích hoạt Skill hay không, nên cần nói rõ Skill làm gì và khi nào dùng. Vì chỉ tên và mô tả chiếm ngữ cảnh, bạn có thể cài nhiều Skill mà không tốn thêm ngữ cảnh.
  2. **Mức 2 – Hướng dẫn (nạp khi được kích hoạt):** phần thân của `SKILL.md` chứa quy trình và thực hành tốt; Claude đọc nó từ hệ thống file bằng bash khi yêu cầu khớp với mô tả của Skill.
  3. **Mức 3 – Tài nguyên và code (nạp khi cần):** các file đi kèm được nạp theo nhu cầu.

## Các mục trong trang gốc

Vì sao dùng Skills · Sử dụng Skills · Cách Skills hoạt động (ba mức, kiến trúc Skills, ví dụ nạp một Skill xử lý PDF) · Nơi Skills hoạt động (Claude API, Claude Code, claude.ai) · Cấu trúc Skill · Cân nhắc về bảo mật · Các Skill có sẵn (dựng sẵn, mã nguồn mở, ví dụ Skill tùy chỉnh) · Lưu giữ dữ liệu · Giới hạn và ràng buộc (khả dụng giữa các bề mặt, phạm vi chia sẻ, ràng buộc môi trường chạy) · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
- [Quickstart: Agent Skills trong API](quickstart.md)
- [Skills trong API](../../build-with-claude/skills-guide.md)

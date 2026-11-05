---
title: Bắt đầu với Agent Skills trong API (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/agent-skills/quickstart
description: Hướng dẫn dùng Agent Skills để tạo tài liệu bằng Claude API trong chưa đầy 10 phút.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/quickstart). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Bài hướng dẫn này chỉ cách dùng Agent Skills để tạo một bản trình chiếu PowerPoint: bật Skills, gửi request và lấy file được tạo ra. Trang gốc có ví dụ code cho nhiều ngôn ngữ (CLI, cURL, Python, TypeScript, C#, Go, Java, PHP, Ruby).

## Các điểm chính

- **Chuẩn bị:** cần một client SDK cho ngôn ngữ của bạn (hoặc `curl` và `jq`) và quen với việc gọi API. Đăng ký hoặc đăng nhập tài khoản Claude Console; đăng nhập bằng CLI được khuyến nghị cho phát triển cục bộ, hoặc dùng API key đặt trong biến `ANTHROPIC_API_KEY`.
- **Skills dựng sẵn trong API:** PowerPoint (`pptx`), Excel (`xlsx`), Word (`docx`) và PDF (`pdf`).
- **Bước 1 – Liệt kê Skills:** dùng Skills API để liệt kê các Skill do Anthropic quản lý; kết quả gồm `pptx`, `xlsx`, `docx`, `pdf`. API trả về metadata (tên và mô tả) của mỗi Skill; đây là mức đầu tiên của progressive disclosure, khi Claude biết có Skill nào mà chưa nạp toàn bộ hướng dẫn.
- **Bước 2 – Tạo bản trình chiếu:** chỉ định Skills bằng tham số `container` của Messages API. Request gồm:
  - `model`: một mô hình hỗ trợ công cụ thực thi code (code execution tool)
  - `container.skills`: các Skill Claude được dùng
  - `type: "anthropic"`: Skill do Anthropic quản lý
  - `skill_id: "pptx"`: định danh Skill PowerPoint
  - `version: "latest"`: phiên bản mới phát hành nhất
  - `tools`: bật thực thi code (bắt buộc khi dùng Skills)
- Ví dụ dùng phiên bản công cụ `code_execution_20260521`; Skills cũng hoạt động với các phiên bản code execution tool hiện hành khác như `code_execution_20250825`.
- **Bước 3 – Tải file đã tạo:** đoạn code ở bước này phân tích các kiểu kết quả mà phiên bản công cụ hiện tại trả về để lấy file.
- **Thử thêm:** tạo bảng tính, tài liệu Word và PDF.

## Các mục trong trang gốc

Trước khi bắt đầu · Tổng quan Agent Skills · Bước 1: Liệt kê các Skills có sẵn · Bước 2: Tạo bản trình chiếu · Bước 3: Tải file đã tạo · Thử thêm ví dụ (bảng tính, Word, PDF) · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/quickstart)
- [Tổng quan Agent Skills](overview.md)
- [Skills trong API](../../build-with-claude/skills-guide.md)
- [Code execution tool](../tool-use/code-execution-tool.md)

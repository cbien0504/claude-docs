---
title: Xây dựng trong Console (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/onboarding
description: Tạo, kiểm thử và lặp lại agent một cách trực quan trong Claude Console, rồi chạy chúng từ code của bạn bằng API.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/onboarding). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Claude Console cung cấp giao diện trực quan để tạo và cấu hình agent, cho phép bạn lặp lại cấu hình một cách tương tác trước khi viết code.

## Các điểm chính

- **Cách xây dựng agent:** giao diện trực quan dẫn bạn qua từng trường của định nghĩa agent:
  - **Mô hình và system prompt:** chọn mô hình và viết system prompt trong trình soạn thảo toàn chiều rộng.
  - **MCP server:** thêm MCP server từ xa theo URL và xác thực agent để hành động thay mặt bạn.
  - **Công cụ:** mở rộng khả năng của agent bằng toolset dựng sẵn và các công cụ MCP.
  - **Skill:** gắn skill của Anthropic hoặc skill tùy chỉnh từ thư viện của tổ chức.
  Khi cấu hình, Console hiển thị request API tương đương để bạn sao chép vào code khi đã hài lòng.
- **Kiểm thử agent:** Console có trình chạy session tích hợp; sau khi cấu hình, bạn bắt đầu session thử ngay, gửi message và xem luồng sự kiện mà không rời trang. Đây là cách nhanh nhất để kiểm tra system prompt và lựa chọn công cụ có cho ra kết quả mong muốn hay không.
- **Từ Console tới code của bạn.**

## Các mục trong trang gốc

Cách xây dựng agent · Kiểm thử agent · Từ Console tới code của bạn · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/onboarding)
- [Thiết lập agent](agent-setup.md)
- [Quickstart](quickstart.md)

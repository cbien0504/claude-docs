---
title: Strict tool use (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/strict-tool-use
description: Bắt buộc đầu vào công cụ của Claude tuân thủ JSON Schema bằng lấy mẫu có ràng buộc ngữ pháp (grammar-constrained sampling).
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/strict-tool-use). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Đặt `strict: true` trên định nghĩa công cụ đảm bảo đầu vào công cụ của Claude khớp JSON Schema của bạn, bằng cách ràng buộc việc lấy mẫu token của mô hình vào các đầu ra hợp lệ theo schema (kỹ thuật gọi là grammar-constrained sampling). Strict tool use xác thực tham số công cụ, bảo đảm Claude gọi hàm của bạn với đối số đúng kiểu.

## Các điểm chính

- **Dùng khi cần:** xác thực tham số công cụ, xây dựng workflow agent, bảo đảm lời gọi hàm an toàn về kiểu, và xử lý các công cụ phức tạp có thuộc tính lồng nhau.
- **Vì sao quan trọng với agent:** xây hệ thống agent đáng tin cậy cần bảo đảm tuân thủ schema. Nếu không có strict mode, Claude có thể trả về kiểu không tương thích (ví dụ `"2"` thay vì `2`) hoặc bỏ sót trường bắt buộc, làm hỏng hàm của bạn và gây lỗi lúc chạy. Strict tool use bảo đảm tham số luôn đúng kiểu.
- Trang gốc có quick start, giải thích cách hoạt động, các trường hợp sử dụng phổ biến và lưu giữ dữ liệu.

## Các mục trong trang gốc

Vì sao strict tool use quan trọng với agent · Quick start · Cách hoạt động · Trường hợp sử dụng phổ biến · Lưu giữ dữ liệu · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/strict-tool-use)
- [Structured outputs](../../build-with-claude/structured-outputs.md)
- [Định nghĩa công cụ](define-tools.md)

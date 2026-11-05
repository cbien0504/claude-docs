---
title: Structured outputs (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/structured-outputs
description: Nhận kết quả JSON đã được xác thực từ các workflow agent.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/structured-outputs). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Structured outputs giúp bạn nhận kết quả JSON đã được xác thực từ các workflow agent. Trang giải thích lý do dùng, cách hoạt động, cách dùng, cách SDK chuyển đổi schema, các cân nhắc quan trọng và khả năng tương thích với các tính năng khác.

## Các điểm chính

- **Cách dùng:** hỗ trợ cả dùng SDK (có bước chuyển đổi schema) lẫn dùng JSON schema thô.
- **Kết hợp strict tool use:** có thể dùng cả hai tính năng cùng nhau.
- **Cân nhắc quan trọng:** biên dịch ngữ pháp và caching; thay đổi prompt và chi phí token; giới hạn của JSON Schema; thứ tự thuộc tính; đầu ra không hợp lệ; giới hạn độ phức tạp của schema (giới hạn tường minh, giới hạn nội bộ bổ sung, mẹo giảm độ phức tạp).
- **Di chuyển từ bản beta** và **khả năng tương thích tính năng** có mục riêng.

## Các mục trong trang gốc

Vì sao dùng structured outputs · Cách hoạt động · Cách dùng · Cách SDK chuyển đổi hoạt động · Dùng JSON schema thô · Trường hợp sử dụng phổ biến · Strict tool use · Các cân nhắc quan trọng · Di chuyển từ bản beta · Tương thích tính năng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/structured-outputs)
- [Strict tool use](../agents-and-tools/tool-use/strict-tool-use.md)
- [Định nghĩa công cụ](../agents-and-tools/tool-use/define-tools.md)

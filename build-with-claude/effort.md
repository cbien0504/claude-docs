---
title: Effort (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/effort
description: Kiểm soát lượng token Claude dùng khi phản hồi bằng tham số effort, đánh đổi giữa độ kỹ lưỡng của phản hồi và hiệu quả token.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/effort). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Tham số effort cho phép bạn kiểm soát số token Claude dùng khi phản hồi, đánh đổi giữa độ kỹ lưỡng và hiệu quả token chỉ với một mô hình. Tham số effort cấp cao nhất khả dụng trên mọi mô hình được hỗ trợ và không cần beta header; effort theo từng message (per-message) đang ở dạng beta. Ở những nơi có adaptive thinking, effort là cách được khuyến nghị để kiểm soát độ sâu của thinking.

## Các điểm chính

- **Cách dùng theo bề mặt:** trong Messages API, đặt `output_config.effort` trên request (không đặt thì áp dụng mức mặc định của mô hình); trong Managed Agents, đặt `effort` trên đối tượng model của agent hoặc trong phần ghi đè mô hình của session (không đặt thì Managed Agents điền mức mặc định của mô hình).
- **Mức mặc định:** đa số mô hình Claude mặc định ở mức high, tiêu tốn bao nhiêu token cần thiết để có kết quả xuất sắc; Claude Opus 5.5 và Claude Haiku 5.5 mặc định ở mức medium. Có thể nâng lên `max` để đạt năng lực tối đa, hoặc hạ xuống để tiết kiệm token hơn.
- **Ví dụ:** trang có ví dụ chạy một request ở mức effort `medium`.
- **Đổi effort giữa hội thoại:** effort theo từng message (beta) hoặc effort cấp cao nhất ở request kế tiếp.

## Các mục trong trang gốc

Đặt mức effort · Cách effort hoạt động (các mức effort) · Mức effort khuyến nghị · Effort với tool use · Effort với thinking · Đổi effort giữa hội thoại (theo từng message (beta), cấp cao nhất ở request tiếp theo) · Thực hành tốt · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/effort)
- [Thinking](thinking.md)
- [Steering và kiểm soát chi phí của thinking](thinking-steering-and-cost.md)
- [Xây dựng chế độ orchestration](mid-conversation-effort-example.md)

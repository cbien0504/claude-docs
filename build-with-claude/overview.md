---
title: Tổng quan tính năng (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/overview
description: Khám phá các tính năng và khả năng nâng cao của Claude.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/overview). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang này là danh mục tổng hợp mọi tính năng của Claude Developer Platform, chia làm ba nhóm; mỗi tính năng là một dòng trong bảng gồm tên (liên kết tới trang riêng) và mô tả ngắn. Đây là điểm xuất phát để tìm tính năng cần dùng.

## Các điểm chính

- **Nhóm tính năng:**
  - **Platform features:** tính năng của nền tảng dùng chung cho nhiều API; trang của từng tính năng nói rõ có thể dùng ở đâu.
  - **Messages API features:** các tính năng dành cho Messages API.
  - **Managed Agents features:** các tính năng dành cho Managed Agents.
- **Tra cứu khả năng của mô hình bằng code:** Models API trả về `max_input_tokens`, `max_tokens` và một đối tượng `capabilities` cho mỗi mô hình khả dụng.
- **Ví dụ các tính năng nền tảng được liệt kê:** Advisor tool (mô hình thực thi nhanh hơn tham vấn một mô hình cố vấn mạnh hơn giữa lúc sinh nội dung); Agent Skills (kèm Skills tùy chỉnh và dựng sẵn); Batch processing (xử lý bất đồng bộ nhiều request Messages API trong một batch với nửa giá tiêu chuẩn); bộ công cụ SDK cho browser use và computer use; Browser use tool; Citations (câu trả lời về tài liệu của bạn trích dẫn đúng đoạn làm căn cứ); Classifier refusals (bộ phân loại an toàn trên một số mô hình có thể từ chối request, phản hồi về như phản hồi bình thường thay vì lỗi) và client-side fallback.
- **Tính đủ điều kiện ZDR/HIPAA:** từng tính năng được liệt kê trong trang về API và lưu giữ dữ liệu. Về quản trị và governance, có Admin API, Usage and Cost Analytics API và Compliance API.

## Các mục trong trang gốc

Tính năng nền tảng · Tính năng Messages API · Tính năng Managed Agents.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/overview)
- [Lưu giữ dữ liệu và tính đủ điều kiện](../manage-claude/api-and-data-retention.md)
- [Sử dụng Messages API](working-with-messages.md)

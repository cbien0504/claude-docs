---
title: Giới thiệu về Claude (tóm tắt)
source: https://platform.claude.com/docs/en/intro
description: Claude là nền tảng AI hiệu năng cao, đáng tin cậy và thông minh do Anthropic xây dựng, mạnh về ngôn ngữ, suy luận, phân tích, lập trình và nhiều lĩnh vực khác.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/intro). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang giới thiệu tổng quan về Claude và hai cách xây dựng ứng dụng với Claude, đồng thời chỉ lộ trình khuyến nghị cho nhà phát triển mới. Nếu bạn chỉ muốn trò chuyện với Claude, hãy truy cập claude.ai.

## Các điểm chính

- **Hai cách xây dựng với Claude:**
  - **Messages API:** truy cập mô hình trực tiếp qua prompt; phù hợp khi cần vòng lặp agent tùy chỉnh và kiểm soát chi tiết.
  - **Claude Managed Agents:** harness agent dựng sẵn, có thể cấu hình, chạy trên hạ tầng được quản lý; phù hợp với tác vụ chạy dài và công việc bất đồng bộ.
- **Chọn mô hình:** nếu chưa chắc nên dùng mô hình nào, bắt đầu với Claude Opus 5.5 (`claude-opus-5-5`) cho đa số workload. Dùng Claude Fable 5.1 (`claude-fable-5-1`) cho suy luận đòi hỏi cao và công việc agent dài hạn, hoặc khi kết quả đánh giá trên Opus 5.5 ở mức effort cao vẫn chưa đạt. Các mô hình hiện tại đều hỗ trợ đầu vào văn bản và hình ảnh, đầu ra văn bản, đa ngôn ngữ, vision và sử dụng công cụ (tool use).
  - Claude Sonnet 5.5 (`claude-sonnet-5-5`): cân bằng tốt giữa tốc độ và trí tuệ, cho tác vụ hằng ngày.
  - Claude Haiku 5.5 (`claude-haiku-5-5`): cho tác vụ khối lượng lớn, nhạy với độ trễ như phân loại, trích xuất, định tuyến.
- **Lộ trình cho nhà phát triển mới:** làm theo quickstart để thiết lập môi trường, cài SDK và gửi tin nhắn đầu tiên; khi tạo API key nên đặt thời hạn, không đưa khóa vào source control, code phía client hay prompt, và cân nhắc dùng Workload Identity Federation thay cho khóa tĩnh.

## Các mục trong trang gốc

Khám phá thế hệ mô hình Claude mới nhất · Lộ trình khuyến nghị cho nhà phát triển mới · Phát triển với Claude · Các khả năng chính · Hỗ trợ.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/intro)
- [Bắt đầu với Claude](get-started.md)
- [Sử dụng Messages API](build-with-claude/working-with-messages.md)
- [Tổng quan Claude Managed Agents](managed-agents/overview.md)
- [Xác thực](manage-claude/authentication.md)

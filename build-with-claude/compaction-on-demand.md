---
title: Compaction theo yêu cầu (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/compaction-on-demand
description: Yêu cầu Claude tóm tắt cuộc hội thoại vào thời điểm ứng dụng của bạn chọn, rồi tiếp tục từ bản tóm tắt.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/compaction-on-demand). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Với compaction theo yêu cầu, ứng dụng của bạn quyết định khi nào tóm tắt hội thoại: bạn gửi một request kèm tham số `compaction`, và Claude trả về một bản tóm tắt thay cho câu trả lời.

## Các điểm chính

- **Request compaction tách biệt với các lượt hội thoại.** Bạn gửi hội thoại hiện tại cùng `"compaction": {"type": "summarize"}`; phản hồi chỉ chứa một block `compaction` với `stop_reason` là `"compaction"`. Block gồm bản tóm tắt dạng văn bản đọc được và một chữ ký (signature); gửi lại nguyên vẹn trong các request sau.
- **Beta header:** gửi `compact-2026-09-04` ở request yêu cầu tóm tắt và ở mọi request sau đó mang block đã ký. Để biết mô hình có hỗ trợ không, gọi Models API.
- **Tiếp tục từ bản tóm tắt:** từ đó block thay thế các message nó đã tóm tắt; nó đứng đầu `messages`, các message đã tóm tắt bị bỏ đi và lượt tiếp theo của bạn đi sau nó.
- **Cách API xử lý request compaction:** tóm tắt mọi message trong request đúng một lần và không sinh câu trả lời nào sau đó. Cuộc gọi dùng `model`, `system`, `tools`, cài đặt thinking và `max_tokens` của request; bộ tóm tắt đọc định nghĩa công cụ nhưng không chạy công cụ nào, và phản hồi không có thinking. Nên gửi cùng `system` prompt và `tools` như phần còn lại của hội thoại.
- **Những điều bị từ chối hoặc nên tránh:** API từ chối request nếu lượt `assistant` cuối cùng kết thúc bằng lệnh gọi công cụ chưa có kết quả (gửi kết quả công cụ trước). Bỏ `stop_sequences`, `output_config.format` của structured output và `tool_choice` kiểu `any` hoặc `tool`, vì chúng không có tác dụng với lệnh tóm tắt.

## Các mục trong trang gốc

Cách compaction theo yêu cầu hoạt động · Yêu cầu bản tóm tắt · Tiếp tục từ bản tóm tắt (compact lại) · Compact trong vòng lặp (khi nào nên compact) · Tự viết prompt tóm tắt · Xử lý trường hợp không có bản tóm tắt hoặc lỗi · Tính mức sử dụng compaction · Giới hạn và tương tác với tính năng khác · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/compaction-on-demand)
- [Tổng quan compaction](compaction.md)
- [Compaction giữ lại các lượt gần nhất](compaction-keep-recent-turns.md)
- [Compaction ở chế độ nền](compaction-background.md)

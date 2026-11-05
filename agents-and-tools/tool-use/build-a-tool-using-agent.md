---
title: "Hướng dẫn: Xây dựng agent dùng công cụ (tóm tắt)"
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/build-a-tool-using-agent
description: Hướng dẫn từng bước đi từ một lệnh gọi công cụ đơn lẻ đến vòng lặp agent sẵn sàng cho production.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/build-a-tool-using-agent). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Hướng dẫn xây dựng một agent quản lý lịch qua năm "vòng" đồng tâm (ring). Mỗi vòng là một chương trình hoàn chỉnh, chạy được, và thêm đúng một khái niệm so với vòng trước. Đến cuối, bạn đã tự viết vòng lặp agent rồi thay nó bằng tool runner. Công cụ ví dụ là `create_calendar_event`, với schema dùng đối tượng lồng nhau, mảng và trường tùy chọn, để bạn thấy Claude xử lý các dạng đầu vào thực tế thay vì một chuỗi phẳng đơn giản. Mọi vòng đều chạy độc lập: bạn có thể chép bất kỳ vòng nào vào một file mới và nó sẽ chạy mà không cần code của các vòng trước.

## Các điểm chính

- **Vòng 1 – Một công cụ, một lượt:** chương trình nhỏ nhất dùng công cụ (một công cụ, một message người dùng, một lệnh gọi, một kết quả). Request gửi mảng `tools` cùng message; khi Claude thấy cần gọi công cụ, phản hồi có `stop_reason: "tool_use"` và một block `tool_use` chứa tên công cụ, `id` duy nhất và đầu vào có cấu trúc. Sau khi gửi kết quả, `stop_reason` thứ hai là `end_turn` và nội dung là ngôn ngữ tự nhiên cho người dùng.
- **Vòng 2 – Vòng lặp agent.**
- **Vòng 3 – Nhiều công cụ, gọi song song.**
- **Vòng 4 – Xử lý lỗi.**
- **Vòng 5 – Lớp trừu tượng tool runner của SDK.**

## Các mục trong trang gốc

Vòng 1: một công cụ, một lượt · Vòng 2: vòng lặp agent · Vòng 3: nhiều công cụ, gọi song song · Vòng 4: xử lý lỗi · Vòng 5: tool runner SDK · Bạn đã xây được gì · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/build-a-tool-using-agent)
- [Cách tool use hoạt động](how-tool-use-works.md)
- [Tool runner (SDK)](tool-runner.md)
- [Parallel tool use](parallel-tool-use.md)

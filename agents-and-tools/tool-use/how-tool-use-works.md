---
title: Cách tool use hoạt động (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/how-tool-use-works
description: Hiểu vòng lặp tool use, nơi công cụ chạy và khi nào nên dùng công cụ thay vì văn xuôi.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/how-tool-use-works). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trang giải thích các khái niệm đằng sau tool use: công cụ chạy ở đâu, vòng lặp agent hoạt động ra sao và khi nào tool use là cách tiếp cận đúng. Muốn thực hành thì bắt đầu với hướng dẫn "Xây dựng một agent dùng công cụ".

## Các điểm chính

- **Hợp đồng tool use:** tool use là một hợp đồng giữa ứng dụng của bạn và mô hình. Bạn chỉ định những thao tác nào khả dụng cùng hình dạng đầu vào/đầu ra; Claude quyết định khi nào và gọi thế nào. Mô hình không bao giờ tự chạy gì cả: nó phát ra một request có cấu trúc, và code của bạn (hoặc của Anthropic) thực thi. Nhờ đó mô hình hành xử giống một hàm bạn gọi hơn là một bộ sinh văn bản: định nghĩa schema, xử lý callback, trả kết quả.
- **Công cụ chạy ở đâu** là trục khác biệt chính, chia thành ba nhóm quyết định trách nhiệm của ứng dụng:
  - **Công cụ do người dùng định nghĩa (client thực thi):** bạn viết schema, chạy code và trả kết quả; phần lớn lưu lượng tool use thuộc nhóm này. Phản hồi chứa block `tool_use` có tên công cụ và đối tượng JSON tham số; ứng dụng chạy thao tác (truy vấn cơ sở dữ liệu, gọi HTTP, ghi file…) và gửi kết quả lại.
  - **Công cụ theo schema của Anthropic (client thực thi):** với một số thao tác phổ biến (quản lý bộ nhớ nháp, chạy lệnh shell, chỉnh sửa file, điều khiển desktop hoặc trình duyệt), Anthropic công bố schema còn ứng dụng của bạn lo phần thực thi; mô hình thực thi giống công cụ do người dùng định nghĩa.
  - **Công cụ do server thực thi:** chạy trên hạ tầng của Anthropic.
- **Hai vòng lặp:** vòng lặp agent với client tool và vòng lặp phía máy chủ.

## Các mục trong trang gốc

Hợp đồng tool use · Công cụ chạy ở đâu · Vòng lặp agent (client tool) · Vòng lặp phía máy chủ · Khi nào dùng công cụ (và khi nào không) · Chọn giữa các cách tiếp cận · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/how-tool-use-works)
- [Xây dựng agent dùng công cụ](build-a-tool-using-agent.md)
- [Định nghĩa công cụ](define-tools.md)
- [Tổng quan sử dụng công cụ](overview.md)

---
title: Browser và computer use với bộ công cụ SDK (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/browser-use-sdk
description: Chạy browser use tool hoặc computer use tool từ SDK Python hoặc TypeScript; SDK chạy vòng lặp và các kiểm tra bạn cấu hình, còn bạn cung cấp trình duyệt hoặc máy tính để bàn.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/browser-use-sdk). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Với các toolset browser và computer trong SDK Python và TypeScript, bạn có thể xây dựng agent làm việc trong trình duyệt web hoặc trên máy tính để bàn, kể cả với ứng dụng không có giao diện lập trình. Qua browser use tool, Claude điều hướng, đọc và tương tác với trang web; qua computer use tool, Claude thao tác trên desktop. SDK kết nối Claude với trình duyệt hoặc desktop của bạn, chạy các kiểm tra bạn cấu hình (ví dụ chính sách URL cho `navigate` hoặc callback phê duyệt), chuyển từng lệnh gọi hợp lệ cho **driver** của bạn và tạo `tool_result` từ những gì driver trả về. Tool runner có thể chạy vòng lặp agent thay bạn.

## Các điểm chính

- **Driver** là phần bạn cung cấp, thao tác trên trình duyệt hoặc desktop. Có thể dùng driver của nhà cung cấp (agent chỉ cần vài dòng code), hoặc tự viết bằng thư viện tự động hóa trình duyệt như Playwright. Kho claude-quickstarts có một driver trình duyệt mẫu bằng Python và TypeScript, điều khiển Chromium qua Chrome DevTools Protocol (CDP).
- **Trạng thái:** lớp toolset browser đang ở dạng beta trong SDK Python và TypeScript; lớp toolset computer cũng ở dạng beta trong các SDK này.
- **Phần lớn trang nói về browser toolset;** mục "Computer toolset" nêu những điểm khác biệt.
- **Chạy an toàn:** trang gốc có phần riêng về viết chính sách URL, chặn request trong driver, đặt chính sách egress ở container, giới hạn upload và download, chặn các thao tác có hệ quả nghiêm trọng, cô lập máy chủ trình duyệt và dùng trình duyệt từ xa/được lưu trữ.

## Các mục trong trang gốc

Dùng driver của nhà cung cấp · Tích hợp đối tác · Tùy biến driver (bật/tắt thành viên, thêm hook trước và sau) · Triển khai driver (trả kết quả, báo trạng thái trình duyệt, xử lý lỗi, bắt đầu lệnh gọi trong khi phản hồi đang streaming, chạy không cần tool runner) · Ví dụ nâng cao: tự viết driver · Chạy toolset an toàn · Computer toolset (viết driver desktop, co giãn tọa độ và kích thước ảnh, kiểm tra đầu vào và kết quả, chạy an toàn, dùng cả hai toolset trong một request) · Tham chiếu · Hạn chế · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/browser-use-sdk)
- [Browser use tool](browser-use-tool.md)
- [Computer use tool](computer-use-tool.md)
- [Tool runner (SDK)](tool-runner.md)

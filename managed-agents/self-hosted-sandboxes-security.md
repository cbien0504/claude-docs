---
title: Mô hình bảo mật của sandbox tự lưu trữ (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-security
description: Mô hình trách nhiệm chia sẻ cho các environment sandbox tự lưu trữ.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-security). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Trong mọi environment, Anthropic bảo mật những phần do Anthropic vận hành: tính toàn vẹn của session và hàng đợi công việc, cô lập đa người thuê (multitenant) và tối thiểu hóa ngữ cảnh của agent. Khi tự lưu trữ sandbox, các trách nhiệm sau thuộc về bạn.

## Các điểm chính

Những gì bạn sở hữu:
- **Chất lượng image sandbox và gia cố runtime:** Anthropic không kiểm tra hay xác minh image; nên theo các thực hành tốt như bỏ các Linux capability không cần thiết, chạy bằng người dùng không phải root và dùng hệ thống file gốc chỉ đọc.
- **Kiểm soát egress mạng:** quyền truy cập mạng của sandbox do VPC và quy tắc tường lửa của bạn quyết định; không hạn chế egress thì một lần thực thi công cụ bị xâm phạm có thể chạm tới host bên ngoài tùy ý.
- **Lưu trữ và xoay vòng khóa dịch vụ:** khóa dịch vụ của environment (`ANTHROPIC_ENVIRONMENT_KEY`) cho phép thăm dò hàng đợi công việc của environment và gửi kết quả về session; hãy lưu trong secrets manager, không đặt trong file môi trường hay image sandbox.
- **Cô lập workload không tin cậy:** khóa phạm vi một hàng đợi environment; nếu chạy code không tin cậy trong sandbox, cân nhắc cấp workspace và environment riêng cho mỗi ranh giới tin cậy.
- **Credential theo từng session:** mỗi work item worker nhận có thể mang một `secret` riêng cho session, được worker dùng thay cho khóa dịch vụ của environment.
- **Phạm vi ảnh hưởng của việc thực thi công cụ:** công cụ chạy trong sandbox với quyền của tiến trình; áp dụng đặc quyền tối thiểu và chỉ mount các thư mục công cụ cần.
- **Lưu giữ log và nội dung session:** nội dung hội thoại và đầu ra công cụ đi qua worker và ở lại trong môi trường của bạn; bạn chịu trách nhiệm lưu giữ, che hoặc xóa chúng theo chính sách của mình.
- **Nội dung memory store:** memory store vẫn do Anthropic lưu trữ (kể cả lịch sử phiên bản); khi session gắn một store, worker giữ bản làm việc dưới `/mnt/memory/` trong sandbox của bạn.

## Các mục trong trang gốc

Những gì bạn sở hữu · Những gì Anthropic không thể làm thay bạn.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-security)
- [Sandbox tự lưu trữ](self-hosted-sandboxes.md)
- [Memory stores trong sandbox tự lưu trữ](self-hosted-sandboxes-memory.md)

---
title: Chọn môi trường cho agent (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/choosing-an-environment
description: Quyết định công cụ và code của Claude Managed Agents chạy trong môi trường đám mây do Anthropic quản lý hay trong sandbox tự lưu trữ, và xem điều gì thay đổi nếu bạn chuyển.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/choosing-an-environment). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Một environment quy định nơi công cụ và code của agent chạy. Chúng chạy trong một sandbox: không gian làm việc cô lập (như một container) nơi agent chạy lệnh và làm việc với file. Bạn có hai lựa chọn, và định nghĩa agent giống nhau dù chọn cách nào (mô hình, prompt, công cụ được đặt trên agent, không đặt trên environment).

## Các điểm chính

- **Môi trường đám mây (cloud environment):** Anthropic chạy sandbox cho bạn. Mỗi session có một container Linux mới trên hạ tầng do Anthropic quản lý, đã cài sẵn các ngôn ngữ, cơ sở dữ liệu và tiện ích phổ biến. Bạn chọn quy tắc mạng và các gói bổ sung.
- **Sandbox tự lưu trữ (self-hosted sandbox):** bạn chạy sandbox trên hạ tầng của mình. Claude vẫn chạy phía Anthropic và quyết định công cụ nào được gọi tiếp theo; một chương trình do bạn chạy, gọi là worker, thực hiện các lệnh gọi công cụ bash và file của agent trên máy của bạn.
- **Khuyến nghị:** nếu chưa chắc nên chọn gì, hoặc mới dùng Claude Managed Agents, hãy bắt đầu với môi trường đám mây.
- Trang gốc có bảng so sánh hai lựa chọn, thời điểm nên chọn sandbox tự lưu trữ, điều không thay đổi khi dùng sandbox tự lưu trữ, những gì bạn gánh thêm và đánh đổi, khác biệt trên Claude Platform on AWS và Claude Models on Google Cloud (Anthropic managed), và cách chuyển từ môi trường đám mây sang sandbox tự lưu trữ.

## Các mục trong trang gốc

Bắt đầu với môi trường đám mây · So sánh các lựa chọn · Khi nào chọn sandbox tự lưu trữ · Điều sandbox tự lưu trữ không thay đổi · Bạn gánh thêm và đánh đổi gì · Khác biệt trên Claude Platform on AWS · Khác biệt trên Claude Models on Google Cloud (Anthropic managed) · Chuyển từ môi trường đám mây sang sandbox tự lưu trữ.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/choosing-an-environment)
- [Cài đặt môi trường đám mây](environments.md)
- [Sandbox tự lưu trữ – tổng quan và quickstart](self-hosted-sandboxes.md)
- [Thiết lập agent](agent-setup.md)

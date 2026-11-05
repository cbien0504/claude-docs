---
title: Xác thực (tóm tắt)
source: https://platform.claude.com/docs/en/manage-claude/authentication
description: Xác thực với Claude API bằng API key, Workload Identity Federation hoặc App Attest.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/manage-claude/authentication). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Claude API hỗ trợ ba cách xác thực request. API key và Workload Identity Federation cấp quyền truy cập như nhau tới các endpoint của Claude API. Nên bắt đầu bằng API key cho nhanh (khóa cá nhân để tự phát triển, hoặc khóa service account cho thứ dùng chung), và chuyển sang Workload Identity Federation khi workload của bạn đã có danh tính do nền tảng cấp mà bạn có thể liên kết. Dùng App Attest cho ứng dụng iOS và macOS phát hành tới người dùng cuối.

## Các điểm chính

| Phương thức | Credential | Phù hợp nhất cho |
| --- | --- | --- |
| API key | Secret tĩnh dạng `sk-ant-api...`, gửi như bearer token trong header `Authorization` | Phát triển cục bộ, tạo prototype, script, và máy chủ nơi bạn kiểm soát việc lưu trữ secret |
| Workload Identity Federation | Bearer token ngắn hạn đổi từ identity token của nhà cung cấp danh tính (identity provider) | Workload production trên nền tảng đám mây (AWS, Google Cloud, Azure), pipeline CI/CD và Kubernetes, khi muốn loại bỏ secret tĩnh |
| App Attest | Access token ngắn hạn cấp cho một bản cài đặt hợp lệ, đã được chứng thực, của ứng dụng iOS hoặc macOS đã đăng ký | Ứng dụng iOS và macOS gọi thẳng Claude API mà không có back end hay proxy |

- **API key** là secret tĩnh bạn tạo trong Claude Console và gửi trong mỗi request qua header `Authorization`. Trang gốc nói về các loại khóa (quyết định khóa làm được gì, dùng ở đâu, hết hiệu lực khi nào), cách tạo và dùng khóa, chọn workspace, thời hạn khóa, thay thế khóa workspace và lưu ý với ứng dụng chạy trên trình duyệt.
- **Workload Identity Federation** và **App Attest** có các mục riêng trong trang gốc.

## Các mục trong trang gốc

API keys (các loại khóa, tạo và dùng khóa, chọn workspace, thời hạn khóa, thay thế khóa workspace, ứng dụng trên trình duyệt) · Workload Identity Federation · App Attest · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/manage-claude/authentication)
- [Bắt đầu với Claude](../get-started.md)

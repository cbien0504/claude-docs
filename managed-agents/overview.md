---
title: Tổng quan về Claude Managed Agents
source: https://platform.claude.com/docs/en/managed-agents/overview
description: Harness agent dựng sẵn, có thể cấu hình, chạy trên hạ tầng được quản lý. Phù hợp nhất cho các tác vụ chạy dài và công việc bất đồng bộ.
featureMetadata:
  topic:
    title: Managed Agents
    url: https://platform.claude.com/docs/en/managed-agents/overview
  status: beta
  betaHeader: managed-agents-2026-04-01
  zdr:
    eligibility: not-eligible
    note: Sessions are stateful resources; transcripts persist until you delete them. Applies to all Managed Agents sub-features, including Self-hosted sandboxes.
  supportedModels:
    - claude-fable-5-1
    - claude-mythos-5-1
    - claude-fable-5
    - claude-mythos-5
    - claude-mythos-preview
    - claude-opus-5-5
    - claude-opus-5
    - claude-sonnet-5-5
    - claude-sonnet-5
    - claude-haiku-5-5
    - claude-haiku-4-5-20251001
    - claude-opus-4-8
    - claude-opus-4-7
    - claude-opus-4-6
    - claude-sonnet-4-6
    - claude-opus-4-5-20251101
    - claude-sonnet-4-5-20250929
  supportedPlatforms:
    Claude API: beta
    Claude Platform on AWS: beta
    Claude Models on Google Cloud (Anthropic managed): beta
---

> Đây là bản dịch không chính thức. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/overview). Khi có khác biệt, bản tiếng Anh là bản đúng.

Anthropic cung cấp hai cách để xây dựng với Claude, mỗi cách phù hợp với các trường hợp sử dụng khác nhau:

|                      | Messages API                                          | Claude Managed Agents                                                              |
| -------------------- | ----------------------------------------------------- | ---------------------------------------------------------------------------------- |
| **Là gì**            | Truy cập trực tiếp vào mô hình thông qua prompt       | Harness agent dựng sẵn, có thể cấu hình, chạy trên hạ tầng được quản lý            |
| **Phù hợp nhất cho** | Vòng lặp agent tùy chỉnh và kiểm soát chi tiết        | Các tác vụ chạy dài và công việc bất đồng bộ                                       |

Claude Managed Agents cung cấp harness (khung điều phối agent) và hạ tầng để chạy Claude như một agent tự chủ. Thay vì tự xây dựng vòng lặp agent (agent loop), cơ chế thực thi công cụ và môi trường runtime, bạn có một môi trường được quản lý hoàn toàn, nơi Claude có thể đọc file, chạy lệnh, duyệt web và chạy code một cách an toàn. Harness hỗ trợ sẵn prompt caching, compaction và các tối ưu hiệu năng khác để cho ra kết quả agent chất lượng cao và hiệu quả. Nếu bạn muốn tự xây dựng vòng lặp agent với quyền truy cập mô hình trực tiếp, hãy xem [Sử dụng Messages API](../build-with-claude/working-with-messages.md).

> **Lưu ý:** Claude Managed Agents cũng khả dụng trên Claude Models on Google Cloud (Anthropic managed) và Claude Platform on AWS, với một số khác biệt về tính năng khả dụng và hành vi của session. Xem hướng dẫn [Claude Models on Google Cloud (Anthropic managed)](../build-with-claude/claude-models-on-google-cloud/anthropic-managed.md#claude-managed-agents) hoặc [Claude Managed Agents](../build-with-claude/claude-platform-on-aws.md#claude-managed-agents) trong hướng dẫn Claude Platform on AWS.

- **[Quickstart](quickstart.md):** Tạo session agent đầu tiên của bạn
- **[Start a session](sessions.md):** Tạo một session và gửi sự kiện đầu tiên
- **[Reference](reference.md):** Các loại sự kiện, giới hạn tốc độ (rate limit), cờ CLI và các bảng tra cứu khác

## Các khái niệm cốt lõi

Claude Managed Agents được xây dựng xoay quanh bốn khái niệm:

| Khái niệm                | Mô tả                                                                                                                                                  |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Agent**                | Mô hình, system prompt, công cụ, MCP server và skill                                                                                                   |
| **Môi trường (Environment)** | Cấu hình nơi các session chạy: sandbox đám mây do Anthropic quản lý, hoặc sandbox tự lưu trữ (self-hosted) trên hạ tầng của riêng bạn                   |
| **Session**              | Một thực thể agent đang chạy trong một môi trường, thực hiện một tác vụ cụ thể và tạo ra các đầu ra                                                    |
| **Sự kiện (Events)**     | Các thông điệp trao đổi giữa ứng dụng của bạn và agent (lượt của người dùng, kết quả công cụ, cập nhật trạng thái)                                    |

## Cách hoạt động

1. **Tạo một agent.** Xác định mô hình, system prompt, công cụ, MCP server và skill. Tạo agent một lần và tham chiếu đến nó bằng ID trong các session.
2. **Tạo một môi trường.** [Cấu hình nơi agent chạy](choosing-an-environment.md): một sandbox đám mây, hoặc một [sandbox tự lưu trữ](self-hosted-sandboxes.md) trên hạ tầng của riêng bạn.
3. **Bắt đầu một session.** Khởi chạy một session tham chiếu đến cấu hình agent và môi trường của bạn.
4. **Gửi sự kiện và nhận phản hồi streaming.** Gửi tin nhắn của người dùng dưới dạng sự kiện. Claude tự động chạy các công cụ và stream kết quả trở lại thông qua server-sent events (SSE). Lịch sử sự kiện được lưu trữ phía máy chủ và có thể được lấy về đầy đủ.
5. **Điều hướng hoặc ngắt.** Gửi thêm các sự kiện của người dùng để định hướng agent trong khi nó đang chạy, hoặc ngắt agent để đổi hướng.

## Khi nào nên dùng Claude Managed Agents

Claude Managed Agents phù hợp nhất cho các workload cần:

* **Thực thi chạy dài:** Các tác vụ chạy trong vài phút hoặc vài giờ với nhiều lần gọi công cụ
* **Hạ tầng đám mây:** Sandbox an toàn với các gói được cài sẵn và quyền truy cập mạng
* **Thực thi tự lưu trữ:** Sandbox trên hạ tầng do bạn kiểm soát nhằm đáp ứng yêu cầu tuân thủ hoặc lưu trú dữ liệu (data residency)
* **Hạ tầng tối thiểu:** Không cần tự xây dựng vòng lặp agent, sandbox hay lớp thực thi công cụ
* **Session có trạng thái (stateful):** Hệ thống file và lịch sử hội thoại được duy trì qua nhiều lần tương tác
* **Thực thi theo lịch:** Chạy agent định kỳ theo lịch cron thông qua [scheduled deployments](scheduled-deployments.md)

## Công cụ được hỗ trợ

Claude Managed Agents cho Claude quyền truy cập vào một bộ công cụ dựng sẵn:

* **Bash:** Chạy các lệnh shell trong sandbox
* **Thao tác file:** Đọc, ghi, chỉnh sửa, glob và grep file trong sandbox
* **Tìm kiếm và tải nội dung web:** Tìm kiếm trên web và lấy nội dung từ URL, có thể giới hạn theo danh sách cho phép (allowlist) hoặc danh sách chặn (blocklist) các domain
* **MCP server:** Kết nối với các nhà cung cấp công cụ bên ngoài

Xem [Tools](tools.md) để biết danh sách đầy đủ và các tùy chọn cấu hình.

## Truy cập bản beta

> **Lưu ý:** Claude Managed Agents đang ở giai đoạn beta. Tất cả endpoint của Managed Agents yêu cầu beta header `managed-agents-2026-04-01`. SDK tự động đặt beta header. Hành vi có thể được tinh chỉnh giữa các bản phát hành để cải thiện đầu ra.

Để bắt đầu, bạn cần:

1. Một [khóa API Claude](https://platform.claude.com/settings/keys) từ Claude Console
2. Beta header `managed-agents-2026-04-01` trên mọi request
3. Quyền truy cập Claude Managed Agents (được bật mặc định cho tất cả tài khoản API)

Trong giai đoạn beta, [MCP tunnels](../agents-and-tools/mcp-tunnels/overview.md) và [dreaming](dreams.md) đang ở dạng research preview (bản xem trước nghiên cứu) với phạm vi hạn chế hơn. [Yêu cầu quyền truy cập](https://claude.com/form/claude-managed-agents) để bật các tính năng này.

Claude Managed Agents được thiết kế theo hướng có trạng thái (stateful): các session chạy lâu dài, tiếp tục mượt mà sau các lần tạm dừng, và lưu lịch sử hội thoại, trạng thái sandbox cùng các đầu ra ở phía máy chủ. Vì vậy, hiện tại Managed Agents không đủ điều kiện áp dụng [Zero Data Retention](../manage-claude/api-and-data-retention.md#zero-data-retention-zdr-scope) hoặc phạm vi của HIPAA Business Associate Agreement (BAA). Bạn giữ quyền kiểm soát dữ liệu này: bạn có thể [xóa session](session-operations.md#deleting-a-session), và xóa riêng bất kỳ [file](../build-with-claude/files.md#delete-a-file) nào bạn đã tải lên, vào bất kỳ lúc nào thông qua API. Để biết mức độ đủ điều kiện của tất cả tính năng, xem [API và lưu giữ dữ liệu](../manage-claude/api-and-data-retention.md#feature-eligibility).

Xem [Giới hạn tốc độ](reference.md#rate-limits) và [Hướng dẫn về thương hiệu](reference.md#branding-guidelines) trong phần reference.

## Tính khả dụng

Managed Agents đang ở giai đoạn beta trên mọi mô hình.

### Hỗ trợ API

| Trạng thái | Nền tảng đám mây                                                                                                                                                                                                                                            | Mô hình                                                    |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Beta       | Claude API, [Claude Platform on AWS](../build-with-claude/claude-platform-on-aws.md), [Claude Models on Google Cloud (Anthropic managed)](../build-with-claude/claude-models-on-google-cloud/anthropic-managed.md) | [Tất cả mô hình](../models/overview.md) |

### Beta header bắt buộc

[Tổng quan về beta header](../api/beta-headers.md)

Beta header cho phép bạn truy cập các tính năng thử nghiệm và khả năng mô hình mới trước khi chúng trở thành một phần của API tiêu chuẩn.

* `managed-agents-2026-04-01`

### Xử lý dữ liệu

[Tổng quan về xử lý dữ liệu](../manage-claude/api-and-data-retention.md#feature-eligibility)

| Mục        | Zero data retention                                                                                                                                                    | HIPAA                                                                                 |
| ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Trạng thái | Không đủ điều kiện                                                                                                                                                     | Không đủ điều kiện                                                                    |
| Chi tiết   | Session là các tài nguyên có trạng thái; bản ghi (transcript) được lưu giữ cho đến khi bạn xóa chúng. Áp dụng cho tất cả tính năng con của Managed Agents, bao gồm Self-hosted sandboxes. | Áp dụng cho tất cả tính năng con của Managed Agents, bao gồm Self-hosted sandboxes.   |

Các endpoint áp dụng:

* `/v1/agents`
* `/v1/sessions`
* `/v1/environments`

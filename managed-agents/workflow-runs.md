---
title: Workflow runs (tóm tắt)
source: https://platform.claude.com/docs/en/managed-agents/workflow-runs
description: Theo dõi các lần chạy workflow của agent: trạng thái và sự kiện của chúng, khi nào công việc hoàn tất, các yêu cầu khi một lần chạy đang mở, ngân sách và giới hạn.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/workflow-runs). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Một **workflow** là chương trình mà agent viết ra để chạy nhiều agent và kết hợp những gì chúng trả về. Một **workflow run** là một lần thực thi của một workflow. Dynamic workflows được giới thiệu trong trang điều phối multiagent.

## Các điểm chính

- **Cách một lần chạy chuyển qua các trạng thái** và **các sự kiện của lần chạy.**
- **Các thread của một lần chạy** và **biết khi nào công việc xong.**
- **Theo dõi một lần chạy**, kể cả cách dựng lại trạng thái lần chạy sau khi kết nối lại.
- **Ngắt một session khi có lần chạy đang mở.**
- **Chi phí và ngân sách; giới hạn** (kể cả giới hạn tốc độ).

## Các mục trong trang gốc

Cách dynamic workflow hoạt động · Cách một lần chạy chuyển trạng thái · Sự kiện của lần chạy · Các thread của một lần chạy · Biết khi nào công việc xong · Theo dõi một lần chạy · Ngắt session khi có lần chạy đang mở · Khi một lần chạy đang mở (dựng lại trạng thái sau khi kết nối lại) · Chi phí và ngân sách · Giới hạn · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/managed-agents/workflow-runs)
- [Điều phối multiagent](multiagent-orchestration.md)
- [Session threads](session-threads.md)
- [Session budgets](budgets.md)

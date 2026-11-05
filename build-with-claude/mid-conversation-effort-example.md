---
title: Xây dựng chế độ orchestration (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/mid-conversation-effort-example
description: Xây dựng một chế độ cấp session cấp sự đồng ý thường trực cho việc phân tán multiagent, bật và tắt bằng system message giữa cuộc hội thoại.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/mid-conversation-effort-example). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Chế độ orchestration là một công tắc cấp session: khi bật, mô hình dồn mức kỹ lưỡng tối đa cho mọi yêu cầu đáng kể, tự khảo sát tác vụ rồi mặc định phân việc cho các subagent chạy song song. Khi tắt, cùng công cụ orchestration đó quay về dạng phải chọn tham gia (opt-in) theo từng yêu cầu. Chế độ này **không phải là tham số API**; nó được lắp từ các thành phần đã có tài liệu.

## Các điểm chính

- **Ba thành phần tạo nên chế độ:**
  1. **Mức effort:** request chạy ở một giá trị Effort đã được tài liệu hóa như `xhigh` (không có mức ẩn nào cao hơn). Ví dụ đặt effort ở cấp cao nhất của mỗi request, không cần beta header.
  2. **Lời nhắc chế độ (mode reminder):** một system message giữa hội thoại cho mô hình biết chế độ đang bật, kèm lời nhắc ngắn sau vài lượt và thông báo thoát khi tắt. Trường `system` cấp cao nhất không bao giờ đổi, nên phần prefix đã cache vẫn nguyên vẹn.
  3. **Sự đồng ý thường trực trong mô tả công cụ:** mô tả của công cụ orchestration nêu rằng khi chế độ bật, mô hình nên tự viết và chạy workflow cho mọi tác vụ đáng kể mà không cần hỏi trước.
- **Lưu ý chi phí:** việc phân tán nhân lên lượng token sử dụng, vì một request có thể sinh nhiều cuộc hội thoại subagent; chỉ nên dùng chế độ cho công việc xứng đáng với chi phí.
- **Hằng số trong ví dụ:** `MAX_CONCURRENT` giới hạn số subagent chạy cùng lúc; `MAX_TOTAL_SUBTASKS` giới hạn số tác vụ con mô hình được xếp hàng trong một lệnh gọi Workflow.

## Các mục trong trang gốc

Thiết lập vòng lặp · Định nghĩa các lời nhắc chế độ · Cấp sự đồng ý thường trực trong mô tả công cụ · Chạy bash tool cục bộ · Chạy một subagent · Ghi nhật ký kết quả để chạy lại có thể tiếp tục · Phân tán rồi kiểm chứng · Bật/tắt chế độ bằng system message giữa hội thoại · Chạy thử · Hướng tới harness production · Liên quan.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/mid-conversation-effort-example)
- [Effort](effort.md)
- [System message giữa hội thoại và thay đổi công cụ](mid-conversation-system-messages.md)

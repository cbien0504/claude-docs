---
title: Batch processing (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/batch-processing
description: Xử lý bất đồng bộ khối lượng lớn request Messages bằng Message Batches API, giảm 50% chi phí và tăng thông lượng.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/batch-processing). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Batch processing là cách xử lý hiệu quả khối lượng lớn request: thay vì xử lý từng request và nhận phản hồi ngay, bạn gửi nhiều request cùng lúc để xử lý bất đồng bộ. Cách này phù hợp khi cần xử lý nhiều dữ liệu, không cần phản hồi tức thì, muốn tối ưu chi phí hoặc chạy đánh giá và phân tích quy mô lớn. Message Batches API là triển khai đầu tiên của Anthropic cho mẫu này: phần lớn batch hoàn tất trong chưa đầy 1 giờ, giảm 50% chi phí và tăng thông lượng.

## Các điểm chính

- **Cách hoạt động:** hệ thống tạo một Message Batch từ các request Messages bạn gửi; batch được xử lý bất đồng bộ, mỗi request xử lý độc lập; bạn thăm dò (poll) trạng thái và lấy kết quả khi mọi request đã xử lý xong.
- **Tình huống phù hợp:** đánh giá quy mô lớn, kiểm duyệt nội dung, phân tích dữ liệu, sinh nội dung hàng loạt (ví dụ mô tả sản phẩm, tóm tắt bài viết).
- **Giới hạn của batch:**
  - Tối đa 100.000 request Messages hoặc 256 MB, tùy mức nào đạt trước.
  - Phần lớn batch xong trong 1 giờ; bạn lấy được kết quả khi tất cả message đã hoàn tất hoặc sau 24 giờ, tùy cái nào đến trước. Batch hết hạn nếu chưa xử lý xong trong 24 giờ.
  - Kết quả khả dụng trong 29 ngày kể từ khi tạo; sau đó vẫn xem được batch nhưng không tải được kết quả.
  - Batch thuộc phạm vi một Workspace trong Claude Console.
  - Áp dụng giới hạn tốc độ (rate limit) cho cả HTTP request của Batches API lẫn số request đang chờ xử lý trong batch; tốc độ xử lý có thể chậm hơn tùy nhu cầu hiện tại.

## Các mục trong trang gốc

Cách Message Batches API hoạt động (giới hạn, mô hình được hỗ trợ, những gì có thể đưa vào batch) · Giá · Cách sử dụng (chuẩn bị và tạo batch, theo dõi batch và thăm dò hoàn tất, liệt kê batch, lấy kết quả, hủy batch, dùng prompt caching với batch, server tool và vòng lặp agent, đầu ra mở rộng (beta), thực hành tốt, xử lý sự cố) · Lưu trữ batch và quyền riêng tư · FAQ · Tính khả dụng · Các bước tiếp theo.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/batch-processing)
- [Prompt caching](prompt-caching.md)
- [Sử dụng Messages API](working-with-messages.md)

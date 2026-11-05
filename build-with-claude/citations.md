---
title: Citations (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/citations
description: Gắn câu trả lời của Claude với tài liệu nguồn của bạn; citations trả về đúng các đoạn văn làm căn cứ cho từng nhận định để bạn kiểm chứng và hiển thị nguồn cho người dùng.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/citations). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Khi trả lời câu hỏi về tài liệu, Claude có thể đưa ra trích dẫn chi tiết, giúp bạn theo dõi và kiểm chứng nguồn đằng sau từng câu trả lời. Tất cả các mô hình đang hoạt động đều hỗ trợ citations.

So với việc yêu cầu Claude trích nguồn bằng prompt, tính năng citations có các ưu điểm:
- **Tiết kiệm chi phí:** `cited_text` không tính vào token đầu ra.
- **Tin cậy hơn:** API phân tích citations vào định dạng phản hồi và trích `cited_text` trực tiếp, nên trích dẫn đảm bảo trỏ hợp lệ tới tài liệu bạn cung cấp.
- **Chất lượng tốt hơn:** theo đánh giá của Anthropic, citations có khả năng chọn đúng đoạn trích phù hợp nhất cao hơn hẳn so với cách chỉ dùng prompt.

## Các điểm chính

Quy trình tích hợp gồm các bước:
1. **Cung cấp tài liệu và bật citations:** đưa tài liệu ở một trong các định dạng được hỗ trợ (PDF, văn bản thuần, hoặc tài liệu nội dung tùy chỉnh) và đặt `citations.enabled=true` trên từng tài liệu. Hiện tại citations phải được bật cho tất cả hoặc không tài liệu nào trong một request. Chỉ hỗ trợ trích dẫn văn bản; chưa hỗ trợ trích dẫn hình ảnh.
2. **Tài liệu được xử lý:** nội dung được chia thành các "chunk" để xác định độ chi tiết tối thiểu của trích dẫn (ví dụ chia theo câu cho phép trích một câu hoặc nhiều câu liên tiếp). Với PDF, văn bản được trích xuất rồi chia theo câu (chưa hỗ trợ trích dẫn hình ảnh trong PDF). Với văn bản thuần, nội dung chia theo câu. Với tài liệu nội dung tùy chỉnh, các block bạn cung cấp được dùng nguyên trạng và không chia thêm.
3. **Claude trả lời kèm trích dẫn:** phản hồi có thể gồm nhiều block văn bản, mỗi block chứa một nhận định của Claude kèm các trích dẫn hỗ trợ nhận định đó.

## Các mục trong trang gốc

Cách citations hoạt động (nội dung có/không thể trích dẫn, chỉ mục trích dẫn, chi phí token) · Tương thích với tính năng khác (lấy dữ liệu có cấu trúc kèm citations, dùng prompt caching với citations) · Các loại tài liệu (chọn loại tài liệu, văn bản thuần, PDF, nội dung tùy chỉnh) · Cấu trúc phản hồi (hỗ trợ streaming) · Các bước tiếp theo · Tính khả dụng.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/citations)
- [Hỗ trợ PDF](pdf-support.md)
- [Prompt caching](prompt-caching.md)
- [Structured outputs](structured-outputs.md)

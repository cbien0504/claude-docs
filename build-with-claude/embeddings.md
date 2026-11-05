---
title: Embeddings (tóm tắt)
source: https://platform.claude.com/docs/en/build-with-claude/embeddings
description: Text embeddings là biểu diễn số của văn bản cho phép đo độ tương đồng ngữ nghĩa; hướng dẫn giới thiệu embeddings, ứng dụng và cách dùng mô hình embedding cho tìm kiếm, gợi ý và phát hiện bất thường.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/build-with-claude/embeddings). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Anthropic không cung cấp mô hình embedding riêng. Một nhà cung cấp embeddings có nhiều mô hình và khả năng là Voyage AI (thuộc MongoDB), chuyên về mô hình embedding và reranker, gồm các mô hình đa dụng, đa phương thức, theo ngữ cảnh (contextualized) và theo lĩnh vực. Phần còn lại của hướng dẫn viết cho Voyage AI, nhưng bạn nên đánh giá nhiều nhà cung cấp embeddings để chọn cái hợp nhất với trường hợp sử dụng của mình.

## Các điểm chính

- **Tiêu chí chọn nhà cung cấp:**
  - Kích thước tập dữ liệu và độ chuyên biệt theo lĩnh vực: dữ liệu lớn hơn hoặc chuyên biệt hơn thường cho embeddings tốt hơn trong lĩnh vực đó.
  - Hiệu năng suy luận: tốc độ tra cứu embedding và độ trễ đầu-cuối, đặc biệt quan trọng với triển khai production quy mô lớn.
  - Khả năng tùy biến: tiếp tục huấn luyện trên dữ liệu riêng hoặc chuyên biệt hóa mô hình cho lĩnh vực hẹp, giúp cải thiện với từ vựng đặc thù.
- **Mô hình khả dụng:** Voyage AI cung cấp nhiều mô hình embedding văn bản; ví dụ `voyage-4-large` (thế hệ mới nhất, độ dài ngữ cảnh 32.000, số chiều embedding 1024 mặc định hoặc 256, 512, 2048) cho chất lượng truy hồi đa dụng và đa ngôn ngữ tốt nhất.
- **Bắt đầu với Voyage AI:** qua thư viện Python, HTTP API hoặc AWS Marketplace; có ví dụ quickstart, FAQ và giá.

## Các mục trong trang gốc

Trước khi triển khai embeddings · Cách lấy embeddings với Anthropic · Mô hình khả dụng · Bắt đầu với Voyage AI (thư viện Python, HTTP API, AWS Marketplace) · Ví dụ quickstart · FAQ · Giá.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/build-with-claude/embeddings)

---
title: Programmatic tool calling (tóm tắt)
source: https://platform.claude.com/docs/en/agents-and-tools/tool-use/programmatic-tool-calling
description: Để Claude gọi các công cụ của bạn từ code trong container thực thi code, giảm số vòng đi lại của mô hình và lượng token trong workflow nhiều công cụ.
type: summary
---

> Đây là bản tóm tắt không chính thức bằng tiếng Việt, không phải bản dịch toàn văn. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/programmatic-tool-calling). Khi có khác biệt, bản tiếng Anh là bản đúng.

## Tóm tắt

Với programmatic tool calling, Claude gọi các công cụ của bạn từ trong code chạy ở container thực thi code, thay vì mỗi lệnh gọi là một vòng đi lại riêng với mô hình. Cách này giúp cắt giảm số vòng đi lại và lượng token trong các workflow dùng nhiều công cụ.

## Các điểm chính

- **Khái niệm cốt lõi:**
  - Trường `allowed_callers` cho biết ai được gọi công cụ.
  - Trường `caller` trong phản hồi cho biết lệnh gọi do ai thực hiện.
  - Vòng đời container.
- **Quy trình ví dụ gồm 5 bước:** request ban đầu; phản hồi API có lệnh gọi công cụ; cung cấp kết quả công cụ; lệnh gọi công cụ tiếp theo hoặc hoàn tất; phản hồi cuối cùng.
- **Mẫu nâng cao:** xử lý theo lô với vòng lặp, kết thúc sớm, chọn công cụ có điều kiện, lọc dữ liệu.
- **Định dạng phản hồi:** lệnh gọi công cụ theo chương trình, xử lý kết quả công cụ, hoàn tất thực thi code; ngoài ra có mục xử lý lỗi.

## Các mục trong trang gốc

Quick start · Cách programmatic tool calling hoạt động · Khái niệm cốt lõi · Quy trình ví dụ · Mẫu nâng cao · Định dạng phản hồi · Xử lý lỗi · và các mục còn lại của trang gốc.

## Xem thêm

- [Bản gốc](https://platform.claude.com/docs/en/agents-and-tools/tool-use/programmatic-tool-calling)
- [Code execution tool](code-execution-tool.md)
- [Quản lý ngữ cảnh của công cụ](manage-tool-context.md)
- [Xử lý lệnh gọi công cụ](handle-tool-calls.md)

# 📋 BÁO CÁO RÀ SOÁT CHI TIẾT: NHOM-17-TMDT.docx

> Rà soát bởi AI Assistant | Ngày: 17/03/2026

---

## 📌 TỔNG QUAN

Báo cáo gồm 3 chương chính + Lời nói đầu + Kết luận, cấu trúc tổng thể **khá tốt**, logic rõ ràng. Tuy nhiên, có một số vấn đề cần khắc phục về **độ chính xác nội dung**, **tính nhất quán giữa các phần**, **trích nguồn**, và **trình bày**.

---

## 🔴 CHƯƠNG 1: Giới thiệu về nhận diện đánh giá giả mạo

### ✅ Điểm tốt
- Phân loại 3 hình thức đánh giá giả mạo rõ ràng, có ví dụ thực tế minh họa
- Trình bày các phương pháp truyền thống và tự động logic, từ đơn giản đến phức tạp
- Phần tiêu chí đánh giá hiệu quả hệ thống đầy đủ (Accuracy, Precision, Recall, F1)

### ⚠️ Vấn đề cần sửa

| # | Vị trí | Loại lỗi | Mô tả | Đề xuất sửa |
|---|--------|-----------|-------|-------------|
| 1 | P41 | Ngữ nghĩa | Định nghĩa "đánh giá giả mạo" hơi dài, nên tách riêng phần "review ảo" với "fake review" | Gọn lại phần định nghĩa, tách 2 đoạn |
| 2 | P70 | Dấu câu | Cuối câu có dấu phẩy thừa: `"...trên nhiều sản phẩm khác biệt,."` | Bỏ dấu phẩy: `"...trên nhiều sản phẩm khác biệt."` |
| 3 | P73 | Lỗi chính tả | `"Shoppe"` → sai tên thương hiệu | Sửa thành `"Shopee"` |
| 4 | P78 | Thiếu trích nguồn | Hình 1.1 không có nguồn trích dẫn | Thêm nguồn gốc của hình |
| 5 | P94 | Thiếu trích nguồn | Hình 1.2 không có nguồn trích dẫn | Thêm nguồn gốc |
| 6 | P82–P90 | Công thức bị lỗi | Các ký hiệu xác suất `P(c|x)`, `P(c)`, `P(x|c)`, `P(x)` bị mất format | Kiểm tra lại format công thức Naïve Bayes trong Word |
| 7 | P95 | Thiếu chính xác | Mô tả SVM dùng ví dụ "quả táo quả lê đặt trên mặt bán" → thiếu chữ `"bàn"` | Sửa: `"mặt bàn"` |
| 8 | P102 | Thiếu trích nguồn | Số liệu "94,92%" trong xác minh chữ ký không được trích nguồn | Thêm số [nguồn] |
| 9 | P117 | Nội dung chưa chính xác | Phần LLMs: "Các mô hình ngôn ngữ lớn (LLMs) như LLaMA hay ChatGPT" nhưng report lại nói "kết hợp với PhoBERT, LLaMA có thể tận dụng..." → miêu tả chưa đúng cách LLaMA hoạt động | Sửa lại: LLaMA không "kết hợp" với PhoBERT theo cách đó; nên nói LLaMA có thể fine-tune riêng để phát hiện spam |
| 10 | P122 | Dấu câu thừa | `"...và hành vi bất thường,."` → dấu phẩy thừa trước dấu chấm | Bỏ dấu phẩy |
| 11 | P133 | Nhầm thuật ngữ | `"Độ đặc hiệu (Precision)"` → Precision không phải "Độ đặc hiệu" | Sửa: Precision = **Độ chính xác dự đoán** (hoặc giữ nguyên tiếng Anh). "Độ đặc hiệu" (Specificity) là khái niệm khác |

---

## 🔴 CHƯƠNG 2: Phương pháp nghiên cứu (⚠️ TRỌNG TÂM RÀ SOÁT)

### ✅ Điểm tốt
- Trình bày kiến trúc PhoBERT rất chi tiết (Transformer, Multi-Head Attention, encoder)
- Phần XGBoost có công thức toán học đầy đủ (hàm mất mát, regularization, gradient)
- Kiến trúc two-stage được giải thích rõ ràng với bảng so sánh 3 phương pháp
- Ví dụ minh họa cách hoạt động PhoBERT + XGBoost rất trực quan

### ⚠️ Vấn đề cần sửa

| # | Vị trí | Loại lỗi | Mô tả | Đề xuất sửa |
|---|--------|-----------|-------|-------------|
| 1 | P145–P147 | **Trùng lặp nội dung** | Đoạn P145 (phần 2.1 Tổng quan) và P147 (phần 2.1.1 PhoBERT) gần như **giống hệt nhau**: *"PhoBERT là một mô hình ngôn ngữ sâu..."* | **Xóa bỏ 1 trong 2**, giữ đoạn ở mục 2.1.1 và viết lại P145 thành tổng quan ngắn gọn |
| 2 | P146 | Lỗi heading | Heading mục 2.1.1 viết `"đặc trừng"` (sai) | Sửa: `"đặc trưng"` |
| 3 | P172 | Văn phong | `"BERT chặt transformer làm đôi và chỉ lấy phần Encoder..."` và `"Tóm lai chỉ còn cái đoạn mà nhét câu văn bản vào..."` → quá nói trò chuyện, không phù hợp báo cáo khoa học | Sửa: *"BERT chỉ sử dụng nửa Encoder của Transformer, tập trung vào việc mã hóa..."*; *"Tóm lại, kiến trúc chỉ giữ lại phần xử lý đầu vào văn bản và đầu ra là các encoder output"* |
| 4 | P182 | Sai ngữ cảnh | `"...ngữ cảnh trước ('sản phẩm này rất') và sau ('em không hài lòng')"` → ví dụ câu gốc dùng "tôi" nhưng đoạn sau ghi "em" | Sửa: `"tôi không hài lòng"` (nhất quán với câu ví dụ gốc) |
| 5 | P183 | Thiếu trích nguồn | Thông tin "20GB dữ liệu tiếng Việt (1GB Wikipedia, 19GB Vietnamese news)" cần trích nguồn từ bài báo PhoBERT gốc | Thêm [nguồn]: Nguyen & Tuan, 2020 |
| 6 | Bảng 2.1 | **Không nhất quán** | Max length trong bảng = **128**, nhưng đoạn P339 ghi `max_length=256` | Thống nhất lại: trong code thực tế dùng 256 hay 128? Nếu 256 thì sửa bảng |
| 7 | P215 | **Sai số liệu** | `"780 chiều (768 chiều từ PhoBERT + 12 đặc trưng thủ công)"` → 768 + 12 = **780**, đúng. Nhưng đoạn P247 viết `"780 đặc trưng (768 PhoBERT + 12 thủ công)"` → cũng đúng. **OK, nhất quán** | Không cần sửa |
| 8 | P231–P236 | Công thức bị thiếu | Nhiều công thức toán bị mất ký hiệu (do Word không render đúng Unicode math) | Kiểm tra lại toàn bộ phần công thức trong Word, đảm bảo ký hiệu hiển thị đầy đủ |
| 9 | P254–P258 | Thiếu trích nguồn | Các tham chiếu `[1]`, `[4]` xuất hiện nhưng **không có trang Tài liệu tham khảo** | Bổ sung trang Tài liệu tham khảo (đang tạo bên dưới) |
| 10 | P303 | Nhầm số liệu | Ghi "3 epoch" nhưng Bảng 2.1 ghi "3-5 epoch" | Thống nhất: nếu thực tế chạy 3 epoch thì sửa bảng thành "3" |
| 11 | P293 | Trình bày | `"Vector kết hợp (780 chiều) = Embedding fine-tuned (768 chiều) + Đặc trưng thủ công (12 chiều)"` nên format thành công thức | Dùng format equation trong Word thay vì plain text |
| 12 | P295 | Sai đánh số | Bảng được gọi là `"Bảng 2.3"` nhưng lại viết `"Bảng phân tích 12 đặc trưng thống kê thủ công"` → nên đánh lại số bảng cho nhất quán | Kiểm tra số thứ tự tất cả bảng |
| 13 | P342 | **Mâu thuẫn nội dung** | Ghi `"torch.no_grad()"` (không tính gradient = đóng băng PhoBERT) nhưng **phương pháp chính là fine-tuned** | Đoạn này mô tả bước **trích xuất embedding** SAU KHI đã fine-tune, nên cần làm rõ: *"Sau khi hoàn tất fine-tuning, mô hình được chuyển sang chế độ không tính gradient (eval mode) để trích xuất embedding"* |
| 14 | Bảng 2.4 | Sai đánh số | Bảng này được gọi "Bảng 2.4" ở mục lục nhưng nội dung là "So sánh ba phương pháp" → thực chất giống "Bảng 2.5" ở phần sau | Kiểm tra và thống nhất đánh số |

---

## 🔴 CHƯƠNG 3: Triển khai thực nghiệm

### ✅ Điểm tốt
- Kết quả thực nghiệm chi tiết, bảng số liệu rõ ràng
- So sánh với baseline đầy đủ, công bằng
- Phần triển khai web demo KMA-SHOP thực tế, ấn tượng

### ⚠️ Vấn đề cần sửa

| # | Vị trí | Loại lỗi | Mô tả | Đề xuất sửa |
|---|--------|-----------|-------|-------------|
| 1 | Bảng 3.4 (Table 11) | **Số liệu không khớp** | BiLSTM baseline: report ghi **81,21%** Accuracy, nhưng paper gốc (ViSpamReviews, ArXiv 2207.14636) ghi PhoBERT đạt **86,89% F1-macro** | Kiểm tra lại bảng so sánh, đối chiếu với paper gốc. Lưu ý paper gốc chỉ báo cáo F1-macro, không báo cáo Accuracy |
| 2 | Bảng 3.4 | Thiếu rõ ràng | Các giá trị `[1]` references nhưng không có trang tài liệu tham khảo | Bổ sung trang Tài liệu tham khảo |
| 3 | P463 | Dấu chấm thừa | `"...REST API endpoint nhận và xử lý đánh giá; phần Frontend..."` rồi dòng P464 có dấu chấm đơn lẻ `"."` | Xóa dấu chấm thừa |
| 4 | P471 | **Trùng đánh số hình** | `"Hình 3.1"` xuất hiện **hai lần**: một lần ở mục lục (P10) – "Giao diện bình luận" và một lần ở P464 – "Giao diện phát hiện..." | Đánh lại số hình: Hình 3.1 → chỗ đầu, Hình 3.2 → chỗ sau, Hình 3.3 → Admin Dashboard |
| 5 | P493 | **Mâu thuẫn Feature Importance** | P442 nói: *"20 đặc trưng quan trọng nhất toàn bộ đều thuộc PhoBERT (20/20 PhoBERT, 0 thủ công)"*. Nhưng P493 lại nói: *"avg_word_length, is_short_review, unique_word_ratio là dấu hiệu quan trọng nhất"* → đây đều là đặc trưng **thủ công**, mâu thuẫn với P442 | Sửa thống nhất. Nếu Feature Importance thực sự cho thấy 20/20 là PhoBERT thì P493 cần sửa lại ví dụ |
| 6 | P488 | Thiếu tên đề tài | Tên đề tài ở Kết luận thiếu chữ "XGBoost": `"PhoBERT trong việc phát hiện..."` nhưng tên đề tài đầy đủ là PhoBERT **và XGBoost** | Thêm: `"PhoBERT và XGBoost"` |
| 7 | Bảng 3.1 | Số liệu | Tổng = 19.870, tỷ lệ 72/8/20 → 14.306/1.590/3.974 = 19.870 ✅ | OK |

---

## 🟡 VẤN ĐỀ CHUNG TOÀN BÁO CÁO

### Trích nguồn
> [!CAUTION]
> Báo cáo sử dụng `[1]`, `[4]` ở nhiều chỗ nhưng **hoàn toàn không có trang Tài liệu tham khảo**. Đây là lỗi nghiêm trọng nhất cần bổ sung ngay.

### Nhất quán thuật ngữ
- Chương 1 hay dùng "đánh giá giả mạo", "review ảo" → OK
- Chương 2 dùng thêm "spam review" → OK nhưng nên ghi chú thống nhất từ đầu
- Xen kẽ giữa "chúng em" và "nghiên cứu này" → nên dùng nhất quán "nhóm nghiên cứu" hoặc "chúng em"

### Hình ảnh
- Nhiều chỗ ghi `[Normal]` rỗng trước hình → có thể hình bị mất khi convert
- Cần kiểm tra tất cả hình vẽ hiển thị đúng trong file Word gốc

### Danh mục bảng
- Bảng 2.3 ở mục lục ghi "So sánh ba phương pháp" nhưng nội dung là bảng 12 đặc trưng thủ công → cần sửa lại mục lục
- Bảng 2.5 ở nội dung là "So sánh hiệu suất các mô hình" nhưng ở mục lục là "Bảng 2.4"

---

## 📊 ĐÁNH GIÁ TỔNG HỢP

| Tiêu chí | Điểm (1-10) | Nhận xét |
|----------|-------------|---------|
| Cấu trúc logic | 8/10 | Tốt, 3 chương rõ ràng |
| Nội dung lý thuyết | 7/10 | Chi tiết nhưng có chỗ trùng lặp và sao chép từ nguồn gốc |
| Phương pháp (Ch.2) | 8/10 | Rất chi tiết, có công thức toán đầy đủ |
| Kết quả (Ch.3) | 8/10 | Số liệu cụ thể, so sánh công bằng |
| Trích nguồn | **3/10** | **Thiếu trang Tài liệu tham khảo - lỗi nghiêm trọng** |
| Chính tả & trình bày | 6/10 | Có lỗi chính tả, dấu câu, format công thức |
| Tính nhất quán | 6/10 | Mâu thuẫn Feature Importance, trùng nội dung Ch.2 |

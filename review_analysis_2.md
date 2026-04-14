# 📋 BÁO CÁO RÀ SOÁT CHI TIẾT: NHOM-17-TMDT.docx

> Rà soát ngày 17/03/2026 | Tổng số vấn đề: ~30 | Mỗi lỗi kèm **đoạn văn sửa đầy đủ** để anh copy vào Word

---

## 🔴 CHƯƠNG 1: Giới thiệu về nhận diện đánh giá giả mạo

---

### Lỗi 1 – P70: Dấu phẩy thừa trước dấu chấm

**Gốc:**
> ...hoặc lịch sử hoạt động chỉ hiển thị các bài viết đánh giá với nội dung tương tự nhau trên nhiều sản phẩm khác biệt**,.**

**Sửa thành:**
> ...hoặc lịch sử hoạt động chỉ hiển thị các bài viết đánh giá với nội dung tương tự nhau trên nhiều sản phẩm khác biệt**.**

---

### Lỗi 2 – P73: Sai tên thương hiệu "Shoppe"

**Gốc:**
> ...với khối lượng dữ liệu khổng lồ phát sinh mỗi giây trên các nền tảng như **Shoppe**, Lazada hay Tiki...

**Sửa thành:**
> ...với khối lượng dữ liệu khổng lồ phát sinh mỗi giây trên các nền tảng như **Shopee**, Lazada hay Tiki...

---

### Lỗi 3 – P95: Thiếu chữ "bàn"

**Gốc:**
> Trong ví dụ quả táo quả lê đặt trên mặt **bán**, margin chính là khoảng cách giữa cây que...

**Sửa thành:**
> Trong ví dụ quả táo quả lê đặt trên mặt **bàn**, margin chính là khoảng cách giữa cây que...

---

### Lỗi 4 – P102: Số liệu 94,92% thiếu trích nguồn

**Gốc:**
> Trong thực tế nghiên cứu, XGBoost đã chứng minh hiệu quả khi đạt tỷ lệ chính xác 94,92% trong xác minh chữ ký, vượt qua cả các bộ phân loại truyền thống như SVM hay các phương pháp học máy thông thường khác.

**Sửa thành:**
> Trong thực tế nghiên cứu, XGBoost đã chứng minh hiệu quả khi đạt tỷ lệ chính xác 94,92% trong xác minh chữ ký ngoại tuyến trên bộ dữ liệu CEDAR **[15]**, vượt qua cả các bộ phân loại truyền thống như SVM (94,09%) hay các phương pháp học máy thông thường khác.

> [!NOTE]
> Nguồn `[15]`: Trần Minh Nhân, Trần Đại Gia Khánh & Hồ Phước Tiến (2022). *Xác minh chữ ký dựa trên kỹ thuật học sâu*. Tạp chí KH&CN – ĐH Đà Nẵng, 20(7), tr. 71–75. (Bảng 3, Mô hình Embedding + XGBoost)

---

### Lỗi 5 – P117: Mô tả LLaMA không chính xác

**Gốc:**
> LLaMA: Là một mô hình ngôn ngữ lớn có khả năng học sâu từ dữ liệu đa dạng. Khi kết hợp với PhoBERT, LLaMA có thể tận dụng cả đặc trưng ngôn ngữ của tiếng Việt và sức mạnh của mô hình lớn để phát hiện đánh giá giả chính xác hơn.

**Sửa thành:**
> LLaMA: Là một mô hình ngôn ngữ lớn (Large Language Model) do Meta phát triển, có khả năng hiểu và sinh văn bản đa ngôn ngữ nhờ được huấn luyện trên tập dữ liệu khổng lồ. Về mặt lý thuyết, LLaMA có thể được tinh chỉnh (fine-tuning) riêng cho bài toán phát hiện đánh giá giả mạo tiếng Việt. Tuy nhiên, do yêu cầu tài nguyên tính toán rất lớn và chưa được tối ưu hóa đặc thù cho tiếng Việt như PhoBERT, việc áp dụng LLaMA cho bài toán này đòi hỏi nghiên cứu bổ sung.

---

### Lỗi 6 – P122: Dấu phẩy thừa trước dấu chấm

**Gốc:**
> ...các hệ thống AI phân tích ngôn ngữ tự nhiên để nhận diện sự trùng lặp, lối viết máy móc và hành vi bất thường**,.**

**Sửa thành:**
> ...các hệ thống AI phân tích ngôn ngữ tự nhiên để nhận diện sự trùng lặp, lối viết máy móc và hành vi bất thường**.**

---

### Lỗi 7 – P133: Nhầm thuật ngữ Precision

**Gốc:**
> Độ đặc hiệu (Precision): Mức độ tin cậy khi hệ thống kết luận một tin tức là giả, giúp giảm thiểu việc báo động nhầm các nguồn tin chính thống.

**Sửa thành:**
> Độ chính xác dự đoán (Precision): Trong số những đánh giá mà hệ thống dự đoán là giả, tỷ lệ thực sự đúng là bao nhiêu. Precision cao giúp giảm thiểu việc gắn nhầm cờ các đánh giá thật thành giả mạo.

> [!WARNING]
> "Độ đặc hiệu" (Specificity) trong y khoa/thống kê là khái niệm khác: TN/(TN+FP). Precision = TP/(TP+FP). Không nên dùng lẫn.

---

## 🔴 CHƯƠNG 2: Phương pháp nghiên cứu (TRỌNG TÂM)

---

### Lỗi 8 – P145 & P147: Trùng lặp nội dung

**Gốc P145 (mục 2.1):**
> PhoBERT là một mô hình ngôn ngữ sâu, được phát triển dựa trên kiến trúc Transformer, và đã được huấn luyện trước (pre-trained) trên một tập dữ liệu lớn tiếng Việt bởi nhóm VinAI. Vai trò chính của PhoBERT trong hệ thống là trích xuất các đặc trưng ngữ nghĩa từ văn bản đánh giá sản phẩm, chuyển đổi dữ liệu thô thành dạng biểu diễn số học có ý nghĩa.

**Gốc P147 (mục 2.1.1):**
> PhoBERT là một mô hình ngôn ngữ sâu, được phát triển dựa trên kiến trúc Transformer, và đã được huấn luyện trước (pre-trained) trên một tập dữ liệu lớn tiếng Việt bởi nhóm VinAI. Vai trò chính của PhoBERT trong hệ thống là trích xuất các đặc trưng ngữ nghĩa từ văn bản thông tin, chuyển đổi dữ liệu thô thành dạng biểu diễn số học có ý nghĩa.

**Sửa P145 thành (tóm gọn, tránh trùng lặp):**
> Phương pháp đề xuất kết hợp hai công cụ chính: PhoBERT – mô hình ngôn ngữ được huấn luyện trước cho tiếng Việt, chịu trách nhiệm trích xuất đặc trưng ngữ nghĩa từ văn bản [3]; và XGBoost – thuật toán Gradient Boosting dựa trên cây quyết định, đảm nhiệm phân loại đánh giá thành "thật" hoặc "giả" [4]. Chi tiết về từng thành phần sẽ được trình bày trong các mục tiếp theo.

**Giữ nguyên P147** (nhưng sửa "văn bản thông tin" → "văn bản đánh giá sản phẩm")

---

### Lỗi 9 – P146: Heading sai chính tả "đặc trừng"

**Gốc:**
> 2.1.1. PhoBERT – mô hình trích xuất đặc **trừng** ngữ nghĩa

**Sửa thành:**
> 2.1.1. PhoBERT – mô hình trích xuất đặc **trưng** ngữ nghĩa

---

### Lỗi 10 – P172: Văn phong quá khẩu ngữ, không phù hợp báo cáo khoa học

**Gốc:**
> PhoBERT chỉ sử dụng phần encoder của Transformer, tức là tập trung vào việc mã hóa văn bản thành các biểu diễn số học mà không sinh ra văn bản mới. **BERT chặt transformer làm đôi và chỉ lấy phần Encoder bên trái và bỏ đi phần Decoder bên phải. Tóm lai chỉ còn cái đoạn mà nhét câu văn bản vào và đầu ra là các encoder output** như hình:

**Sửa thành:**
> PhoBERT chỉ sử dụng phần Encoder của kiến trúc Transformer, tức là tập trung vào việc mã hóa văn bản thành các biểu diễn số học mà không sinh ra văn bản mới. Cụ thể, BERT loại bỏ hoàn toàn khối Decoder (phần giải mã) của Transformer gốc và chỉ giữ lại khối Encoder (phần mã hóa). Nói cách khác, kiến trúc chỉ bao gồm phần nhận đầu vào là chuỗi văn bản đã được tokenize và đầu ra là các Encoder Output tương ứng, như minh họa trong hình dưới đây:

---

### Lỗi 11 – P182: Nhầm "em" thay vì "tôi" trong ví dụ

**Gốc:**
> ...BERT hiểu "tệ" là tính từ tiêu cực liên quan đến "sản phẩm" dựa trên cả ngữ cảnh trước ("sản phẩm này rất") và sau ("**em** không hài lòng").

**Sửa thành:**
> ...BERT hiểu "tệ" là tính từ tiêu cực liên quan đến "sản phẩm" dựa trên cả ngữ cảnh trước ("sản phẩm này rất") và sau ("**tôi** không hài lòng").

---

### Lỗi 12 – P183: Thông tin PhoBERT thiếu trích nguồn

**Gốc:**
> Huấn luyện trước của PhoBERT: PhoBERT được huấn luyện trên 20GB dữ liệu tiếng Việt (1GB từ Wikipedia corpus, 19GB từ Vietnamese news corpus), tương đương 145 triệu câu.

**Sửa thành:**
> Huấn luyện trước của PhoBERT: PhoBERT được huấn luyện trên 20GB dữ liệu tiếng Việt (1GB từ Wikipedia corpus, 19GB từ Vietnamese news corpus), tương đương 145 triệu câu **[3]**.

---

### Lỗi 13 – Bảng 2.1: max_length không nhất quán

**Bảng 2.1** ghi Max length = **128**, nhưng đoạn P339 ghi `max_length=256`.

> [!IMPORTANT]
> Nếu code thực tế dùng **256** thì sửa Bảng 2.1: `Max length` → `256`. Nếu dùng 128 thì sửa P339. Anh kiểm tra notebook để xác nhận giá trị đúng.

---

### Lỗi 14 – P342: Mâu thuẫn torch.no_grad() với fine-tuning

**Gốc:**
> Sau khi văn bản đã được mã hóa, chúng em sử dụng mô hình PhoBERT để trích xuất đặc trưng ngữ nghĩa. Mô hình được chạy trong chế độ không tính gradient (torch.no_grad()) nhằm tiết kiệm bộ nhớ và tăng tốc độ xử lý, vì mục tiêu là trích xuất đặc trưng chứ không phải tinh chỉnh mô hình.

**Sửa thành:**
> Sau khi hoàn tất quá trình fine-tuning ở Giai đoạn 1, mô hình PhoBERT đã tinh chỉnh được chuyển sang chế độ đánh giá (eval mode) và không tính gradient (`torch.no_grad()`) để trích xuất đặc trưng ngữ nghĩa cho toàn bộ tập dữ liệu. Việc tắt gradient ở bước này nhằm tiết kiệm bộ nhớ GPU và tăng tốc độ xử lý, vì mục tiêu lúc này là trích xuất embedding chứ không phải tiếp tục tinh chỉnh mô hình.

---

### Lỗi 15 – Bảng 2.1 epoch: "3-5" vs thực tế "3"

**Bảng 2.1** ghi `Số epoch: 3-5`, nhưng P303 và Bảng 3.2 đều ghi thực tế chạy **3 epoch**.

**Sửa Bảng 2.1:** `Số epoch` → `3` (hoặc "3, với cơ chế dừng sớm")

---

## 🔴 CHƯƠNG 3: Triển khai thực nghiệm

---

### Lỗi 16 – P464: Dấu chấm đơn lẻ thừa

**Gốc (P463-P464):**
> ...phần Frontend là giao diện web mô phỏng sàn thương mại điện tử với đầy đủ tính năng đăng nhập, mua hàng và viết đánh giá.
> **.**

**Sửa:** Xóa dấu chấm đơn lẻ ở dòng P464.

---

### Lỗi 17 – Hình 3.1 trùng số (xuất hiện 2 lần)

- P464: `Hình 3.1. Giao diện phát hiện đánh giá giả mạo trên nền tảng KMA-SHOP`
- P471: `Hình 3.1. Giao diện bình luận của hệ thống trang Web demo`

**Sửa thành:**
- P464 → `Hình 3.1. Giao diện phát hiện đánh giá giả mạo trên nền tảng KMA-SHOP`
- P471 → `Hình 3.2. Giao diện bình luận của hệ thống trang Web demo`
- P474 → `Hình 3.3. Bảng điều khiển Admin Dashboard của hệ thống trang Web demo`

Đồng thời cập nhật **Danh mục hình vẽ** ở đầu báo cáo cho khớp.

---

### Lỗi 18 – P442 vs P493: Mâu thuẫn Feature Importance

**P442 viết:**
> Kết quả phân tích cho thấy trong số 20 đặc trưng có tầm quan trọng cao nhất, **toàn bộ đều thuộc nhóm chiều embedding** của PhoBERT đã tinh chỉnh (20/20 chiều PhoBERT, 0/20 đặc trưng thống kê).

**P493 viết:**
> Feature Importance cho thấy **avg_word_length, is_short_review, và unique_word_ratio** là các dấu hiệu quan trọng nhất của spam...

→ Đây là 3 đặc trưng **thủ công** (không phải PhoBERT), mâu thuẫn hoàn toàn với P442.

**Sửa P493 thành (nếu P442 đúng – top 20 toàn PhoBERT):**
> Khả năng giải thích: Khác với các mô hình Deep Learning thuần túy hoạt động như "hộp đen", phương pháp đề xuất cung cấp Feature Importance thông qua XGBoost, cho phép giải thích cụ thể tại sao mỗi đánh giá bị phân loại là spam. Kết quả cho thấy các chiều embedding PhoBERT đã tinh chỉnh chiếm ưu thế tuyệt đối trong top đặc trưng quan trọng nhất, phản ánh khả năng nắm bắt ngữ nghĩa chuyên biệt của mô hình sau quá trình fine-tuning. Bên cạnh đó, các đặc trưng thống kê thủ công như avg_word_length, is_short_review và unique_word_ratio cũng đóng vai trò bổ trợ, giúp hệ thống kiểm duyệt hoạt động minh bạch hơn.

---

### Lỗi 19 – P488: Tên đề tài thiếu "XGBoost"

**Gốc:**
> ...đề tài "Nghiên cứu ứng dụng mô hình **PhoBERT** trong việc phát hiện đánh giá giả mạo..."

**Sửa thành:**
> ...đề tài "Nghiên cứu ứng dụng mô hình **PhoBERT và XGBoost** trong việc phát hiện đánh giá giả mạo..."

---

## 🟡 VẤN ĐỀ CHUNG

---

### Lỗi 20 – Thiếu trang Tài liệu tham khảo

> [!CAUTION]
> Báo cáo dùng `[1]`, `[4]` ở nhiều nơi nhưng **hoàn toàn không có trang Tài liệu tham khảo**. Anh cần thêm 1 trang cuối cùng liệt kê tất cả 15 nguồn. Em đã tạo sẵn trong file [references.md](file:///C:/Users/Knowm/.gemini/antigravity/brain/696594b3-42ff-47c3-bd99-3dd56228d67d/references.md) – anh copy vào Word ở cuối báo cáo.

### Nhất quán xưng hô
Xen kẽ giữa "chúng em" và "nghiên cứu này" → nên dùng nhất quán **"nhóm nghiên cứu"** hoặc **"chúng em"** xuyên suốt.

### Danh mục bảng không khớp nội dung
- Bảng 2.3 ở mục lục ghi "So sánh ba phương pháp" → thực tế là bảng 12 đặc trưng thủ công
- Bảng 2.5 ở nội dung ghi "So sánh hiệu suất" → ở mục lục là "Bảng 2.4"
- **Cần cập nhật lại Word → References → Update All Fields** để tự đồng bộ

---

## 📊 ĐÁNH GIÁ TỔNG HỢP

| Tiêu chí | Điểm | Nhận xét |
|----------|:-----:|---------|
| Cấu trúc | 8/10 | Tốt, 3 chương rõ ràng |
| Nội dung lý thuyết | 7/10 | Chi tiết nhưng trùng lặp P145/P147 |
| Phương pháp (Ch.2) | 8/10 | Rất chi tiết, có công thức |
| Kết quả (Ch.3) | 8/10 | Số liệu cụ thể, so sánh công bằng |
| Trích nguồn | **3/10** | **Thiếu trang TLTK** |
| Chính tả | 6/10 | Có lỗi rải rác |
| Nhất quán | 6/10 | Mâu thuẫn Feature Importance |

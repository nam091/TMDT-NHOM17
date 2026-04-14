# TÀI LIỆU THAM KHẢO

> File này chứa danh sách tài liệu tham khảo đầy đủ cho báo cáo NHOM-17-TMDT.
> Các trích nguồn được đánh số `[1]`, `[2]`, ... và được sử dụng xuyên suốt trong 3 chương của báo cáo.

---

## Danh sách tài liệu tham khảo (Bibliography)

**[1]** Van Dinh, C., Luu, S. T., & Nguyen, A. G.-T. (2022). *Detecting Spam Reviews on Vietnamese E-Commerce Websites*. In: Nguyen, N. T., Tran, T. K., Tukayev, U., Hong, T.-P., Trawiński, B., Szczerbicki, E. (eds) Intelligent Information and Database Systems. ACIIDS 2022. Lecture Notes in Computer Science, vol 13758. Springer, Cham. pp. 595–607. https://doi.org/10.1007/978-3-031-21743-2_48
- ArXiv: https://arxiv.org/abs/2207.14636
- Dataset: https://github.com/sonlam1102/vispamdetection

**[2]** Van Dinh, C. & Luu, S. T. (2024). *Metadata Integration for Spam Reviews Detection on Vietnamese E-Commerce Websites*. International Journal of Asian Language Processing, 34(01). https://doi.org/10.1142/S2717554524500024
- ArXiv: https://arxiv.org/abs/2405.13292

**[3]** Nguyen, D. Q. & Nguyen, A. T. (2020). *PhoBERT: Pre-trained language models for Vietnamese*. In Findings of the Association for Computational Linguistics: EMNLP 2020, pp. 1037–1042. https://doi.org/10.18653/v1/2020.findings-emnlp.92
- GitHub: https://github.com/VinAIResearch/PhoBERT

**[4]** Chen, T. & Guestrin, C. (2016). *XGBoost: A Scalable Tree Boosting System*. In Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining (KDD '16), pp. 785–794. https://doi.org/10.1145/2939672.2939785

**[5]** Devlin, J., Chang, M.-W., Lee, K., & Toutanova, K. (2019). *BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding*. In Proceedings of the 2019 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies (NAACL-HLT), Volume 1, pp. 4171–4186. https://arxiv.org/abs/1810.04805

**[6]** Vaswani, A., Shazeer, N., Parmar, N., et al. (2017). *Attention Is All You Need*. In Advances in Neural Information Processing Systems 30 (NeurIPS 2017). https://arxiv.org/abs/1706.03762

**[7]** Akiba, T., Sano, S., Yanase, T., Ohta, T., & Koyama, M. (2019). *Optuna: A Next-generation Hyperparameter Optimization Framework*. In Proceedings of the 25th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining (KDD '19), pp. 2623–2631. https://doi.org/10.1145/3292500.3330701

**[8]** Hochreiter, S. & Schmidhuber, J. (1997). *Long Short-Term Memory*. Neural Computation, 9(8), pp. 1735–1780. https://doi.org/10.1162/neco.1997.9.8.1735

**[9]** Chung, J., Gulcehre, C., Cho, K., & Bengio, Y. (2014). *Empirical Evaluation of Gated Recurrent Neural Networks on Sequence Modeling*. arXiv preprint. https://arxiv.org/abs/1412.3555

**[10]** Kim, Y. (2014). *Convolutional Neural Networks for Sentence Classification*. In Proceedings of the 2014 Conference on Empirical Methods in Natural Language Processing (EMNLP), pp. 1746–1751. https://doi.org/10.3115/v1/D14-1181

**[11]** Bùi Trường Thịnh. (2025). *Ứng dụng PhoBERT và SVM trong nhận diện tin giả tiếng Việt*. Đồ án chuyên ngành, Trường Đại học Sài Gòn, Khoa Công nghệ Thông tin. (Tài liệu tham khảo nội bộ)

**[12]** Luật Bảo vệ quyền lợi người tiêu dùng, Số 19/2023/QH15 (2023). Quốc hội nước Cộng hòa Xã hội Chủ nghĩa Việt Nam.

**[13]** Wolf, T., Debut, L., Sanh, V., et al. (2020). *Transformers: State-of-the-Art Natural Language Processing*. In Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing: System Demonstrations, pp. 38–45. https://doi.org/10.18653/v1/2020.emnlp-demos.6

**[14]** Breiman, L. (2001). *Random Forests*. Machine Learning, 45(1), pp. 5–32. https://doi.org/10.1023/A:1010933404324

---

## Bảng ánh xạ trích nguồn trong báo cáo

> Bảng dưới đây chỉ ra nơi các trích nguồn `[n]` nên được sử dụng trong báo cáo.

| Ký hiệu | Tài liệu | Nơi sử dụng trong báo cáo |
|----------|-----------|---------------------------|
| `[1]` | Van Dinh et al. (2022) – ViSpamReviews | Ch.2: Nguồn dataset; Ch.3: Bảng so sánh baseline (BiLSTM, GRU, TextCNN, PhoBERT gốc) |
| `[2]` | Van Dinh & Luu (2024) – Metadata Integration | Ch.2: Phiên bản v2 dataset |
| `[3]` | Nguyen & Nguyen (2020) – PhoBERT | Ch.2: Mô tả PhoBERT, huấn luyện trên 20GB dữ liệu tiếng Việt |
| `[4]` | Chen & Guestrin (2016) – XGBoost | Ch.1: Random Forest; Ch.2: Công thức XGBoost, hàm mục tiêu, Eq.1 |
| `[5]` | Devlin et al. (2019) – BERT | Ch.2: Kiến trúc BERT, Masked LM, NSP |
| `[6]` | Vaswani et al. (2017) – Transformer | Ch.2: Kiến trúc Transformer, Multi-Head Attention |
| `[7]` | Akiba et al. (2019) – Optuna | Ch.2: Tối ưu hóa siêu tham số |
| `[8]` | Hochreiter & Schmidhuber (1997) – LSTM | Ch.1: Mô tả LSTM |
| `[9]` | Chung et al. (2014) – GRU | Ch.1: Mô tả GRU |
| `[10]` | Kim (2014) – CNN for text | Ch.1: Mô tả CNN trong NLP |
| `[11]` | Bùi Trường Thịnh (2025) | Tài liệu tham khảo gốc cho Ch.1 lý thuyết |
| `[12]` | Luật BVQLNTD 2023 | Ch.1: Khung pháp lý đánh giá giả mạo |
| `[13]` | Wolf et al. (2020) – Transformers lib | Ch.2: Sử dụng thư viện HuggingFace Transformers |
| `[14]` | Breiman (2001) – Random Forest | Ch.1: Mô tả Random Forest |

---

## Hướng dẫn chèn trích nguồn vào báo cáo

Dưới đây là các vị trí cụ thể cần bổ sung trích nguồn trong file Word:

### Chương 1
- **P43** (Luật BVQLNTD): thêm `[12]` sau "...cạnh tranh không lành mạnh"
- **P76** (Machine Learning): thêm `[14]` sau phần Random Forest
- **P82** (Naïve Bayes): không cần nguồn cụ thể (kiến thức phổ thông)
- **P95** (SVM): có thể thêm nguồn Cortes & Vapnik nếu muốn
- **P102** (94.92% xác minh chữ ký): **cần thêm nguồn cụ thể** (nghiên cứu nào?)
- **P104** (Deep Learning): thêm `[8]` cho LSTM, `[9]` cho GRU, `[10]` cho CNN
- **P114** (BERT): thêm `[5]`
- **P115** (PhoBERT): thêm `[3]`

### Chương 2
- **P145/P147** (PhoBERT overview): thêm `[3]`
- **P183** (20GB dữ liệu): thêm `[3]`
- **P213** (XGBoost): thêm `[4]`
- **P231** (Hàm mục tiêu XGBoost, paper gốc): thêm `[4]`
- **P254–P258** (Eq.1, shrinkage, sigmoid): thêm `[4]`
- **P264** (Optuna): thêm `[7]`
- **P313** (ViSpamReviews dataset): thêm `[1]`
- **P338** (transformers library): thêm `[13]`

### Chương 3
- **P456** (So sánh baseline): thêm `[1]` cho các kết quả baseline
- **Bảng 3.4** (BiLSTM, GRU, TextCNN, PhoBERT gốc): đã có `[1]` ✅

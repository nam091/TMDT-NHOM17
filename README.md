# Nghiên cứu ứng dụng mô hình PhoBERT và XGBoost trong việc phát hiện đánh giá giả mạo trên các sàn thương mại điện tử Việt Nam

[![Python](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0-EE4C2C.svg)](https://pytorch.org/)
[![Transformers](https://img.shields.io/badge/HuggingFace-Transformers%204.38-FFD21E.svg)](https://huggingface.co/docs/transformers)
[![XGBoost](https://img.shields.io/badge/XGBoost-2.0-006A4E.svg)](https://xgboost.readthedocs.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **Bài tập lớn môn An toàn Thương mại Điện tử**
> Học viện Kỹ thuật Mật mã – Khoa An toàn Thông tin

---

## 📋 Tổng quan

Đề tài nghiên cứu và triển khai hệ thống phát hiện đánh giá giả mạo (spam review) trên các sàn thương mại điện tử Việt Nam, sử dụng kiến trúc kết hợp hai giai đoạn (**two-stage pipeline**):

1. **Giai đoạn 1 – Fine-tuning PhoBERT**: Tinh chỉnh mô hình PhoBERT-base trên bộ dữ liệu ViSpamReviews để trích xuất embedding ngữ nghĩa chuyên biệt (768 chiều).
2. **Giai đoạn 2 – Phân loại bằng XGBoost**: Kết hợp embedding đã tinh chỉnh với 12 đặc trưng thống kê thủ công (tổng cộng 780 chiều), tối ưu siêu tham số bằng Optuna, và phân loại bằng XGBoost.

### Kết quả đạt được

| Chỉ số | Giá trị |
|--------|---------|
| **Accuracy** | **91,04%** |
| **F1-score (macro)** | **88,89%** |
| **AUC-ROC** | **0,9612** |
| Precision (Real / Spam) | 0,94 / 0,84 |
| Recall (Real / Spam) | 0,94 / 0,84 |

> Vượt trội so với baseline PhoBERT gốc của tác giả ViSpamReviews (Accuracy 90,01%, F1-macro 86,89%) và các mô hình DNN truyền thống (BiLSTM, GRU, TextCNN).

---

**Giảng viên hướng dẫn**: ThS. Nguyễn Thị Thu Thủy – Khoa An toàn Thông tin, Học viện Kỹ thuật Mật mã

---

## 📁 Cấu trúc thư mục

```
Phobert+XGBoost/
├── README.md                          # Mô tả dự án
└── finetuned_xgboost.ipynb            # Notebook thực nghiệm (Google Colab)
```

---

## 🏗️ Kiến trúc hệ thống

```
┌──────────────────────────────────────────────────────────────────┐
│                    PIPELINE PHÁT HIỆN SPAM                       │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│  Văn bản đánh giá ─► Tiền xử lý ─► Tokenizer PhoBERT           │
│                                          │                       │
│  ┌─────────────────────── Giai đoạn 1 ──┼──────────────────────┐ │
│  │  PhoBERT-base (Fine-tuned)           │                      │ │
│  │  12 tầng Transformer                 ▼                      │ │
│  │  135M tham số        ──►  [CLS] Embedding (768 chiều)       │ │
│  └──────────────────────────────────────┬──────────────────────┘ │
│                                         │                        │
│  ┌──────────────────────────────────────┼──────────────────────┐ │
│  │  12 Đặc trưng thủ công              │                      │ │
│  │  (rating, độ dài, emoji,             ▼                      │ │
│  │   từ lặp, dấu câu...)  ──► Concatenate ──► Vector 780 chiều│ │
│  └──────────────────────────────────────┬──────────────────────┘ │
│                                         │                        │
│  ┌─────────────────────── Giai đoạn 2 ──┼──────────────────────┐ │
│  │  XGBoost Classifier                  │                      │ │
│  │  (Tối ưu bằng Optuna)               ▼                      │ │
│  │  549 cây, max_depth=9  ──►  Real (0) / Spam (1)            │ │
│  │  + Feature Importance                                       │ │
│  └─────────────────────────────────────────────────────────────┘ │
└──────────────────────────────────────────────────────────────────┘
```

---

## 📊 Bộ dữ liệu

Sử dụng bộ dữ liệu **ViSpamReviews** từ nghiên cứu của Van Dinh, Luu & Nguyen (2022):

- **Nguồn**: [sonlam1102/vispamdetection](https://github.com/sonlam1102/vispamdetection)
- **HuggingFace**: [sonlam1102/vispamdetection](https://huggingface.co/datasets/sonlam1102/vispamdetection)

| Tập dữ liệu | Số lượng | Tỷ lệ | Mục đích |
|-------------|---------|--------|---------|
| Train | 14.306 | 72,0% | Huấn luyện mô hình |
| Dev | 1.590 | 8,0% | Tinh chỉnh, dừng sớm, tối ưu Optuna |
| Test | 3.974 | 20,0% | Đánh giá hiệu suất cuối cùng |
| **Tổng** | **19.870** | **100%** | |

Mỗi mẫu gồm: `rating` (1-5), `comment` (tiếng Việt), `label` (0=Real, 1=Spam), `SpamLabel` (0-3).

---

## ⚙️ Hướng dẫn tái tạo thực nghiệm

### Yêu cầu môi trường
- **Nền tảng**: Google Colaboratory (Colab)
- **GPU**: NVIDIA Tesla T4 (14,6 GB VRAM) — chọn chế độ GPU trong Runtime
- **Python**: ≥ 3.10

### Quy trình thực thi

1. Truy cập [Google Colab](https://colab.research.google.com/) và upload file `finetuned_xgboost.ipynb`
2. Chọn **Runtime → Change runtime type → GPU (T4)**
3. Chạy tuần tự từng cell — toàn bộ thư viện phụ thuộc sẽ được cài đặt tự động trong notebook
4. Kết quả huấn luyện và đánh giá sẽ được hiển thị trực tiếp tại các cell output

---

## 🔬 Cấu hình huấn luyện

### Giai đoạn 1: Fine-tuning PhoBERT

| Tham số | Giá trị |
|---------|---------|
| Mô hình cơ sở | `vinai/phobert-base` (135M params) |
| Learning rate | 2×10⁻⁵ |
| Optimizer | AdamW (weight decay 0.01) |
| Batch size | 16 |
| Số epoch | 3 |
| Max length | 256 tokens |
| LR Scheduler | Linear Warmup + Decay |
| Mixed Precision | FP16 |
| Thời gian | ~7 phút (Tesla T4) |

### Giai đoạn 2: XGBoost (tối ưu Optuna)

| Siêu tham số | Khoảng tìm kiếm | Giá trị tối ưu |
|-------------|-----------------|----------------|
| n_estimators | 100 – 600 | 549 |
| max_depth | 3 – 10 | 9 |
| learning_rate | 0.01 – 0.3 | 0.0446 |
| subsample | 0.6 – 1.0 | 0.8952 |
| colsample_bytree | 0.3 – 0.8 | 0.4356 |
| Số trial Optuna | – | 60 |
| Thời gian | – | ~62 phút (CPU) |

---

## 📈 So sánh hiệu suất

| Phương pháp | Accuracy (%) | F1-macro (%) | Giải thích được |
|-------------|-------------|-------------|----------------|
| BiLSTM [1] | 81,21 | 74,97 | ❌ |
| GRU [1] | 81,74 | 75,84 | ❌ |
| TextCNN [1] | 83,30 | 77,04 | ❌ |
| BERT4News [1] | 86,39 | 81,20 | ❌ |
| PhoBERT đóng băng + XGBoost | 87,64 | 83,52 | ✅ |
| PhoBERT (tác giả) [1] | 90,01 | 86,89 | ❌ |
| PhoBERT Fine-tuned (standalone) | 90,92 | 88,63 | ❌ |
| **PhoBERT FT + XGBoost (đề xuất)** | **91,04** | **88,89** | **✅** |

---

## 🌐 Triển khai Demo

Hệ thống được triển khai thử nghiệm trên **KMA-SHOP**: [https://shop.kamavn.tech](https://shop.kamavn.tech)

**Tính năng:**
- Kiểm duyệt AI tự động khi gửi đánh giá
- Badge xanh lá (Real) / đỏ (Spam) kèm độ tin cậy
- Admin Dashboard quản lý đánh giá bị gắn cờ
- Feature Importance giải thích quyết định phân loại

---

## 📚 Tài liệu tham khảo chính

```bibtex
@InProceedings{VanDinh2022ViSpam,
  author    = {Van Dinh, Co and Luu, Son T. and Nguyen, Anh Gia-Tuan},
  title     = {Detecting Spam Reviews on Vietnamese E-Commerce Websites},
  booktitle = {Intelligent Information and Database Systems (ACIIDS 2022)},
  year      = {2022},
  publisher = {Springer},
  pages     = {595--607},
  doi       = {10.1007/978-3-031-21743-2_48}
}

@article{Nguyen2020PhoBERT,
  author  = {Nguyen, Dat Quoc and Nguyen, Anh Tuan},
  title   = {PhoBERT: Pre-trained language models for Vietnamese},
  journal = {Findings of EMNLP 2020},
  year    = {2020},
  pages   = {1037--1042},
  doi     = {10.18653/v1/2020.findings-emnlp.92}
}

@InProceedings{Chen2016XGBoost,
  author    = {Chen, Tianqi and Guestrin, Carlos},
  title     = {XGBoost: A Scalable Tree Boosting System},
  booktitle = {Proceedings of KDD 2016},
  year      = {2016},
  pages     = {785--794},
  doi       = {10.1145/2939672.2939785}
}
```

---

## 📄 Giấy phép

Dự án này được phát triển cho mục đích học thuật trong khuôn khổ bài tập lớn môn **An toàn Thương mại Điện tử**, Học viện Kỹ thuật Mật mã, năm học 2024–2025.

Bộ dữ liệu ViSpamReviews thuộc bản quyền của tác giả gốc. Vui lòng liên hệ [sonlt@uit.edu.vn](mailto:sonlt@uit.edu.vn) để xin quyền sử dụng dataset.

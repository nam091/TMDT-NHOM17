# CÂU 2 (4 điểm) — BÀI LÀM

**Mã SV:** AT190557 → **M = 557**

## Phần 1: Xác định đường đi từ A đến Z qua chuỗi xáo trộn Mix

Dựa vào sơ đồ Mix Network gồm 3 lớp (9 nút Mix), xác định đường đi của thông điệp M từ khách hàng A đến cổng thanh toán Z:

**Đường đi:** A → Mix 4 → Mix 8 → Mix 9 → Z

**Quá trình mã hóa và truyền tin:**

Gọi PK_i, SK_i lần lượt là khóa công khai và khóa bí mật của nút Mix thứ i.

**A thực hiện mã hóa lớp (từ trong ra ngoài):**

- C₀ = E(PK_Z, M) — Mã hóa M bằng khóa công khai của Z
- C₁ = E(PK₉, C₀) — Mã hóa bằng khóa công khai Mix 9
- C₂ = E(PK₈, C₁) — Mã hóa bằng khóa công khai Mix 8
- C₃ = E(PK₄, C₂) — Mã hóa bằng khóa công khai Mix 4

A gửi C₃ vào mạng.

**Quá trình giải mã tại mỗi nút:**

| Nút | Nhận | Giải mã | Chuyển tiếp |
|-----|------|---------|-------------|
| Mix 4 | C₃ | D(SK₄, C₃) = C₂ | → Mix 8 |
| Mix 8 | C₂ | D(SK₈, C₂) = C₁ | → Mix 9 |
| Mix 9 | C₁ | D(SK₉, C₁) = C₀ | → Z |
| Z | C₀ | D(SK_Z, C₀) = **M** | Nhận được bản rõ |

Tại mỗi nút Mix, các thông điệp từ nhiều nguồn được **xáo trộn thứ tự** trước khi chuyển tiếp → đảm bảo tính ẩn danh.

---

## Phần 2: Mã hóa RSA tại cổng thanh toán Z

**Cho:** M = 557, p = 61, q = 53, e = 17

### Bước 1: Tính n

n = p × q = 61 × 53 = **3233**

### Bước 2: Tính φ(n)

φ(n) = (p − 1)(q − 1) = 60 × 52 = **3120**

### Bước 3: Kiểm tra e

gcd(17, 3120) = 1 ✓ → e = 17 hợp lệ

### Bước 4: Tìm d sao cho e·d ≡ 1 (mod 3120)

Áp dụng thuật toán Euclid mở rộng:

```
3120 = 183 × 17 + 9
  17 =   1 ×  9 + 8
   9 =   1 ×  8 + 1
   8 =   8 ×  1 + 0
```

Thế ngược:

```
1 = 9 − 1 × 8
  = 9 − 1 × (17 − 1 × 9)
  = 2 × 9 − 17
  = 2 × (3120 − 183 × 17) − 17
  = 2 × 3120 − 367 × 17
```

⇒ d ≡ −367 (mod 3120) = 3120 − 367 = **2753**

Thử lại: 17 × 2753 = 46801 = 15 × 3120 + 1 ✓

### Bước 5: Xác định cặp khóa

- **Khóa công khai:** (e, n) = **(17, 3233)**
- **Khóa bí mật:** (d, n) = **(2753, 3233)**

### Bước 6: Mã hóa

C = M^e mod n = 557^17 mod 3233 = **760**

### Bước 7: Giải mã (kiểm chứng)

M' = C^d mod n = 760^2753 mod 3233 = **557** ✓

**Kết luận:** Thông điệp M = 557 được mã hóa RSA thành **C = 760** với khóa công khai (17, 3233) và giải mã thành công bằng khóa bí mật (2753, 3233).

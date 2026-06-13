---
title: "1MW Điện Có Thể Chạy Bao Nhiêu Token? Phân Tích Hiệu Suất Năng Lượng GPU NVIDIA"
date: 2026-06-04T16:00:00+08:00
draft: false
tags: ["AI芯片", "英伟达", "能效", "算力", "Token", "H100", "B200"]
description: "Lấy 1MW điện làm chuẩn, so sánh hiệu suất sinh Token của NVIDIA H100, H200, B200, phân tích khoảng cách hiệu suất năng lượng và các yếu tố hạn chế."
summary: "Với NVIDIA H100, mỗi MW có thể triển khai khoảng 1400 thẻ, sinh khoảng 18-22T Token/MWh; B200 vượt trội về hiệu suất, hiệu suất Token đạt 36T/MWh, là lựa chọn hàng đầu cho suy luận AI thế hệ tiếp theo."
ShowToc: true
TocOpen: false
---

## Bối cảnh: Tại sao dùng "Token / MW" để đo lường?

Trong cuộc đua sức mạnh tính toán AI, **điện năng là ràng buộc tối hậu**. Bất kể chip mạnh đến đâu, cuối cùng đều phải xem xét "tốn bao nhiêu tiền điện, sinh ra được bao nhiêu token".

Chỉ số này tổng hợp:
- Mức tiêu thụ điện của GPU (TDP)
- Sức mạnh tính toán của GPU (TFLOPS)
- Số lượng GPU (bị giới hạn bởi tường công suất)
- Hiệu suất suy luận thực tế (bị ảnh hưởng bởi băng thông bộ nhớ, băng thông kết nối)

---

## So sánh dữ liệu cốt lõi

### Bảng thông số kỹ thuật GPU

| Chip | TDP (W) | Sức mạnh FP16 (TFLOPS) | Băng thông bộ nhớ | Bộ nhớ | Kiến trúc |
|---|---|---|---|---|---|
| **H100 SXM5** | 700 | 3,956 | 3,350 GB/s | 80GB HBM3 | Hopper |
| **H200 SXM** | 700 | 3,956 | 4.8 TB/s | 141GB HBM3e | Hopper |
| **B100** | 700 | 14,400 | ~3.2 TB/s | 192GB HBM3e | Blackwell |
| **B200 SXM** | 1,000 | 20,000 | ~8 TB/s | 192GB HBM3e | Blackwell |

> Nguồn dữ liệu: Sách trắng chính thức của NVIDIA

---

## Sức mạnh tính toán lý thuyết: Mỗi MW có thể triển khai bao nhiêu card?

$$N_{cards} = \frac{1{,}000{,}000 \text{ W}}{TDP_{per\_card}}$$

| Chip | Công suất mỗi card | Có thể triển khai mỗi MW |
|---|---|---|
| H100 / H200 | 700W | ~1,428 card |
| B100 | 700W | ~1,428 card |
| B200 | 1,000W | 1,000 card |

---

## Sức mạnh FP16: Tổng sức mạnh tính toán mỗi MW

$$P_{MW} = N_{cards} \times FP16_{per\_card}$$

| Chip | FP16 mỗi card | Số card triển khai mỗi MW | Tổng sức mạnh mỗi MW |
|---|---|---|---|
| H100 | 3,956 TFLOPS | 1,428 | **5.65 PFLOPS** |
| H200 | 3,956 TFLOPS | 1,428 | **5.65 PFLOPS** |
| B100 | 14,400 TFLOPS | 1,428 | **20.6 PFLOPS** |
| B200 | 20,000 TFLOPS | 1,000 | **20 PFLOPS** |

**Kết luận**: B100 với kiến trúc Blackwell, dưới cùng mức điện năng, đạt được tổng sức mạnh tính toán gấp **3,6 lần** H100.

---

## Ước tính hiệu suất sinh Token

### Phương pháp ước tính

Sức mạnh FP16 ≠ Lượng Token sinh ra. Hiệu suất thực tế phụ thuộc vào:
1. **Băng thông bộ nhớ**: Quyết định tốc độ cung cấp dữ liệu
2. **Băng thông kết nối**: Quyết định hiệu quả hợp tác đa card
3. **Kích thước mô hình**: Mô hình lớn có nút thắt ở băng thông bộ nhớ
4. **batch size**: Xử lý theo lô có thể cải thiện tỉ lệ sử dụng

**Tiêu chuẩn ước tính**: Lấy mô hình Llama-70B làm ví dụ

| Chip | Token/s mỗi card (ước tính) | Tham khảo |
|---|---|---|
| H100 SXM | 2,500 – 4,000 tok/s | Llama-70B @ FP16 |
| H200 | 3,000 – 5,000 tok/s | Tương tự, được hỗ trợ bởi HBM3e |
| B100 | 7,000 – 10,000 tok/s | Nâng cấp kiến trúc Blackwell |
| B200 | 8,000 – 12,000 tok/s | Hỗ trợ NVLink 5.0 |

---

## So sánh Token / MWh

$$\text{Token per MWh} = \text{Token/s per card} \times N_{cards} \times 3600$$

### Triển khai tĩnh (không tính thời gian nghỉ)

| Chip | Token/s mỗi card | Số card mỗi MW | **Token / MWh (tĩnh)** |
|---|---|---|---|
| H100 | 3,500 | 1,428 | **17.9 T** |
| H200 | 4,200 | 1,428 | **21.6 T** |
| B100 | 8,500 | 1,428 | **43.7 T** |
| B200 | 10,000 | 1,000 | **36.0 T** |

> T = Nghìn tỷ (10¹²)

### Tỉ lệ sử dụng động (xét đến hiệu suất triển khai thực tế)

Trong suy luận thực tế, GPU không thể hoạt động 100%. Sau khi xét đến tỉ lệ sử dụng đỉnh:

| Chip | Token/MWh tĩnh | Tỉ lệ sử dụng 70% |
|---|---|---|
| H100 | 17.9 T | **12.5 T** |
| H200 | 21.6 T | **15.1 T** |
| B100 | 43.7 T | **30.6 T** |
| B200 | 36.0 T | **25.2 T** |

---

## Kết luận cốt lõi

### 1. B200 hiện là GPU có hiệu suất Token cao nhất

Hiệu suất Token mỗi MW của B200 gấp khoảng **2 lần** H100, tổng sức mạnh tính toán gấp **3,6 lần** H100.

Ưu thế cốt lõi của kiến trúc Blackwell:
- **NVLink 5.0**: Kết nối hai chiều 1,8 TB/s, triệt tiêu hoàn toàn nút thắt giao tiếp đa card
- **192GB HBM3e**: Mỗi card có thể chứa mô hình 70B+, batch size lớn hơn
- **20 PFLOPS FP16**: Sức mạnh tính toán trên mỗi đơn vị điện năng tăng đáng kể

### 2. H200 là lựa chọn cân bằng nhất hiện nay

H200 sử dụng cùng mức tiêu thụ điện với H100 (700W), nhưng với bộ nhớ 141GB HBM3e:
- Dung lượng bộ nhớ tăng 76%
- Băng thông bộ nhớ tăng 43%
- Hiệu suất Token cao hơn H100 **khoảng 20%**

Đối với doanh nghiệp đã có cụm H100, nâng cấp lên H200 là lựa chọn có tỉ lệ chi phí-hiệu quả cao nhất.

### 3. Băng thông kết nối là nút thắt cốt lõi

Đối với suy luận mô hình lớn, NVLink là đường sống:
- Mô hình 70B không thể chứa trên một card, buộc phải xử lý song song đa card
- Băng thông HCCS/PCIe thấp hơn nhiều so với NVLink, tỉ lệ sử dụng đa card sẽ giảm đáng kể
- NVLink 5.0 của B200 (1,8 TB/s) nhanh gấp **2 lần** so với NVLink 4.0 của H100 (900 GB/s)

### 4. Cân bằng giữa tiêu thụ điện và sức mạnh tính toán

B200 tiêu thụ điện cao hơn H100 43% (1000W so với 700W), nhưng tổng sức mạnh tính toán gấp 3,6 lần H100.

Điều này có nghĩa:
- Thiết kế tản nhiệt của trung tâm dữ liệu cần nâng cấp
- Số giá rack mỗi MW giảm, nhưng tổng sức mạnh tính toán tăng đáng kể
- **Chi phí điện năng trên mỗi Token thực tế giảm hơn 50%**

---

## Tham khảo nhanh

| Chỉ số | H100 | H200 | B100 | B200 |
|---|---|---|---|---|
| Số card mỗi MW | 1,428 | 1,428 | 1,428 | 1,000 |
| FP16 mỗi MW | 5.65 PFLOPS | 5.65 PFLOPS | 20.6 PFLOPS | 20 PFLOPS |
| Token/MWh (tĩnh) | 17.9 T | 21.6 T | 43.7 T | 36.0 T |
| Token/MWh (@70%) | ~12.5 T | ~15 T | ~30.6 T | ~25 T |
| Ưu thế chính | Ổn định, chín muồi | Bộ nhớ lớn | Sức mạnh cao | Băng thông kết nối |

---

*Nguồn dữ liệu: Sách trắng chính thức của NVIDIA, AnandTech, Semianalysis và các báo cáo phân tích khác, ước tính dữ liệu thực tế năm 2024-2025.*

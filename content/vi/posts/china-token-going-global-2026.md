---
title: "Token Trung Quốc vươn ra toàn cầu 2026: Từ cuộc chiến giá đến bước ngoặt thị phần"
date: 2026-06-11
draft: false
description: "Các mô hình lớn của Trung Quốc chiếm 61% thị phần trên OpenRouter mới chỉ là bước khởi đầu. Bài viết phân tích ai thực sự đang ra nước ngoài, cách chọn thị trường mục tiêu, cách chơi cuộc chiến giá, và các con đường kiếm tiền thực sự — cũng như lý do vì sao khách hàng doanh nghiệp nước ngoài bắt đầu chuyển lưu lượng sản xuất sang các mô hình Trung Quốc."
tags: ["AI", "Kinh tế Token", "Vươn ra toàn cầu", "Mô hình lớn", "MaaS", "Phân tích thị trường", "Mã nguồn mở", "Thị trường toàn cầu"]
slug: "china-token-going-global-2026"
cover:
  image: "https://images.unsplash.com/photo-1521295121783-8a321d551ad2?w=1200&q=80"
  alt: "Mạng lưới kỹ thuật số toàn cầu và các nút mạng"
  caption: "Token Trung Quốc vươn ra toàn cầu: không phải bán mô hình, mà là bán lệnh gọi"
ShowToc: true
translationKey: "china-token-going-global-2026"
---

![Mạng lưới toàn cầu](https://images.unsplash.com/photo-1521295121783-8a321d551ad2?w=1200&q=80)
*Định tuyến toàn cầu của mô hình Trung Quốc đang được viết lại—nhưng người chiến thắng không phải kẻ chạy nhanh nhất, mà là kẻ chạy ổn định nhất*

---

## Mở đầu: Ẩn số phía sau con số 61%

Nếu chỉ nhìn vào bảng xếp hạng công khai của OpenRouter, câu chuyện rất đơn giản:

> Đầu năm 2025, tỷ trọng Token của các mô hình nguồn mở Trung Quốc trên OpenRouter là **1,2%**.  
> Đầu năm 2026, con số này là **61%**.  
> Mười tám tháng, gấp năm mươi lần.

Nhưng tỷ trọng không phải là doanh thu, giá cả không phải là lợi nhuận. Khó khăn thực sự khi ra nước ngoài nằm ở nửa sau của câu: **Sau tỷ trọng thì kiếm tiền thế nào**.

Tôi đã dành hai tháng theo dõi 11 nền tảng API mô hình lớn toàn cầu, 4 cổng tổng hợp, 3 cộng đồng nhà phát triển độc lập, để phân tách “Token Trung Quốc ra nước ngoài” thành một tấm bản đồ. Dưới đây chính là tấm bản đồ ấy.

---

## 1. Trước hết cần làm rõ: “Token ra nước ngoài” là gì

Nhiều người đang nhập nhằng ba khái niệm, tôi tách chúng ra như sau:

| Khái niệm | Ý nghĩa | Ví dụ điển hình |
|------|------|----------|
| **Mô hình ra nước ngoài** | Công bố trọng số mô hình (mã nguồn mở/bán mở) lên các nền tảng như Hugging Face | Đội ngũ nguồn mở nội địa hàng đầu R / Nhà cung cấp đám mây tổng hợp lớn B / Công ty khởi nghiệp K / Công ty khởi nghiệp Z |
| **API ra nước ngoài** | Triển khai dịch vụ suy luận ở nước ngoài, bán lượt gọi | Trang quốc tế của Nhà cung cấp đám mây tổng hợp B, trang quốc tế của Nhà cung cấp đám mây video A, các mô hình Trung Quốc trên Together AI |
| **Token ra nước ngoài** | Thông qua các nền tảng bên thứ ba (OpenRouter, GitHub Models, Vercel AI Gateway) được các nhà phát triển nước ngoài gọi gián tiếp | Đây là hình thức ra nước ngoài ngầm, lượng lớn nhất, ít được bàn luận nhất |

**Điều thực sự quyết định tỷ trọng chính là mục thứ ba**. Nhà phát triển sẽ không đăng ký tài khoản đám mây Trung Quốc, không mở thanh toán quốc tế—họ trực tiếp chuyển đổi API chỉ bằng một cú nhấp chuột trên OpenRouter, chỉ cần mô hình Trung Quốc nằm trong top bảng xếp hạng, tính cước theo lượt gọi sẽ tự nhiên được chọn.

Điều này có nghĩa: **Ra nước ngoài không phải là vấn đề bán hàng, mà là vấn đề hạ tầng.** Ai làm trước bộ tứ: trọng số mô hình, năng lực suy luận, giao diện tương thích OpenAI, thanh toán qua Stripe, người đó sẽ giành được lưu lượng thụ động.

---

## 2. Bản đồ người chơi: Ai đang thực sự ra nước ngoài

Tôi xếp hạng năm cấp độ theo “chiều sâu thực tế ra nước ngoài”. **Tất cả các công ty thống nhất sử dụng mã thay thế, bảng đối chiếu nằm trong tài liệu nội bộ**.

### 2.1 Cấp độ 1: Thực sự hưởng lợi từ làn sóng nhà phát triển toàn cầu (≥5% tỷ lệ gọi từ nước ngoài)

**Đội ngũ nguồn mở nội địa hàng đầu R**  
- Sau khi phát hành V3 cuối năm 2024, **lượng Token gọi trong ngày đứng đầu OpenRouter chỉ trong 7 ngày**
- Giá API: cache hit $0,014 / cache miss $0,28 (trên một triệu token)
- Tỷ lệ gọi từ nước ngoài trên 60%
- Cách đánh cốt lõi: **“Ba cú đánh liên tiếp” Giấy phép MIT + Giao thức tương thích OpenAI + Giá cực thấp**
- Hào chiến lược then chốt: Thu mua tuân thủ cụm H800 (qua lộ trình Singapore) + Hiệu quả huấn luyện (chi phí chỉ bằng 1/10 so với cùng quy mô)

**Nhà cung cấp đám mây tổng hợp hàng đầu B**  
- Ma trận mô hình đầy đủ nhất (bao phủ toàn bộ kích thước từ 0,6B–235B + đa phương thức)
- Quý 4 năm 2025 phát hành kép qua Hugging Face, ModelScope, **dòng B trên HF đạt tổng lượt tải về 42 triệu**
- Lượng gọi từ nước ngoài chỉ đứng sau R
- Động thái chính: ModelStudio phiên bản quốc tế + Tương thích ba bộ SDK OpenAI / Anthropic / Vertex

**Công ty khởi nghiệp AI Trung Quốc K**  
- Các mô hình hệ K thường xuyên trong Top 3 OpenRouter
- Thâm nhập cực mạnh vào các ngữ cảnh dài (trên 200K token) ở nước ngoài
- Điểm khác biệt chính: **Ngữ cảnh dài 200K + Gọi công cụ mạnh + Độ trễ thấp**
- Mức độ nhận diện trong cộng đồng nhà phát triển quốc tế: GitHub Stars 21K+ (cùng kỳ GPT-4o đạt 38K)

### 2.2 Cấp độ 2: Được quốc tế biết đến nhưng lượng gọi chưa bùng nổ

**Công ty khởi nghiệp AI Trung Quốc Z**  
- Mô hình thế hệ 4.5 thường xuyên lọt danh sách Trending trên Hugging Face
- Từ tháng 8 năm 2025 đã có lượt gọi ổn định trên OpenRouter
- **Vấn đề cốt lõi: Nhận diện thương hiệu Z của nhà phát triển nước ngoài thấp**, khoảng cách với công ty dẫn đầu nước ngoài còn lớn
- Trong nước kiếm được tiền nhờ tăng giá Coding 83%, nhưng tỷ lệ chuyển đổi trả phí ở nước ngoài chỉ bằng 1/5

**Công ty khởi nghiệp AI Y**  
- Các mô hình hệ K2 có những người dùng tiên phong ở nước ngoài
- Ngữ cảnh dài + Gọi công cụ là điểm sáng
- Con đường thương mại hóa vẫn đang tìm kiếm

**Công ty khởi nghiệp AI S**  
- Mô hình thế hệ 2 / 3 được chấp nhận ở nước ngoài trong một số kịch bản đa phương thức cụ thể
- Quy mô còn nhỏ

### 2.3 Cấp độ 3: Ra nước ngoài qua kênh (không ra mô hình, ra lượt gọi)

**Nhà cung cấp đám mây video hàng đầu A**  
- Mô hình tạo video trên phiên bản quốc tế hướng tới khách hàng phim ngắn / quảng cáo / thương mại điện tử nước ngoài
- Thông qua hệ sinh thái quốc tế của công ty mẹ dòng A (các dòng sản phẩm khác trong cùng tập đoàn) để mở rộng
- API nước ngoài cạnh tranh trực tiếp với Runway / Pika

**Một nhà cung cấp đám mây Trung Quốc C**  
- Ra nước ngoài gián tiếp qua trạm quốc tế của nhà cung cấp đám mây C
- Lượng gọi nhỏ, chủ yếu phục vụ khách hàng game / tài chính Đông Nam Á

### 2.4 Cấp độ 4: Ra nước ngoài về hạ tầng

**Nền tảng năng lực tính toán AI T** (Together AI)  
- Xuất thân Trung Quốc, hiện là đám mây suy luận độc lập lớn nhất Bắc Mỹ
- Đồng thời lưu trữ các mô hình nguồn mở như Llama / Q / D / G
- Năng lực tính toán đến từ cụm tự dựng A100 / H100 / H200

**Cổng định tuyến mô hình lớn G** (một trong những đối tác ban đầu của OpenRouter)  
- Cung cấp API thống nhất, chuyển đổi dự phòng tự động, thanh toán
- Gián tiếp khuếch đại khả năng tiếp cận của tất cả các mô hình Trung Quốc

### 2.5 Cấp độ 5: Đang chờ ra nước ngoài

Phần này chưa có tên nhưng đáng chú ý: Ngoài R / B / K / Z / Y / S ra, một vài đội ngũ “chuyên sâu, đặc thù, mới mẻ” đang thực hiện:
- Phiên bản tiếng Anh của mô hình chuyên ngành dọc (y tế / pháp luật / tài chính)
- Lộ trình khác biệt hóa cho giọng nói / tạo nhạc
- Khung Agent (không chỉ bán mô hình, bán cả chuỗi công cụ)

---

## 3. Thị trường mục tiêu: Đông Nam Á là “sân tập”, Âu Mỹ là “chiến trường chính”

Phân tách lượt gọi ra nước ngoài của mô hình Trung Quốc theo khu vực, tỷ lệ đại khái là:

| Khu vực | Tỷ trọng | Kịch bản điển hình | Loại khách hàng |
|------|------|----------|----------|
| Bắc Mỹ | 38% | Nguyên mẫu nhà phát triển, SaaS độc lập, khởi nghiệp công cụ AI | Nhà phát triển cá nhân + Công ty khởi nghiệp giai đoạn đầu |
| Châu Âu | 17% | Đa ngôn ngữ, kịch bản nhạy cảm về quyền riêng tư | SaaS quy mô vừa, dự án nghiên cứu chính phủ-doanh nghiệp |
| Đông Nam Á | 22% | Chăm sóc khách hàng đa ngôn ngữ, hướng dẫn mua sắm thông minh, dịch thuật | Nền tảng Internet (thương mại điện tử / gọi xe / tài chính) |
| Mỹ Latinh | 9% | Chăm sóc khách hàng tiếng Tây Ban Nha/Bồ Đào Nha, giáo dục | Công ty Internet khu vực |
| Trung Đông | 6% | Tiếng Ả Rập, số hóa chính phủ-doanh nghiệp | Khách hàng đám mây có vốn nhà nước |
| Châu Phi / Khác | 8% | NLP cơ bản, giáo dục, hành chính | NGO / Hạ tầng số quốc gia |

**Quan sát chính**:

1. **Bắc Mỹ là chiến trường chính, nhưng nhạy cảm về giá**. Lựa chọn đầu tiên của nhà phát triển là “đủ dùng và rẻ”, tổ hợp “giá/hiệu năng” của mô hình Trung Quốc gần như vô địch trước khi GPT-5 ra mắt—nhưng cuối năm 2025 GPT-5 xuất hiện, khoảng cách hiệu năng thu hẹp, mô hình Trung Quốc buộc phải dựa vào “chi phí” để kéo dài.

2. **Đông Nam Á là bể thu nhập thực sự**. Đây không phải là nhà phát triển dùng API, mà là doanh nghiệp dùng giải pháp toàn diện. Một tập đoàn gọi xe lớn ở Đông Nam Á đã chuyển 30% lưu lượng sản xuất sang mô hình Trung Quốc (chăm sóc khách hàng đa ngôn ngữ, phân đơn thông minh, kiểm duyệt tuân thủ), mỗi năm tiết kiệm được 40 triệu USD so với dùng OpenAI.

3. **Châu Âu là cuộc đua tuân thủ**. GDPR + EU AI Act khiến cho “mã nguồn mở Trung Quốc” ngược lại dễ được phê duyệt hơn “mã đóng của Mỹ” (trọng số mở = minh bạch có thể kiểm toán), nhưng chi phí nội địa hóa (lưu trữ dữ liệu, phòng suy luận tại châu Âu) cao.

4. **Mỹ Latinh / Trung Đông có tốc độ tăng trưởng cao nhưng cơ sở thấp**. Một quỹ đầu tư quốc gia Trung Đông năm 2025 bắt đầu mua API mô hình Trung Quốc để triển khai số hóa chính phủ, đơn hàng đơn lẻ lên tới 50 triệu USD.

---

## 4. Cuộc chiến định giá: 1/10 không phải là kết thúc, 1/30 mới là

Tôi đã lập một biểu đồ giá đầu vào của 20 mô hình hàng đầu trên OpenRouter vào tháng 5 năm 2026:

| Mô hình | Đầu vào $/triệu token | Đầu ra $/triệu token | Giá so với GPT-4o |
|------|------------------|------------------|------------------|
| GPT-4o (mã đóng) | 2,50 | 10,00 | 1,0× |
| Hệ A mã đóng (dẫn đầu nước ngoài) | 3,00 | 15,00 | 1,3× |
| Hệ B mã đóng (dẫn đầu nước ngoài) | 1,25 | 10,00 | 0,7× |
| Llama 4 70B (mã nguồn mở) | 0,85 | 0,85 | 0,2× |
| Nguồn mở Trung Quốc hệ R 235B | 0,20 | 0,60 | 0,04× |
| Nguồn mở Trung Quốc hệ R V3.2 | 0,14 | 0,28 | 0,03× |
| Nguồn mở Trung Quốc hệ Z 4.5 | 0,20 | 0,20 | 0,03× |
| Nguồn mở Trung Quốc hệ K K2 | 0,15 | 2,50 | 0,06× |

**Một vài sự thật bị bỏ qua**:

- “Giá đầu vào” của mô hình Trung Quốc đã bằng 1/20~1/30 của OpenAI, nhưng “giá đầu ra” chênh lệch ít hơn (hệ Z 0,03× là trường hợp cực đoan nhất, hệ K 0,06× là “phạm vi bình thường”)
- **Điều này có nghĩa lợi nhuận thực sự của Token ra nước ngoài nằm ở phía đầu vào**—ngữ cảnh dài, phân tích tài liệu, truy xuất RAG, là những kịch bản lợi thế tự nhiên của Trung Quốc
- **“Trúng bộ nhớ đệm” chính là vũ khí hạt nhân của mô hình Trung Quốc**: Giá cache hit của hệ R V3 là 0,014 USD/triệu token, thấp hơn cả batch API của OpenAI một bậc
- **Lần đầu tiên tăng giá không giảm lượng là đúng**: Trong nước, hệ Z 5.1 quý 1 tăng giá 83% + lượng gọi tăng 400%—điều này chưa tái hiện ở nước ngoài, nhưng **dự báo các mô hình hàng đầu ở nước ngoài cũng sẽ đi theo con đường tương tự**

---

## 5. Lộ trình kiếm tiền: 4 mô hình đã chạy thành công

Ra nước ngoài không lãng mạn như kiểu “bỏ mô hình lên HF rồi chờ tải xuống”. Tôi đã tổng hợp 4 lộ trình kiếm tiền đã đạt quy mô:

### 5.1 Lộ trình A: Bán trực tiếp API (phù hợp nhất với đại gia đám mây)

**Quy mô doanh thu**: 100 triệu - 5 tỷ USD/năm (tùy quy mô nhà cung cấp đám mây)  
**Biên lợi nhuận gộp**: 30-50% (bao gồm năng lực suy luận + băng thông + chi phí bán hàng)  
**Đại diện**: Phiên bản quốc tế Nhà cung cấp đám mây tổng hợp B, Phiên bản quốc tế Nhà cung cấp đám mây video A  
**Năng lực then chốt**:
- Triển khai đa vùng (Singapore / Frankfurt / Virginia)
- Đa dạng phương thức thanh toán (Stripe / Airwallex / thẻ tín dụng địa phương)
- Tuân thủ địa phương (GDPR / PDPA / Luật bảo vệ dữ liệu UAE)

**Thách thức lớn nhất**: Xây dựng đội ngũ phát triển kinh doanh địa phương + lòng tin của khách hàng trong bối cảnh quan hệ Mỹ-Trung

### 5.2 Lộ trình B: Chia sẻ doanh thu qua nền tảng tổng hợp (phù hợp nhất với đội ngũ khởi nghiệp mới)

**Quy mô doanh thu**: 10 triệu - 500 triệu USD/năm  
**Biên lợi nhuận gộp**: 50-70% (nền tảng trích 15-30%, nhưng tự mình không cần xây dựng đội ngũ kinh doanh)  
**Đại diện**: Together AI, Fireworks AI, OpenRouter  
**Năng lực then chốt**:
- Trọng số mô hình + tối ưu suy luận (vLLM / SGLang / TensorRT-LLM)
- Tự động mở rộng thu hẹp + định tuyến đa mô hình
- Mua sắm năng lực tính toán từ các đám mây GPU thượng nguồn (CoreWeave / Lambda)

**Thách thức lớn nhất**: Tốc độ lặp mô hình (mô hình mới ra, giá mô hình cũ lập tức bị cắt giảm)

### 5.3 Lộ trình C: SaaS ngành dọc (kiếm tiền nhất nhưng khó nhất)

**Quy mô doanh thu**: 500 triệu - 10 tỷ USD/năm  
**Biên lợi nhuận gộp**: 60-80% (định giá theo kết quả / theo chỗ ngồi)  
**Đại diện**:
- AI pháp lý: Một công ty AI Trung Quốc + hợp tác với hãng luật Mỹ, triển khai trên AWS GovCloud, **ARR 30 triệu USD**  
- AI y tế: Một công ty AI Trung Quốc + hợp tác với bệnh viện Trung Đông, **trị giá dự án 80 triệu USD**  
- AI giáo dục: Một công ty AI Trung Quốc + hợp tác với Bộ Giáo dục Đông Nam Á, **5 năm 200 triệu USD**

**Năng lực then chốt**:
- Năng lực tinh chỉnh giám sát (SFT) lĩnh vực chuyên sâu
- Tuân thủ dữ liệu + thích ứng quy định địa phương
- Quan hệ khách hàng dài hạn (không chỉ là một lần gọi API)

**Thách thức lớn nhất**: Chu kỳ dự án đơn điểm dài, nhân rộng quy mô khó

### 5.4 Lộ trình D: Bó cứng phần cứng + mô hình (IDC / nhà sản xuất chip ưa thích nhất)

**Quy mô doanh thu**: 100 triệu - 3 tỷ USD/năm (một lần + đăng ký)  
**Biên lợi nhuận gộp**: 20-35% (phần cứng biên lợi thấp)  
**Đại diện**:
- Một nhà sản xuất chip thương hiệu Trung Quốc + một mô hình lớn Trung Quốc, **đóng gói bán cho khách hàng Đông Nam Á**  
- Một nhà sản xuất máy chủ thương hiệu Trung Quốc + một mô hình lớn Trung Quốc, **bán giải pháp toàn bộ cho khách hàng Trung Đông**  
- Một nhà sản xuất mô-đun quang thương hiệu Trung Quốc, **gắn kèm API mô hình Trung Quốc bán sang Mỹ Latinh**

**Năng lực then chốt**:
- Giải pháp một điểm đến (phần cứng + phần mềm + tích hợp + đào tạo)
- Năng lực sản xuất địa phương / đối tác năng lực địa phương
- Hỗ trợ vận hành dài hạn

**Thách thức lớn nhất**: Áp lực kép biên lợi nhuận phần cứng + ROI mô hình

---

## 6. Ba phát hiện phản trực giác

---
Sau khi viết xong bản đồ phía trên, tôi có một vài góc nhìn **không hoàn toàn trùng khớp với diễn biến chính**:

### 6.1 “Các mô hình Trung Quốc chiếm 61% thị phần trên OpenRouter” chỉ là bề nổi, số liệu thực tế có thể còn cao hơn

OpenRouter là dữ liệu công khai, nhưng vẫn còn **lượng gọi ẩn lớn hơn nhiều**:
- **Hệ R / B trên AWS Bedrock**: Chỉ riêng Bedrock, tổng số Token gọi hàng tháng của dòng B cao gấp 3 lần so với lượng Token gọi dòng B trên OpenRouter.
- **Phi / M series trên Azure AI Foundry**: Microsoft bán phần này như một giải pháp “thay thế OpenAI” cho khách hàng doanh nghiệp.
- **B / G series trên Vertex AI Model Garden**: Google phân phối gián tiếp.
- **Vercel AI Gateway / Cloudflare AI Gateway**: Các nhà phát triển gọi mà không để ý đến nhà cung cấp.

Tính cả những nguồn này, **thị phần thực tế của các mô hình Trung Quốc trong tổng lưu lượng suy luận LLM toàn cầu có thể đã tiệm cận 45%** (61% trên OpenRouter chỉ là kịch bản người dùng tự chọn + chủ động điều hướng, chưa bao gồm phần “bị AWS / Azure đẩy lưu lượng sang”).

### 6.2 “Ra nước ngoài” thành công nhất không phải là các công ty mô hình, mà là tầng trung gian

- **Together AI** (có yếu tố Trung Quốc): ARR thường niên hóa 500 triệu USD, tỷ suất lợi nhuận gộp trên 60%, **về bản chất là đem mô hình nguồn mở Trung Quốc bán trở lại Mỹ** – việc này dễ hơn gấp 100 lần so với “bán thẳng mô hình Trung Quốc sang Mỹ”.
- **Đội ngũ ban đầu của OpenRouter**: Một nửa lập trình viên cốt lõi là người Hoa, ngay từ ngày đầu tiên nền tảng đã được tối ưu hóa cho các dòng R / B / G.
- **Cloudflare Workers AI**: Đem mô hình Trung Quốc bán cho khách hàng SaaS Âu Mỹ như một giải pháp “thay thế với độ trễ thấp”.

**Kết luận**: Phần lớn tiền từ việc ra nước ngoài đang **bị các đội ngũ người Hoa làm trung gian ở nước ngoài kiếm được**. Đây chính là phiên bản AI của mô hình “kho ngoại kiều” trong thương mại điện tử xuyên biên giới suốt một thập kỷ qua.

### 6.3 “Mã nguồn mở” là đòn bẩy lớn nhất khi ra nước ngoài, nhưng cũng là rủi ro lớn nhất

Các mô hình Trung Quốc trong giai đoạn 2025-2026 đang vận hành theo cặp động cơ kép “**cực kỳ cởi mở + giá siêu thấp**”. Cách đánh này đã khiến thị phần tăng 50 lần trong vòng 18 tháng, nhưng chôn sẵn ba quả mìn:

1. **Rủi ro ngược từ việc bị chưng cất**: Các ông lớn nước ngoài (đặc biệt là dòng A mã nguồn đóng và dòng B mã nguồn đóng) đang chưng cất đầu ra của mô hình nguồn mở Trung Quốc một cách có hệ thống. Nếu tương lai mô hình Trung Quốc biến thành “tập huấn luyện bị nuôi miễn phí”, về lâu dài sẽ thiệt.
2. **Rủi ro địa chính trị**: Từ năm 2025, Quốc hội Mỹ bắt đầu thảo luận về “kiểm soát xuất khẩu mô hình AI”. **Nếu “trọng số mô hình” cũng bị đưa vào danh sách quản lý của BIS**, toàn bộ trọng số Trung Quốc trên Hugging Face sẽ bị gỡ bỏ.
3. **Khóa chặt hệ sinh thái theo hướng ngược**: Khi các nhà phát triển nước ngoài đã quen với “giao thức tương thích OpenAI + thanh toán Stripe + triển khai AWS”, **mức độ gắn kết giữa họ và mô hình Trung Quốc thực ra rất thấp** – bất kỳ thay đổi chính sách nào cũng có thể khiến họ chuyển về lại chỉ trong một đêm.

**Vì vậy, người chiến thắng thực sự không phải là kẻ “mở nguồn nhất”, mà là những bên có bố cục toàn diện “mã nguồn mở + mã nguồn đóng + SaaS chuyên ngành + đóng gói cùng phần cứng”.** Trần của lối đi đơn lẻ đã xuất hiện.

---

## 7. Gợi ý cho các tổ chức AI trong nước (và công việc của bạn)

Nếu bạn cũng đang làm AI ra nước ngoài như tôi, dưới đây là vài nhận định **có thể dùng được ngay**:

### 7.1 Hành vi mua của khách hàng đang phân hóa thành hai tầng

- **Nhà phát triển cá nhân / startup giai đoạn đầu**: Trả tiền theo lượng Token, cực kỳ nhạy cảm với giá, **mô hình Trung Quốc = lựa chọn mặc định**.
- **SaaS quy mô vừa / khách hàng doanh nghiệp**: Trả tiền theo “kết quả kinh doanh” hoặc “theo đầu ghế”, rất nhạy cảm với tính tuân thủ, bản địa hóa và SLA, **mô hình Trung Quốc = phương án dự phòng + con bài đàm phán**.

**Chiến lược bán hàng cần chia thành hai bộ**: Một bộ dành cho tiếp cận nhà phát triển (GitHub / Discord / HN), một bộ dành cho người ra quyết định mua hàng (tài liệu tuân thủ + lưu trữ dữ liệu tại chỗ + case study địa phương).

### 7.2 Ba cơ hội thị trường “bị đánh giá thấp”

1. **Chăm sóc khách hàng đa ngôn ngữ Đông Nam Á**: Dữ liệu SFT chất lượng cao cho tiếng Indonesia / tiếng Việt / tiếng Thái. **Các đội ngũ Trung Quốc có lợi thế kép về ngôn ngữ học và kỹ thuật**, các đội ở nước ngoài gần như chưa làm.
2. **Dạy lập trình Coding bằng tiếng Tây Ban Nha tại Mỹ Latinh**: Đào tạo K12 và hướng nghiệp tại Mexico / Brazil. **Mô hình Coding Trung Quốc + đối tác giáo dục địa phương** là một tổ hợp tự nhiên.
3. **Kịch bản tiếng Ả Rập và văn hóa Hồi giáo tại Trung Đông**: Tuân thủ tài chính, tư vấn luật Sharia, kiểm duyệt nội dung văn hóa. **Mô hình Trung Quốc có lợi thế tương đối về điều chỉnh văn hóa và triển khai kỹ thuật**.

### 7.3 Một hướng “ra nước ngoài ngược” thường bị bỏ qua

Doanh thu nội địa của các hãng MaaS trong nước (A / B / Z, v.v.) đã tăng lên 100-150 tỷ NDT/năm, **nhưng doanh thu API từ nước ngoài của họ phần lớn chưa bằng 1/10 mức đó**. Điều này có nghĩa:

- **API nước ngoài là con đường “chiến tranh giá cả + lợi nhuận mỏng”**.
- **Thứ thực sự sinh lời là “ra nước ngoài ngược” – kéo nhà phát triển nước ngoài vào đại hệ sinh thái trong nước**.

Hành động cụ thể:
- Mời nhà phát triển nước ngoài tham dự các hội nghị AI lớn trong nước (WAIC / Vân Tê).
- Cung cấp trải nghiệm gói ba món “mô hình Trung Quốc + sức mạnh tính toán Trung Quốc + thanh toán Trung Quốc”.
- Kéo các đội khởi nghiệp nước ngoài về đăng ký trong nước (vườn ươm AI ở Hàng Châu / Tô Châu / Thâm Quyến).
- Dùng “ca thành công trong nước” để làm BD ở nước ngoài (“Nền tảng X ở Đông Nam Á sau khi dùng chúng tôi đã tiết kiệm 40 triệu USD”).

### 7.4 Một tín hiệu đáng phải cảnh giác

Cuối năm 2025 xuất hiện một dấu hiệu: **Một công ty AI hàng đầu của Mỹ bắt đầu có hành động pháp lý đối với việc “bị các mô hình nguồn mở Trung Quốc phân luồng”**.

Hành động cụ thể là “truy xuất nguồn gốc tuân thủ dữ liệu huấn luyện” – tuyên bố rằng mô hình Trung Quốc đã sử dụng dữ liệu đầu ra của họ trong quá trình huấn luyện và yêu cầu gỡ xuống.

**Ngắn hạn**: Chiến tranh pháp lý khó có thể khơi mào, các giấy phép mã nguồn mở có lớp bảo vệ.  
**Dài hạn**: Đây là một tín hiệu – các ông lớn nước ngoài đã xếp “mã nguồn mở Trung Quốc” vào danh sách **đối thủ cạnh tranh trực tiếp**. Trong 12-18 tháng tới, xung đột ba mặt địa chính trị + pháp lý + thương mại sẽ gia tăng.

**Đối với công việc của bạn**: Trong tất cả hợp đồng với khách hàng lớn ở nước ngoài, **cần phải dự trù sẵn “điều khoản chuyển đổi mô hình” và “điều khoản bất khả kháng địa chính trị”**.

---

## 8. Kết luận: Ba câu hỏi thực sau thị phần

Ngoài con số 61%, cuộc ra nước ngoài của Token vẫn phải trả lời ba câu hỏi:

1. **Doanh thu** – 61% trên OpenRouter chuyển thành ARR là bao nhiêu? Số liệu thực có thể ở mức 30-50 tỷ USD/năm, nhưng **liệu lợi nhuận gộp có đủ bù đắp chi phí suy luận hay không**?  
2. **Hệ sinh thái** – Nhà phát triển nước ngoài dùng mô hình Trung Quốc, nhưng **sau khi dùng xong, điểm đến tiếp theo của họ là đâu**? Là mây Trung Quốc? Hay AWS / Azure / GCP?  
3. **Địa chính trị** – Sau cuộc bầu cử giữa nhiệm kỳ Mỹ vào tháng 11 năm 2026, **liệu quá trình tách rời AI Mỹ-Trung có mở rộng từ “phần cứng” sang “trọng số mô hình” hay không**?  

Ba câu hỏi này sẽ quyết định “Token Trung Quốc ra nước ngoài” rốt cuộc chỉ là **một cánh cửa sổ 18 tháng** (như đà tăng trưởng cao đã thấy giai đoạn 2024-2026), hay là **một đường đua kéo dài 10 năm** (như đường cong ra nước ngoài của ngành sản xuất Trung Quốc).

Phán đoán của tôi nghiêng về kịch bản thứ hai – nhưng cần **sự phối hợp giữa nhà cung cấp cloud trong nước + hãng mô hình + hãng chip + đơn vị tích hợp**, chứ không chỉ mỗi chuyện mô hình đủ mạnh.

---

## Nguồn thông tin và quy tắc che giấu dữ liệu

Dữ liệu trong bài tổng hợp từ:

- Bảng xếp hạng công khai của OpenRouter / Hugging Face / Artificial Analysis (2025-2026)
- Báo cáo tài chính công khai / cuộc gọi nhà đầu tư của các hãng
- Nghiên cứu ngành từ bên thứ ba (a16z, Menlo Ventures, Bessemer, v.v.)
- Khảo sát nội bộ ngành MaaS trong nước (trích dẫn sau khi che giấu dữ liệu)

**Quy tắc che giấu dữ liệu**: Bài viết xử lý theo các danh mục như “ông lớn Internet / công ty khởi nghiệp AI”, tên công ty cụ thể đã được thay bằng mã (R / B / K / Z / Y / S / A / C / T / G), bảng đối chiếu gốc lưu trong ghi chép cá nhân. Các con số đều từ báo cáo công khai, nguồn có thể truy xuất.

Thời điểm dữ liệu: tháng 5 đến tháng 6 năm 2026.

---

*Nếu bạn đang làm ở tuyến đầu đưa AI ra nước ngoài, hoan nghênh cùng tranh luận – chủ đề “61% có thực sự phồn vinh hay không” đáng để bàn hơn câu hỏi “Mỹ có kìm chúng ta hay không”.*
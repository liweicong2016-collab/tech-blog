---
title: "Nền kinh tế Token và thương mại hóa MaaS của các ông lớn Internet Trung Quốc"
date: 2026-06-04T00:55:00+08:00
draft: false
tags: ["MaaS", "Token", "ByteDance", "Alibaba", "Tencent", "Doubao", "Bailian", "TokenHub"]
description: "ByteDance, Alibaba, Tencent: từ cạnh tranh năng lực mô hình chuyển sang cạnh tranh tổng hợp về quy mô Token, hiệu quả chi phí và cửa ngõ hệ sinh thái. MaaS đang trở thành lớp đo lường mới giữa đám mây và ứng dụng AI."
summary: "Doubao xử lý trung bình 120 nghìn tỷ Token mỗi ngày / Bailian tăng gấp 6 lần sau 3 tháng / TokenHub giảm giá 50-80% — ba tuyến chủ đạo quyết định thắng thua của MaaS năm 2026."
ShowToc: true
TocOpen: true
---

> **Nhận định cốt lõi**: MaaS đang trở thành tầng đo lường mới giữa đám mây và ứng dụng AI. Token không chỉ là đơn vị chi phí, mà còn là ngôn ngữ chung cho định giá sản phẩm, trợ cấp hệ sinh thái, điều phối sức mạnh tính toán và ROI doanh nghiệp.

## Ba con số gây chấn động

| Con số | Nhà cung cấp | Ý nghĩa |
|---|---|---|
| **120 nghìn tỷ+** | ByteDance 豆包 | Lượng Token sử dụng trung bình hàng ngày, được thúc đẩy bởi cả C-end và API doanh nghiệp |
| **6 lần** | Alibaba 百炼 | Mức tiêu thụ Token dịch vụ mô hình công cộng tăng trong ba tháng |
| **50%-80%** | Tencent TokenHub | Mức chiết khấu của gói dịch vụ so với API theo lưu lượng |

## Điều hướng chương

Bài viết này tái hiện chính xác theo 10 slide nghiên cứu gốc, **kèm 10 đồ họa thông tin SVG tông màu lạnh, tối**：

1. [Tóm tắt thực hiện: Ba trục chính](#exec-summary)
2. [Kinh tế Token: Sự kết hợp giữa doanh thu và chi phí](#token-economics)
3. [Thị trường MaaS: Từ API nâng cấp thành hệ điều hành AI](#maas-market)
4. [ByteDance 火山引擎: Dùng lưu lượng ứng dụng để kéo bánh đà Token](#bytedance)
5. [Alibaba 百炼: Biến AI thành tầng tăng trưởng của đám mây](#alibaba)
6. [Tencent 混元 + TokenHub: Đặt cược vào cổng tổng hợp](#tencent)
7. [Ma trận cạnh tranh: Ba bên thâm nhập từ các điểm kiểm soát nhu cầu khác nhau](#matrix)
8. [Hàm ý chiến lược: Tái định hình thiết kế đám mây, phần mềm và sản phẩm dành cho nhà phát triển](#implications)
9. [Triển vọng 2026-2027: Từ phổ cập giá rẻ đến phân tầng hiệu quả](#outlook)
10. [Nguồn tham khảo chính](#sources)

---

<a id="exec-summary"></a>
## 1. Tóm tắt thực hiện: Ba trục chính quyết định thành bại MaaS năm 2026

![Ba trục chính: Token quy mô / Đường cong chi phí đi xuống / Tái sắp xếp cổng sinh thái](/tech-blog/images/maas-ppt/01-three-main-lines.svg)

**Trục chính thứ nhất: Token quy mô** —— Lượng gọi API hàng ngày trở thành chỉ số thương mại hóa AI số một của các nhà cung cấp đám mây. ByteDance tiết lộ lượng Token 豆包 sử dụng trung bình hằng ngày vượt 120 nghìn tỷ, Alibaba tiết lộ mức tiêu thụ Token 百炼 tăng 6 lần trong ba tháng.

**Trục chính thứ hai: Đường cong chi phí đi xuống** —— Giá chuyển từ API theo lưu lượng sang cấu trúc nhiều lớp như Token đầu vào/đầu ra, độ dài ngữ cảnh, Batch, bộ nhớ đệm, gói cước, các nhà cung cấp khoá chân nhà phát triển bằng mô hình giá rẻ.

**Trục chính thứ ba: Tái sắp xếp cổng sinh thái** —— Alibaba thiên về đám mây và ngăn xếp toàn diện doanh nghiệp, ByteDance thiên về lưu lượng ứng dụng và nội dung/Agent, Tencent thiên về kết nối doanh nghiệp, hệ sinh thái WeChat và cổng tổng hợp TokenHub.

> **Hàm ý đầu tư và kinh doanh**: Cốt lõi của MaaS không phải là lợi nhuận gộp của từng mô hình đơn lẻ, mà là lợi nhuận kết hợp của “lưu lượng Token tần suất cao + chi phí suy luận biên thấp + chuyển đổi ứng dụng trong hệ sinh thái”.

Nguồn: 火山引擎, 阿里云百炼, 腾讯云 TokenHub, các báo cáo công khai

---

<a id="token-economics"></a>
## 2. Kinh tế Token: Thiết kế doanh thu gắn với chi phí suy luận

![Công thức kinh tế Token: Token = usage + pricing + compute](/tech-blog/images/maas-ppt/02-token-economics.svg)

### Phía doanh thu

- Định giá riêng biệt theo Token đầu vào/đầu ra, **đầu ra thường đắt hơn**
- Ngữ cảnh dài, chế độ suy nghĩ, đa phương thức, tạo video tạo thành bậc thang giá
- Token Plan, gói năm/tháng và cam kết tiêu dùng doanh nghiệp biến các lời gọi dao động thành doanh thu ổn định

### Phía chi phí

- GPU/chip AI nội địa, HBM, mạng và điện quyết định chi phí nền của suy luận
- Gọi Batch, bộ nhớ đệm ngữ cảnh, chưng cất, định tuyến mô hình nhỏ giảm chi phí đơn vị
- Chuỗi dài Agent sẽ khuếch đại mức tiêu thụ Token, đồng thời tăng tính gắn kết và giá trị khách hàng

### Biến số then chốt × Hàm ý thương mại × Trọng tâm quản lý

| Biến số then chốt | Hàm ý thương mại | Trọng tâm quản lý |
|---|---|---|
| **Đơn giá mỗi triệu Token** | Quyết định ngưỡng tiếp cận nhà phát triển và chi phí thay thế đối thủ | Phổ giá, gói cước, hạn mức miễn phí |
| **Chi phí suy luận đơn vị** | Quyết định độ co giãn lợi nhuận gộp MaaS | Nén mô hình, điều phối, bộ nhớ đệm, cung ứng chip |
| **Tỷ lệ duy trì Token** | Quyết định liệu có chuyển từ dùng thử sang môi trường sản xuất hay không | SLA, chuỗi công cụ, an toàn dữ liệu, khung Agent |

> **Công thức một câu**: `Token = usage + pricing + compute`

---

<a id="maas-market"></a>
## 3. Thị trường MaaS: Từ API mô hình nâng cấp thành hệ điều hành AI

![Ngăn xếp ba tầng MaaS: tầng mô hình / tầng nền tảng / tầng ứng dụng](/tech-blog/images/maas-ppt/03-maas-stack.svg)

| Tầng | Năng lực | Thu giữ giá trị | Trọng tâm cạnh tranh |
|---|---|---|---|
| **Tầng mô hình** | Đa năng, suy luận, code, đa phương thức, video, giọng nói | Tính phí theo Token/nhiệm vụ | Hiệu năng, chi phí, ngữ cảnh, chiến lược nguồn mở/đóng |
| **Tầng nền tảng** | Chợ mô hình, cổng API, đánh giá, giám sát, quản trị dữ liệu | Hợp đồng doanh nghiệp, gói cước, liên kết tài nguyên đám mây | Trải nghiệm phát triển, SLA, tuân thủ và triển khai riêng |
| **Tầng ứng dụng** | Agent, văn phòng, chăm sóc khách hàng, tiếp thị, tìm kiếm, sinh code | Đăng ký, giá trị gia tăng, quảng cáo, chuyển đổi thương mại điện tử | Vòng khép kín ngữ cảnh, cổng người dùng, độ kết dính luồng công việc |

> **Nhận định then chốt 2026**: Cạnh tranh không còn là “ai có mô hình”, mà là ai có thể nhúng mô hình vào quy trình doanh nghiệp và các điểm tiếp xúc người tiêu dùng, đồng thời tích lũy các lời gọi tần suất cao thành doanh thu Token có thể dự báo.

---

<a id="bytedance"></a>
## 4. ByteDance 火山引擎: Dùng lưu lượng ứng dụng để kéo bánh đà Token

![ByteDance 火山引擎: 豆包 120 nghìn tỷ + ma trận cổng vào](/tech-blog/images/maas-ppt/04-bytedance.svg)

**Con số cốt lõi: Lượng Token 豆包 sử dụng trung bình hằng ngày vượt 120 nghìn tỷ**

Các báo cáo công khai cho thấy, lượng Token sử dụng trung bình hằng ngày của mô hình lớn 豆包 đã vượt 120 nghìn tỷ, thể hiện lợi thế quy mô lời gọi từ ứng dụng C-end đến API doanh nghiệp.

### Chiến thuật sản phẩm

Dòng 豆包 2.0 bao phủ các cấp **Pro, Lite, Mini, Code**, dùng năng lực/chi phí khác nhau để phối hợp với Agent, lập trình và các ngữ cảnh chung.

### Đòn bẩy thương mại hóa

- **火山方舟** tiếp nhận API doanh nghiệp
- Hệ sinh thái **豆包 / 即梦 / 抖音** đóng góp ngữ cảnh ứng dụng
- Các công cụ phát triển như **TRAE** khuếch đại mức tiêu thụ Token dạng code

### SWOT

| Điểm mạnh | Hạn chế |
|---|---|
| Cổng vào C-end tần suất cao, ngữ cảnh sinh nội dung phong phú, giá quyết liệt | Tâm trí đám mây doanh nghiệp yếu hơn Alibaba/Tencent, cần chứng minh SLA và khả năng triển khai ngành |

> **Chỉ số quan sát**: Doanh thu MaaS doanh nghiệp, tỷ lệ duy trì Token Plan, chuyển đổi ứng dụng Agent

Nguồn: Tân Lãng Khoa Kỹ; cộng đồng nhà phát triển 火山引擎, API 豆包 2.0

---

<a id="alibaba"></a>
## 5. Alibaba 百炼: Biến AI thành tầng tăng trưởng của đám mây

![Alibaba 百炼: 3 tháng 6 lần + bậc thang giá](/tech-blog/images/maas-ppt/05-alibaba.svg)

**Con số cốt lõi: Mức tiêu thụ Token 百炼 tăng 6 lần trong ba tháng**

Ban lãnh đạo Alibaba tiết lộ, mức tiêu thụ Token trên thị trường dịch vụ mô hình công cộng của nền tảng MaaS 百炼 đã tăng 6 lần trong ba tháng.

### Cấu trúc giá

Trang giá chính thức của 百炼 cho thấy, dòng Qwen được phân lớp theo **độ dài ngữ cảnh, đầu vào/đầu ra, chế độ suy nghĩ**; gọi Batch và bộ nhớ đệm ngữ cảnh cung cấp chiết khấu.

### Tự sự toàn ngăn xếp

Từ **AI Infra, chip/máy chủ, mô hình, nền tảng 百炼 đến trang ứng dụng 千问**, Alibaba cố gắng gắn kết doanh thu Token với mức tiêu thụ tài nguyên đám mây.

### SWOT

| Điểm mạnh | Hạn chế |
|---|---|
| Cơ sở khách hàng đám mây, khả năng triển khai doanh nghiệp, hệ sinh thái Qwen nguồn mở, hệ thống giá minh bạch | Cổng vào siêu ứng dụng C-end tương đối phân tán, chiến tranh giá thấp nén lợi nhuận gộp ngắn hạn |

> **Chỉ số quan sát**: Tỷ trọng doanh thu 百炼 trong Alibaba Cloud, tỷ lệ chuyển đổi dự án Agent doanh nghiệp sang sản xuất

Nguồn: Trang giá chính thức của 阿里云百炼; Tân Lãng Tài Chính; Mỗi Kinh Võng

---

<a id="tencent"></a>
## 6. Tencent 混元 + TokenHub: Đặt cược vào cổng tổng hợp

![Tencent TokenHub: chiết khấu 50-80% + cổng tổng hợp](/tech-blog/images/maas-ppt/06-tencent.svg)

### Cổng nền tảng

**腾讯云 TokenHub định vị là cổng vào dịch vụ mô hình lớn thống nhất**, tích hợp 混元 và giới thiệu mô hình bên thứ ba, bao phủ các ngữ cảnh hội thoại, suy luận, code, thị giác, hình ảnh và video.

**Chiết khấu gói cước: 50%-80%** —— Trang sản phẩm TokenHub nhấn mạnh gói cước rẻ hơn 50%-80% so với tính phí theo API lưu lượng, dùng trả trước và gói lưu lượng để giảm cảm nhận chi phí biên của nhà phát triển.

### Lặp mô hình

Bản preview 混元 Hy3 đã được phát hành nguồn mở, dữ liệu công khai cho thấy giá đầu vào khoảng **1,2 NDT/triệu Token**, đồng thời ra mắt Token Plan dành cho nhà phát triển Agent.

### SWOT

| Điểm mạnh | Hạn chế |
|---|---|
| Hệ sinh thái WeChat/WeCom/Tencent Meeting/đám mây và bảo mật, nền tảng tổng hợp thuận lợi cho quản trị đa mô hình doanh nghiệp | Cần cân bằng giữa tâm trí mô hình tự nghiên cứu và thu giữ giá trị khi tổng hợp bên thứ ba |

> **Chỉ số quan sát**: Tỷ lệ mua lại gói TokenHub, hệ sinh thái nguồn mở 混元, lưu lượng gọi trong ngữ cảnh WeChat

Nguồn: Trang sản phẩm 腾讯云 TokenHub; cộng đồng nhà phát triển 腾讯云

---

<a id="matrix"></a>
## 7. Ma trận cạnh tranh: Ba bên thâm nhập từ các điểm kiểm soát nhu cầu khác nhau

![Ma trận so sánh ba bên: bản đồ nhiệt 6 chiều](/tech-blog/images/maas-ppt/07-matrix.svg)

| Chiều | ByteDance | Alibaba | Tencent |
|---|---|---|---|
| **Cổng vào cốt lõi** | 豆包, 抖音, 即梦, TRAE, 火山方舟 | 阿里云百炼, 千问, khách hàng doanh nghiệp đám mây | 腾讯云 TokenHub, 混元, hệ sinh thái WeChat/WeCom |
| **Nguồn tăng trưởng Token** | Tương tác tần suất cao C-end, sinh nội dung, Agent lập trình | Ứng dụng doanh nghiệp, luồng công việc AI trên đám mây, di cư hệ sinh thái nguồn mở | Cộng tác doanh nghiệp, hệ sinh thái WeChat, tổng hợp mô hình bên thứ ba |
| **Phong cách định giá** | Mô hình hiệu suất/giá cao + kế hoạch ngưỡng thấp | Giá phân lớp minh bạch + chiết khấu Batch/bộ nhớ đệm | Khoá giá gói + ưu đãi gọi tổng hợp |
| **Cơ hội lớn nhất** | Biến lưu lượng C-end thành doanh thu MaaS cấp doanh nghiệp | Khiến MaaS trở thành một trong những dòng sản phẩm lớn nhất của Alibaba Cloud | Trở thành cổng vào gọi và quản trị đa mô hình cho doanh nghiệp |
| **Rủi ro chính** | Xây dựng tâm trí về triển khai và tuân thủ doanh nghiệp | Chiến tranh giá và áp lực chi phí sức mạnh tính toán lên lợi nhuận gộp | Nền tảng tổng hợp làm loãng sự khác biệt của mô hình tự nghiên cứu |

> So sánh chiến lược dựa trên định vị sản phẩm công khai, trang giá và các báo cáo công khai năm 2026

---

<a id="implications"></a>
## 8. Hàm ý chiến lược: Tái định hình thiết kế đám mây, phần mềm và sản phẩm dành cho nhà phát triển

![Sơ đồ tác động: bốn góc phần tư Đám mây / Doanh nghiệp / Nhà phát triển / Nhà đầu tư](/tech-blog/images/maas-ppt/08-implications.svg)

### Đối với nhà cung cấp đám mây

- MaaS sẽ trở thành mặt tiền mới cho tài nguyên đám mây, phía sau gắn kết GPU, lưu trữ, mạng và an toàn dữ liệu
- Chiến tranh giá là không thể tránh khỏi, mấu chốt là dùng bộ nhớ đệm, Batch, định tuyến mô hình và chip tự nghiên cứu để duy trì lợi thế chi phí

### Đối với khách hàng doanh nghiệp

- Tiêu chuẩn mua sắm chuyển từ điểm số bảng xếp hạng mô hình sang **tổng chi phí sở hữu, độ ổn định, cô lập dữ liệu và tích hợp luồng công việc**
- Dự án Agent phải thiết lập ngân sách Token, quy kết hiệu quả và chiến lược tự động giáng cấp

### Đối với nhà phát triển

- **Định tuyến đa mô hình, bộ nhớ đệm prompt, nén ngữ cảnh, tái sử dụng kết quả** sẽ trở thành kỹ năng cơ bản quyết định tỷ suất lợi nhuận ứng dụng

### Đối với nhà đầu tư

- Nên theo dõi **mức tiêu thụ Token, tỷ lệ duy trì có trả phí, chi phí suy luận đơn vị, tỷ trọng doanh thu đám mây AI**, thay vì chỉ nhìn vào nhịp độ phát hành mô hình

---

<a id="outlook"></a>
## 9. Triển vọng 2026-2027: Từ phổ cập giá rẻ đến phân tầng hiệu quả

![Triển vọng 2026-2027: dòng thời gian xu hướng](/tech-blog/images/maas-ppt/09-outlook.svg)

### Ba dự báo

1. **Giá tiếp tục phân tầng**: Mô hình chủ lực tăng giá hoặc giữ ổn định, mô hình Lite/Mini gánh vác lưu lượng phổ cập
2. **MaaS doanh nghiệp chuyển từ thí điểm sang sản xuất**: Agent, chăm sóc khách hàng, code, nội dung tiếp thị sẽ tăng lượng trước
3. **Nền tảng chuyển từ bán API sang bán quản trị**: Chợ mô hình, kiểm toán, định tuyến, kiểm soát chi phí trở thành tiêu chuẩn

### Khuyến nghị

| Vai trò | Khuyến nghị |
|---|---|
| **Nhà cung cấp** | Dùng Token Plan khoá chân nhà phát triển tần suất cao, đồng thời công khai SLA và năng lực tối ưu chi phí |
| **Doanh nghiệp** | Xây dựng chiến lược đa nhà cung cấp, phân tách cấp độ mô hình theo nhiệm vụ, tránh bị khoá chặt vào chi phí một mô hình duy nhất |
| **Nhà phát triển** | Đưa chi phí Token vào thiết kế sản phẩm, mặc định làm bộ nhớ đệm, nén và định tuyến mô hình |

---

<a id="sources"></a>
## 10. Nguồn tham khảo chính

- 阿里云百炼 trang giá mô hình: help.aliyun.com/zh/model-studio/model-pricing
- 腾讯云 TokenHub trang sản phẩm: cloud.tencent.com/product/tokenhub
- Cộng đồng nhà phát triển 腾讯云, bản preview 混元 Hy3: developer.cloud.tencent.com/article/2660040
- Cộng đồng nhà phát triển 火山引擎, API 豆包 2.0: developer.volcengine.com/articles/7610285824933445675
- Tân Lãng Khoa Kỹ, lượng Token sử dụng hằng ngày của 豆包 vượt 120 nghìn tỷ: finance.sina.com.cn/tech/roll/2026-04-02/doc-inhtazrx7826779.shtml
- Tân Lãng Tài Chính, mức tiêu thụ Token 百炼 tăng 6 lần trong ba tháng: finance.sina.com.cn/tob/2026-03-19/doc-inhrpspp8552821.shtml
- Mỗi Kinh Võng, tự sự MaaS và Agent của 阿里云: nbd.com.cn/articles/2026-05-21/4402582.html

*Nguồn được kiểm tra tháng 6/2026*

---

## Tổng kết một câu

> **Thành bại của MaaS không phụ thuộc vào “ai có mô hình mạnh nhất”, mà phụ thuộc vào “ai có thể tích luỹ lưu lượng Token thành doanh thu đám mây có thể dự báo”** —— Đây là tự sự cốt lõi của thị trường đám mây Trung Quốc năm 2026.

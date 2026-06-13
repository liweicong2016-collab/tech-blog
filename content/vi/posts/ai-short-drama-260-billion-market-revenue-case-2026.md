---
title: "Thị trường AI kịch ngắn 260 tỷ: Cách mô hình video lớn kiếm tiền"
date: 2026-06-03
draft: false
description: "Dữ liệu ngành công khai ngày 3/6/2026 cho thấy một mô hình video đạt doanh thu 1 tỷ NDT/tháng, ARR ước tính tối thiểu 15 tỷ NDT+, chiếm 58% giá trị sản lượng hàng năm của AI kịch ngắn Trung Quốc. Bài viết phân tích cách Mô hình Giáp dùng API xuyên thủng chuỗi cung ứng kịch ngắn trong 4 tháng, ai trả tiền, tại sao không thể thay thế, và ý nghĩa cuối cùng cho cuộc chiến MaaS của các nhà cung cấp đám mây Trung Quốc."
tags: ["MaaS", "Kinh tế Token", "AI kịch ngắn", "Mô hình video lớn", "Nghiên cứu điển hình kiếm tiền", "AI nội địa", "Seedance", "Douyin", "Kling", "Kuaishou"]
slug: "ai-short-drama-260-billion-market-revenue-case-2026"
cover:
  image: "https://images.unsplash.com/photo-1574717024653-61fd2cf4d44d?w=1200&q=80"
  alt: "AI kịch ngắn và tạo video"
  caption: "AI kịch ngắn Trung Quốc sản lượng hàng năm 260 tỷ, riêng Mô hình Giáp chiếm 58%"
ShowToc: true
---

<link rel="stylesheet" href="/tech-blog/css/bis.css">

<div class="bis-wrap">

<div class="bis-hero">
  <span class="tag">Case study kiếm tiền · 2026-06-03</span>
  <h1>Thị trường AI phim ngắn 260 tỷ: Các mô hình video lớn kiếm tiền như thế nào</h1>
  <p class="subtitle">Một mô hình video bán 1 tỷ/tháng / ARR thận trọng 15 tỷ+ / Chiếm 58% sản lượng phim ngắn — Case study xuyên thủng chuỗi công nghiệp chỉ trong 4 tháng</p>
  <p class="date">2026-06-03 · Case study ngành</p>
</div>

<div class="bis-alert">
  <strong>Đây là một case study đi ngược lại trực giác thông thường</strong>. Ra mắt ngày 10/02/2026, doanh số một tháng vượt 1 tỷ nhân dân tệ chỉ trong 4 tháng; đó không phải là một "ứng dụng tiêu dùng" (các nhà sáng tạo trên Xiaohongshu/Douyin/Video WeChat hoàn toàn không dùng API), mà là <strong>một API B2B thuần túy</strong>, khách hàng <strong>hầu như toàn bộ là các công ty AI phim ngắn</strong>. Bài viết này phân tích cách nó kiếm tiền, ai đang trả tiền, tại sao đối thủ không đuổi kịp, và ý nghĩa cuối cùng đối với chiến trường MaaS Trung Quốc.
</div>

<div class="bis-signal">
<h3>💡 Key Takeaways</h3>
<ul>
  <li><strong>API B2B là con đường đúng đắn để kiếm tiền từ mô hình video</strong> — Người sáng tạo C-end dùng Jimeng/XiaoYunQue (đăng ký/miễn phí), các công ty phim ngắn B-end dùng API (tính phí theo Token); hai thị trường không chồng lấn, toàn bộ doanh số 1 tỷ/tháng đến từ B-end</li>
  <li><strong>Quy mô doanh thu mô hình video đã vượt tất cả các mô hình LLM đa dụng</strong> — ARR ước tính thận trọng của Mô hình A là 15 tỷ, bằng 100% mục tiêu MaaS 2026 của ByteDance (15 tỷ), vượt bất kỳ doanh thu công ty LLM đơn lẻ nào</li>
  <li><strong>58% giá trị sản xuất AI phim ngắn đổ vào khâu sinh nội dung</strong> — Các công ty phim ngắn trả được tiền vì ARPU người dùng 10-50 nhân dân tệ, tỷ lệ mua lại cao, ROI quảng cáo vẫn dương; sau khi thay thế chi phí quay phim người thật bằng AI, ROI tổng thể vẫn dương</li>
  <li><strong>Khoảng cách 4,4 lần có nghĩa người dùng thậm chí còn chưa thử Kling</strong> — ARR của Kling 3,4 tỷ so với Mô hình A 15 tỷ; chi phí chuyển đổi (viết lại workflow 3-6 tháng, tổn thất năng lực sản xuất hàng chục triệu nhân dân tệ) khiến các công ty phim ngắn không thể di chuyển</li>
  <li><strong>Cuộc chiến điểm đơn lẻ trong mảng sinh video đã kết thúc</strong> — Mô hình A thực tế độc quyền trên một kênh video cloud hàng đầu; các nhà cung cấp cloud khác nên chuyển hướng sang giải pháp đa phương thức, giải pháp ngành và nền tảng Agent</li>
</ul>
</div>

<!-- ============ MOD-01 一图速览 ============ -->
<div class="bis-section">
<h2><span class="num">1</span>Tổng quan một hình — Dữ liệu công khai ngày 03/06/2026</h2>

<div class="bis-grid">
  <div class="bis-card red">
    <span class="val">1<span style="font-size:14px"> tỷ/tháng</span></span>
    <span class="lab">Doanh số tháng của một kênh video cloud hàng đầu</span>
  </div>
  <div class="bis-card">
    <span class="val">15<span style="font-size:14px"> tỷ+</span></span>
    <span class="lab">Ước tính ARR thận trọng</span>
  </div>
  <div class="bis-card green">
    <span class="val">3,4<span style="font-size:14px"> tỷ</span></span>
    <span class="lab">ARR của Kling (so sánh ngang)</span>
  </div>
  <div class="bis-card purple">
    <span class="val">~58%</span>
    <span class="lab">Chiếm sản lượng AI phim ngắn Trung Quốc</span>
  </div>
  <div class="bis-card">
    <span class="val">26<span style="font-size:14px"> tỷ</span></span>
    <span class="lab">Giá trị sản xuất AI phim ngắn Trung Quốc ước trung vị</span>
  </div>
  <div class="bis-card red">
    <span class="val">95%</span>
    <span class="lab">Tỷ lệ thâm nhập API ngành phim ngắn</span>
  </div>
</div>

<p><strong>Tín hiệu cốt lõi</strong>: Mô hình video lớn (không phải LLM, không phải mô hình hình ảnh) lần đầu tiên trở thành dịch vụ MaaS <strong>doanh thu điểm đơn vượt 10 tỷ</strong>. Quy mô này <strong>đã</strong> vượt qua doanh thu của bất kỳ công ty LLM đa dụng đơn lẻ nào, <strong>bằng 100% mục tiêu MaaS 2026 của ByteDance là 15 tỷ</strong>.</p>
</div>

<!-- ============ MOD-02 数据来源与口径 ============ -->
<div class="bis-section">
<h2><span class="num">2</span>Nguồn dữ liệu và cách tính (bắt buộc đọc)</h2>

<p>Ngày 03/06/2026, một cuộc thảo luận trong ngành đã công bố một bộ số liệu, với <strong>cách tính gốc</strong> như sau:</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Chỉ số</th>
      <th>Giá trị</th>
      <th>Thời điểm</th>
      <th>Đơn vị công bố</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Doanh số tháng của một mô hình video (Mô hình A) trên một kênh video cloud hàng đầu</td>
      <td><strong>1 tỷ nhân dân tệ</strong></td>
      <td>06/2026</td>
      <td>Công khai trong thảo luận ngành</td>
    </tr>
    <tr>
      <td>ARR tương ứng (tính theo năm)</td>
      <td>~12 tỷ nhân dân tệ</td>
      <td>06/2026</td>
      <td>Tính niên suất đơn giản</td>
    </tr>
    <tr>
      <td>ARR mới nhất của Kling (Kuaishou)</td>
      <td>3,4 tỷ nhân dân tệ</td>
      <td>2026 tính đến hiện tại</td>
      <td>Công khai từ báo cáo tài chính Kuaishou</td>
    </tr>
    <tr>
      <td>Sản lượng niên xuất AI phim ngắn Trung Quốc</td>
      <td>22-30 tỷ nhân dân tệ (trung vị 26 tỷ)</td>
      <td>2026 tính đến hiện tại</td>
      <td>Kasi/Juliang Engine</td>
    </tr>
    <tr>
      <td>Mục tiêu MaaS 2026 của một hãng video cloud hàng đầu</td>
      <td>15 tỷ nhân dân tệ</td>
      <td>04/2026 điều chỉnh tăng</td>
      <td>OKR nội bộ</td>
    </tr>
    <tr>
      <td>Doanh thu MaaS thực tế 2025 của một hãng video cloud hàng đầu</td>
      <td>~1,5 tỷ nhân dân tệ</td>
      <td>Cả năm 2025</td>
      <td>Ước tính ngành</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>Một thực tế ẩn quan trọng</strong>:</p>

<ul>
  <li>Một hãng video cloud hàng đầu <strong>cả năm 2025 MaaS thực tế ~1,5 tỷ</strong></li>
  <li>Một hãng video cloud hàng đầu <strong>mục tiêu cả năm 2026 là 15 tỷ</strong> (<strong>tăng trưởng gấp 10 lần</strong>)</li>
  <li>Mô hình A <strong>doanh số tháng chỉ một mô hình</strong> đã 1 tỷ, ARR 15 tỷ+</li>
  <li>Nói cách khác: <strong>gần như toàn bộ 100% mục tiêu 2026 của cloud đó đến từ Mô hình A</strong>, các mô hình video khác đóng góp tỷ lệ nhỏ</li>
</ul>

<div class="bis-quote">
"Tăng trưởng gấp 10 lần so với cùng kỳ không đến từ mở rộng mặt khách hàng, mà đến từ <strong>sự bùng nổ về lượng từ một khách hàng đơn lẻ (công ty AI phim ngắn) trên một điểm tiếp xúc duy nhất (API sinh video)</strong>." —— Nhận định ngành 03/06/2026
</div>
</div>

<!-- ============ MOD-03 ARR 测算的三大变量 ============ -->
<div class="bis-section">
<h2><span class="num">3</span>Từ doanh số tháng 1 tỷ đến ARR 15 tỷ — Ba biến số</h2>

<p>Tính niên suất trực tiếp: 1 tỷ × 12 = 12 tỷ. Nhưng <strong>ARR thực tế sẽ cao hơn</strong>, vì:</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Biến số</th>
      <th>Tỷ lệ đóng góp</th>
      <th>Giải thích</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Cơ sở: Doanh số tháng trên kênh video cloud hàng đầu</td>
      <td>1 tỷ/tháng</td>
      <td>Điểm công bố dữ liệu</td>
    </tr>
    <tr>
      <td>① Cân đối giai đoạn tăng trưởng</td>
      <td>+20-30%</td>
      <td>Hoạt động vẫn đang tăng</td>
    </tr>
    <tr>
      <td>② Kênh bên thứ ba</td>
      <td>+15-20%</td>
      <td>Một số đại lý được ủy quyền</td>
    </tr>
    <tr>
      <td>③ Ngoại tuyến chưa toàn lượng</td>
      <td>+30-50%</td>
      <td>Phần gia tăng sau khi chính thức ra mắt tại nước ngoài</td>
    </tr>
    <tr>
      <td><strong>Ước tính ARR thận trọng</strong></td>
      <td><strong>~15 tỷ nhân dân tệ</strong></td>
      <td>Thận trọng hơi thấp</td>
    </tr>
    <tr>
      <td>Ước tính ARR lạc quan (bao gồm ngoại bộ)</td>
      <td>~25-30 tỷ nhân dân tệ</td>
      <td>Sau khi toàn lượng ngoại bộ trong 12-18 tháng</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>Phán định then chốt</strong>:</p>

<ul>
  <li><strong>15 tỷ</strong> là con số <strong>thận trọng</strong> hướng thấp, không phải con số lạc quan</li>
  <li>Mức tăng 30-50% từ ngoại bộ <strong>chưa chắc đã rơi xuống trong 12 tháng</strong> — khách hàng ngoại dùng video API của cloud Trung Quốc, <strong>tuân thủ + niềm tin + kênh thanh toán</strong> đều có rào cản</li>
  <li>Tuyên bố bên ngoài "ARR 15 tỷ" là <strong>thận trọng hợp lý</strong>, không có độn nước</li>
</ul>
</div>

<!-- ============ MOD-04 谁在付钱？======== -->
<div class="bis-section">
<h2><span class="num">4</span>Ai đang trả tiền — Khách hàng thực của API</h2>

<p>Điều này rất dễ bị hiểu sai thành "nhà sáng tạo chỉ cần dùng Jimeng, XiaoYunQue là đủ", nhưng <strong>đó là C-end</strong>. Những ai dùng API <strong>hầu như toàn bộ là các công ty AI phim ngắn</strong>.</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Loại khách hàng</th>
      <th>Phương thức sử dụng</th>
      <th>Phương thức tính phí</th>
      <th>Tỷ lệ đóng góp vào doanh thu Mô hình A</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Công ty AI phim ngắn</strong> (Hongguo, Dianzhong, Jiuzhou, v.v.)</td>
      <td>API hàng loạt, sinh đoạn video trên 5 giây</td>
      <td>Theo Token (số giây video)</td>
      <td><strong>~95%</strong></td>
    </tr>
    <tr>
      <td>Nhà sáng tạo Xiaohongshu/Douyin/Video WeChat (C-end)</td>
      <td>Dùng ứng dụng "đủ dùng" như Jimeng, XiaoYunQue</td>
      <td>Đăng ký / miễn phí</td>
      <td>Gần như 0</td>
    </tr>
    <tr>
      <td>Công ty quảng cáo / marketing</td>
      <td>API quảng cáo ngắn / tài liệu thương hiệu</td>
      <td>Theo Token</td>
      <td>~3%</td>
    </tr>
    <tr>
      <td>Công ty game / hoạt hình</td>
      <td>API diễn tập kịch bản / nguyên mẫu</td>
      <td>Theo Token</td>
      <td>~1%</td>
    </tr>
    <tr>
      <td>Nhà phát triển cá nhân / dự án giai đoạn đầu</td>
      <td>API thí điểm</td>
      <td>Theo Token</td>
      <td>~1%</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>Điểm ngược trực giác chính</strong>:</p>

<ul>
  <li>Mô hình A <strong>không phải "ứng dụng tiêu dùng"</strong>, mà là <strong>MaaS B2B thuần túy</strong></li>
  <li>Nhà sáng tạo trên Xiaohongshu/Douyin/Video WeChat <strong>chưa bao giờ là người dùng trả tiền</strong></li>
  <li>Vì vậy "nhà sáng tạo dùng Jimeng" và "Mô hình A bán 1 tỷ/tháng" là <strong>hai việc hoàn toàn không mâu thuẫn</strong></li>
  <li>Điều này giải thích một câu hỏi then chốt: <strong>Tại sao một API hướng B-end có thể đạt doanh số tháng 1 tỷ, mà không bị tác động bởi một sự kiện ăn khách nào đó như ứng dụng tiêu dùng</strong> — khách hàng của nó <strong>là các công ty thương mại</strong>, không phải "người dùng"</li>
</ul>

<div class="bis-punchline">
<h2>🎬 "Phục vụ thị trường năng suất sản xuất" — API B-end mới là con đường kiếm tiền đúng đắn cho mô hình video</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
  <strong>Nhà sáng tạo dùng Jimeng, XiaoYunQue là đủ</strong> (C-end, chế độ đăng ký, chia sẻ lưu lượng).<br>
  <strong>Sử dụng API hầu như toàn bộ là các công ty AI phim ngắn</strong> (B-end, tính phí Token, thị trường năng suất).<br>
  Hai thị trường <strong>không chồng lấn</strong>.<strong>Doanh số tháng 1 tỷ, ARR 15 tỷ</strong>, <strong>tất cả đều đến từ B-end</strong>.
</p>
</div>
</div>

<!-- ============ MOD-05 为什么 AI 短剧要付这个钱 ============ -->
<div class="bis-section">
<h2><span class="num">5</span>Kinh tế học — Tại sao các công ty AI phim ngắn trả được tiền này</h2>

<p>"Tại sao các công ty AI phim ngắn có thể gánh được doanh số tháng 1 tỷ?" <strong>Hãy suy ngược lại</strong> toàn bộ chuỗi công nghiệp AI phim ngắn Trung Quốc:</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Khâu</th>
      <th>Tỷ lệ sản lượng phim ngắn</th>
      <th>Số tiền tương ứng (theo sản lượng 26 tỷ)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Kịch bản / phân cảnh / sáng tạo</td>
      <td>~5%</td>
      <td>1,3 tỷ nhân dân tệ</td>
    </tr>
    <tr>
      <td><strong>API sinh video (Mô hình A, v.v.)</strong></td>
      <td><strong>~58%</strong></td>
      <td><strong>~15 tỷ nhân dân tệ</strong></td>
    </tr>
    <tr>
      <td>Thay thế diễn viên / lồng tiếng / hậu kỳ</td>
      <td>~10%</td>
      <td>2,6 tỷ nhân dân tệ</td>
    </tr>
    <tr>
      <td>Phân phối nội dung / quảng cáo</td>
      <td>~20%</td>
      <td>5,2 tỷ nhân dân tệ</td>
    </tr>
    <tr>
      <td>Vận hành / chia sẻ nền tảng / lợi nhuận</td>
      <td>~7%</td>
      <td>1,9 tỷ nhân dân tệ</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>Quan sát chính</strong>:</p>

<ul>
  <li><strong>58%</strong> sản lượng được chuyển thẳng cho khâu sinh nội dung (chủ yếu là Mô hình A)</li>
  <li>Biên lợi nhuận của các công ty phim ngắn bị <strong>siết chặt nghiêm trọng</strong>, nhưng vẫn có thể hoạt động <strong>nghĩa là</strong>:<br>
    ① Người dùng có ý định chi trả mạnh (giá mỗi phim ngắn 1-10 nhân dân tệ, ARPU 10-50 nhân dân tệ, tỷ lệ mua lại cao)<br>
    ② ROI quảng cáo vẫn dương (phân phối nội dung qua Douyin / ứng dụng Hongguo)<br>
    ③ <strong>Tăng hiệu suất</strong> khâu sinh nội dung khiến tổng chi phí giảm (AI thay thế chi phí quay phim người thật)</li>
  <li>Nếu Mô hình A <strong>không</strong> đẩy doanh số tháng lên 1 tỷ, các công ty AI phim ngắn <strong>không đủ tiền</strong> trả cho các khâu khác (sáng tạo, quảng cáo)</li>
  <li><strong>Đây là một vòng khép kín</strong>: Mô hình A giá rẻ → sản lượng phim ngắn bùng nổ → quảng cáo thu hồi → lượng dùng Mô hình A tiếp tục tăng</li>
</ul>

<div class="bis-signal">
<h3>🔄 Giá đơn vị vs sản lượng — Sự khác biệt căn bản giữa mô hình video và SaaS truyền thống</h3>
<p>SaaS truyền thống: <strong>giá đơn vị giảm = lợi nhuận giảm</strong> (số tiền thu được từ mỗi người dùng ít hơn).<br>
Mô hình video lớn: <strong>giá đơn vị giảm = tổng tiền tăng</strong> (cùng một số tiền có thể sinh ra nhiều video hơn, năng lực sản xuất của công ty AI phim ngắn mở rộng, thực tế dùng nhiều hơn).</p>
<p>Đó là lý do tại sao "tăng giá không làm giảm lượng dùng" ở mô hình video <strong>còn rõ ràng hơn ở mô hình Coding</strong> — video là <strong>nhu cầu hoàn toàn co giãn</strong>, giá thấp một chút thì sinh gấp đôi video, giá cao một chút thì sinh ít đi một nửa, <strong>đối với các công ty phim ngắn, ROI luôn dương</strong>, chỉ

（150 亿 vs 34 亿，<strong>价格战 = 自杀</strong>）</li>
  <li>✅ <strong>应该</strong>切<strong>模型甲没覆盖的细分场景</strong>：<br>
    ① 超长视频（5 分钟以上连续剧情）<br>
    ② 3D / 虚拟人 / 数字孪生（短剧外的工业场景）<br>
    ③ 海外华人 / 东南亚市场（模型甲海外未全量）</li>
  <li>✅ <strong>应该</strong>走<strong>开源 / 本地部署</strong>路线（避开与模型甲的正面 API 竞争）</li>
</ul>
</div>

<!-- ============ MOD-07 给中国 MaaS 战场的终局意义 ============ -->
<div class="bis-section">
<h2><span class="num">7</span>终局意义 — 中国云厂商 MaaS 战争"提前结束"？</h2>

<p>2026/6/3 行业讨论的<strong>核心判断</strong>：</p>

<div class="bis-quote">
"<strong>中国云厂商在 MaaS 市场的战争，至少在今年，是已经提前结束了。</strong>" —— 2026/6/3 行业判断
</div>

<p>对此判断的<strong>拆解</strong>：</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>论断</th>
      <th>成立？</th>
      <th>适用范围</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>视频生成赛道胜负已分</td>
      <td>✅ 成立</td>
      <td>模型甲在某头部视频云渠道事实上无对手</td>
    </tr>
    <tr>
      <td>Coding 战场胜负已分</td>
      <td>❌ 不成立</td>
      <td>公司 X / 公司 Y / 公司 Z 多家头部并存</td>
    </tr>
    <tr>
      <td>LLM 通用赛道胜负已分</td>
      <td>❌ 不成立</td>
      <td>已被地板价击穿，<strong>不是赢家通吃</strong>，而是<strong>没人赚钱</strong></td>
    </tr>
    <tr>
      <td>整体 MaaS 平台胜负已分</td>
      <td>❌ 不成立</td>
      <td>公司 B / 公司 C 仍在持续投入，2026 Q3 见分晓</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>更准确的表述</strong>：</p>

<ul>
  <li><strong>"单点模型"（视频生成）的战争在某头部视频云渠道已赢</strong>——这是个 B2B API 胜者为王的故事</li>
  <li><strong>"整体 MaaS 平台"的战争远远没结束</strong>——多模态、API 编排、行业方案仍在打</li>
  <li>对<strong>其他云厂商</strong>（公司 B / 公司 C）：<strong>别再正面打视频生成 API</strong>，转去打：
    <ul>
      <li>多模态组合（视频 + 图像 + 文本 + 语音）</li>
      <li>行业方案（金融 / 制造 / 教育的 Agent）</li>
      <li>Agent 平台（多模型编排 + 业务流）</li>
    </ul>
  </li>
</ul>

<div class="bis-punchline">
<h2>🎯 关键判断：B2B API 才是中国 MaaS 的终局</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
  <strong>C 端创作者 = 流量 / 品牌 / 拉新</strong>（亏本换市场）<br>
  <strong>B 端 API = 营收 / 利润 / 复利</strong>（赚钱靠这个）<br><br>
  模型甲的成功路径证明：<strong>当一个 AI 模型能做到 SOTA + 5 个月先发优势 + 95% 行业渗透 + 切换成本极高时，B2B API 收入能跑到 150 亿 ARR</strong>——这比所有 LLM 通用模型、所有 C 端 App、所有订阅业务<strong>都赚得多</strong>。
</p>
</div>
</div>

<!-- ============ MOD-08 给海外客户的启示 ============ -->
<div class="bis-section">
<h2><span class="num">8</span

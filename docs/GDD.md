# GDD v3.0 – Petty Pantheon (Đền Thần Nhỏ Nhen)

17/11/2026 · Bản hợp nhất từ *Petty Pantheon v1* (repo) và *GODFORGE: AI PANTHEON v2.0* (Google Doc), có bổ sung nghiên cứu thị trường.

## 0. Tóm tắt một trang

**Pitch:** Một god game cho nhóm bạn. 2–4 vị thần nhỏ nhen phải **cùng nhau** giữ thế giới qua các thảm hoạ, nhưng cuối ván **chỉ một thần** được dân thờ nhiều nhất. Dân biết nhớ ai đã cứu, ai đã hại mình, và học cách chống lại thần.

**Luật chơi trong một câu:** *Cứu thế giới cùng nhau, giành tín đồ của nhau. Thế giới chết thì tất cả đều thua.*

**Ba quyết định lớn của v3:**

1. **Bán bán-hợp-tác (co-opetition).** Phần co-op lấy từ GODFORGE: combo phép, khủng hoảng chung. Phần cạnh tranh nhỏ nhen lấy từ Petty Pantheon: Đổ tội, Cướp công. Xung đột giữa bạn bè tạo kịch tính và clip; cái chết chung của thế giới buộc mọi người phải hợp tác.
2. **Ván ngắn 15–20 phút, chơi lại ngay.** Thị trường 2026 thưởng cho game co-op ngắn, dễ stream (mục 1). Sandbox vô hạn vẫn có, nhưng là chế độ phụ.
3. **Phạm vi theo kỷ luật của GODFORGE.** Bản đồ nhỏ, 60–150 dân, 8 quyền năng, 3 combo, 1 tài nguyên. Kéo mạng lên tuần 1–3 như Petty Pantheon.

| Hạng mục | MVP (tuần 12) |
| --- | --- |
| Engine | Unity 6 LTS, C#, URP 2D |
| Nền tảng | PC Windows trên Steam; tiếng Anh + tiếng Việt |
| Người chơi | 1–4 (chơi đơn với thần bot) |
| Chế độ | **Một Kiếp** (ván 15–20 phút, chính) · Sandbox (phụ) |
| Bản đồ | 96×96 ô, 3 biome, 4–6 làng |
| Dân | Mục tiêu 100; bắt đầu 60, chỉ tăng sau khi profile |
| Thần | 4 thần (khác màu + 1 nội tại), chung bộ quyền năng |
| Quyền năng | 8 phép + 3 combo |
| Tài nguyên | 1: **Hương khói** |
| Hệ thống AI | Utility AI, Ký ức làng + tin đồn, Thích nghi theo mối đe doạ, Sấm Truyền (6 thẻ), Biên niên sử, thần bot |
| Chi phí AI | 0 USD, không gọi cloud, không LLM trong MVP |
| Mục tiêu 12 tuần | Bản demo 4 người online chơi trọn một ván, trang Steam Coming Soon, dữ liệu playtest cho khoá luận |

## 1. Thị trường 2026 và hướng đi

### 1.1 Số liệu chính

Valve không công bố doanh số, nên mọi con số dưới đây là ước tính của bên thứ ba và chỉ để định hướng.

| Quan sát | Số liệu | Ý nghĩa cho dự án |
| --- | --- | --- |
| WorldBox vẫn là ông lớn của thể loại | Ước tính 1,2–2,1 triệu bản, 14–32 triệu USD gộp; 2026 trung bình ~1.500–1.900 người chơi cùng lúc; giá 19,99 USD | Thể loại có cầu thật và bền. Chưa tìm thấy thông tin WorldBox có multiplayer → **"god game chơi cùng bạn" là khoảng trống**. |
| God game mới ra đều yếu | Fata Deum (EA 9/2025): Mixed, 59% của 415 đánh giá. Godcraft Simulator, Island God Simulator (2026): gần như không có đánh giá | Cạnh tranh trực tiếp thấp, nhưng làm "WorldBox thứ hai" thì không đủ. Cần một góc nhìn khác hẳn. |
| Game hay nhưng khó hiểu bán ít | Reus 2: 95% tích cực nhưng chỉ ~41 nghìn bản. Người chơi chê tutorial yếu, UI khó hiểu, giống puzzle hơn god game | **Dễ hiểu quan trọng ngang chất lượng.** Đây là lý do có trụ cột "Đọc được trong 10 giây". |
| Co-op đang thắng lớn | Game gắn tag co-op năm 2025 có doanh thu ~4 lần trung vị indie; co-op chỉ chiếm ~6,5% số game ra mắt | Co-op là đòn bẩy doanh thu lớn nhất trong tầm tay một nhóm nhỏ. |
| "Friendslop" (co-op ngắn, hỗn loạn, rẻ) | Nhiều tựa nằm trong top bán chạy 2025 (R.E.P.O., PEAK…). Đẩy bởi streamer và nhóm bạn trên Discord. Hit thường giảm còn ~10% người chơi sau 3–9 tháng | Học cách lan truyền (ván ngắn, khoảnh khắc đáng react, mời bạn). Tránh điểm yếu chóng chán bằng **chiều sâu sandbox và ký ức** để mỗi ván khác nhau. |
| Sandbox/Simulation có tỉ lệ thành công cao | Doanh thu trung vị của sandbox ~2,2 lần mức chung; tỉ lệ "hit" ~27% | Giữ bản chất mô phỏng là lựa chọn đúng. |
| Wishlist thực tế khá thấp | Trung vị Next Fest 2/2026: khoảng 200–800 wishlist mỗi game; demo→wishlist ~19%; wishlist→mua tuần đầu ~12–13% | Hạ KPI cho thực tế (mục 15). Đặt trang Steam càng sớm càng tốt. |
| Steam tại Việt Nam | Bị chặn kỹ thuật ở nhiều nhà mạng từ 5/2024; người dùng vẫn vào được bằng cách đổi DNS/VPN; chưa rõ tình trạng thanh toán | **Không dựa vào doanh thu Việt Nam.** Đặt tiếng Anh làm mặc định, thị trường quốc tế là chính; cộng đồng Việt dùng để làm devlog và playtest. |

### 1.2 Hướng đi được chọn

> **"God game dành cho nhóm bạn": dễ hiểu như một party game, sâu như một sandbox.**

- **Khách hàng chính:** nhóm 2–4 bạn trên Discord, 16–30 tuổi, quốc tế, thích game co-op hỗn loạn; fan WorldBox muốn chơi cùng bạn.
- **Khách hàng phụ:** streamer và khán giả (Stream Mode ở giai đoạn sau), người chơi đơn thích mô phỏng.
- **Không nhắm:** người chơi strategy hardcore (4X), thị trường mobile ở giai đoạn này.
- **Bản sắc:** chất dân gian Á Đông (đình làng, cây đa, ruộng bậc thang, lễ hội) kèm giọng hài phổ quát. Bản sắc này lạ với thị trường quốc tế và tách game khỏi WorldBox.
- **Không đặt chữ "AI" vào tên và quảng cáo.** Người chơi Steam 2026 nhạy cảm với "AI". Hãy bán trải nghiệm: "dân biết nhớ, biết thù, biết học". Nếu văn bản trong game do AI hỗ trợ viết, phải khai báo trong mục AI disclosure của Steam.

## 2. Năm trụ cột thiết kế

Mọi tính năng phải phục vụ ít nhất một trụ cột. Không phục vụ trụ nào thì cắt.

1. **Đọc được trong 10 giây.** Người xem một clip 10 giây phải hiểu được ai đã làm gì và dân phản ứng ra sao. Mỗi thần một màu; mọi thứ thần làm đều phát sáng màu đó.
2. **Thần nhỏ nhen.** Thần ganh đua bằng giọng hài, mọi quyền năng đều có hệ quả xã hội.
3. **Dân biết nhớ và biết học.** Làng nhớ ai cứu, ai hại mình; tin đồn lan sang làng khác; ai bị sét đánh nhiều thì dựng cột thu lôi.
4. **Cùng nhau mới sống.** Khủng hoảng chung và combo cần hai thần, nên không ai thắng nếu thế giới chết.
5. **Mỗi ván là một câu chuyện.** Biên niên sử và tờ báo cuối ván tự viết lại những gì đã xảy ra, sẵn để chia sẻ.

**Không làm:** 3D, MMO/dedicated server, gacha hay pay-to-win, sao chép art, UI, tên gọi hay chủng tộc của WorldBox, tuyên bố "AI tự học" khi thực chất là luật.

## 3. Vòng chơi và thiết kế gây nghiện

### 3.1 Một Kiếp (chế độ chính, 15–20 phút)

| Giai đoạn | Thời gian | Chuyện gì xảy ra |
| --- | --- | --- |
| Khai Thiên | 0–3 phút | Sinh thế giới từ seed, mỗi thần chọn một làng khởi đầu, mở **1 thẻ Thiên Mệnh** (luật ngẫu nhiên của ván, ví dụ "Sét rẻ một nửa", "Dân rất hay quên") |
| Tranh Đạo | 3–7 phút | Đáp lời cầu, ban phước, gieo hoạ; cướp tín đồ của nhau |
| Khủng Hoảng 1 | ~7 phút | Hạn hán **hoặc** Cháy rừng toàn bản đồ. Phải phối hợp combo để cứu |
| Tranh Đạo 2 | 9–13 phút | Dân đã có ký ức, có làng đã đổi đạo, có làng bắt đầu thích nghi |
| Khủng Hoảng 2 | ~13 phút | Khủng hoảng còn lại, mạnh hơn |
| Phán Xét | 15–18 phút | Đếm tín đồ, chiếu Biên niên sử + Báo Thần Giới, trao danh hiệu |

**Luật thắng thua:**

- **Thắng:** thần có nhiều tín đồ nhất khi hết giờ.
- **Thắng sớm (Thăng Thiên):** giữ ≥ 60% dân số thế giới trong 90 giây.
- **Tận Thế:** dân số thế giới dưới 25% so với lúc đông nhất → **tất cả thua**, và tờ báo cuối ván chế giễu cả nhóm. Đây là cái phanh chống phá game và là nguồn clip hài.
- **Thần Bị Lãng Quên:** thần mất hết tín đồ không bị loại. Thần đó còn 2 quyền năng phá đám miễn phí và hồi sinh được nếu có làng cầu nguyện tới mình. Người thua vẫn ở lại và vẫn có việc vui để làm.

### 3.2 Vòng lặp theo tầng thời gian

| Tầng | Người chơi làm gì | Phần thưởng tức thì |
| --- | --- | --- |
| 10 giây | Thấy bong bóng lời cầu → bấm quyền năng → làng đổi màu, dân reo hoặc chạy tán loạn | Hương khói +, hiệu ứng "đã mắt" |
| 1–2 phút | Cướp một làng của bạn, Đổ tội thành công, combo cứu làng | Tín đồ, tiếng cười trong voice chat |
| 1 ván | Thắng / Tận Thế / bị lật kèo phút chót | Biên niên sử, danh hiệu, thẻ báo để khoe |
| Nhiều ván | Lên cấp thần, mở thần thứ 4, sưu tầm danh hiệu, thử Thiên Mệnh mới | Lý do chơi thêm một ván nữa |

### 3.3 Các móc giữ chân (có đạo đức)

| Móc | Cách làm | Vì sao hiệu quả |
| --- | --- | --- |
| Ván ngắn + nút "Kiếp mới" | Màn kết thúc có nút chơi lại ngay, giữ nguyên phòng | Rào cản bằng không cho thêm một ván |
| Kết quả không đoán trước | Mô phỏng, tin đồn, Thiên Mệnh, lời cầu ngẫu nhiên | Phần thưởng biến thiên, không ván nào giống ván nào |
| Thua sát nút | Màn kết thúc ghi rõ "Bạn chỉ thua 3 tín đồ" | Muốn gỡ ngay |
| Kình địch với bạn bè | Thống kê đối đầu giữa từng cặp bạn (ai Đổ tội ai bao nhiêu lần) | Chuyện để nói tiếp trên Discord |
| Sưu tầm | ~40 danh hiệu ("Kẻ Đổ Tội Chuyên Nghiệp", "Thần Hiền Nhất Mà Vẫn Thua"), 20 thẻ Thiên Mệnh, 4 thần | Mục tiêu dài hạn rõ ràng |
| Tiến trình nhìn thấy được | Cấp thần mở skin, khung avatar, thần thứ 4 | Cảm giác đi lên |
| Daily Kiếp (P1) | Một seed mỗi ngày, bảng xếp hạng Steam | Lý do quay lại mỗi ngày, không cần server |

**Giới hạn đạo đức (không vượt qua):** không lootbox, không năng lượng giới hạn lượt chơi, không phạt người chơi vì nghỉ một ngày, không bán sức mạnh. Muốn "gây nghiện" thì làm bằng niềm vui và câu chuyện, không bằng thao túng.

## 4. Dễ hiểu: cách dạy người chơi

- **Một con số duy nhất:** Hương khói. Không có hai thanh hay nhiều tài nguyên thần.
- **Màu = thần.** Viền làng, phép, bong bóng thoại đều mang màu thần liên quan.
- **Làng nói bằng biểu tượng:** trên mỗi làng có màu thần đang thờ và mặt cảm xúc 😊 / 😨 / 😠. Rê chuột vào làng để xem 3 ký ức gần nhất (ví dụ "Thần Đỏ đốt ruộng – 2 năm trước").
- **Lời cầu là tutorial.** Ba lời cầu đầu tiên của ván đầu có mũi tên chỉ đúng quyền năng cần dùng. Người chơi học bằng cách làm, không phải đọc chữ.
- **Giải thích mọi thay đổi.** Khi làng đổi đạo hay xây cột thu lôi, một dòng chữ hiện lên kèm lý do ("Làng Cây Đa bỏ Thần Xanh vì bị sét đánh 3 lần").
- **Thử nghiệm 3 phút:** người chưa từng chơi phải dùng được quyền năng đầu tiên trong 30 giây và tự giải thích được luật thắng sau 3 phút. Đo bằng playtest (mục 16).

## 5. Hệ thống cốt lõi

### 5.1 Hương khói và quy kết

- Mỗi tín đồ dâng Hương khói đều đặn. Làng có Đền dâng nhiều hơn.
- **Thiện được lâu, ác được nhanh.** Phép lạ mà dân *nhìn thấy* tăng lòng tin, nên tín đồ ở lại lâu. Thảm hoạ mà dân thấy màu bạn cho một khoản Hương khói lớn ngay (dâng vì sợ), nhưng làng ghi **thù**. Thù đủ nhiều thì làng đổi sang thần khác hoặc dựng phòng thủ chống bạn.
- **Quy kết theo màu:** dân chỉ biết ai gây ra một việc khi thấy màu của thần đó. Đây là nền tảng cho Đổ tội và Cướp công.

### 5.2 Lời cầu nguyện

- Làng sinh nhu cầu (đói, hạn, cháy, bệnh, ghen tị) và hiện bong bóng biểu tượng trên bản đồ.
- Đáp ứng đúng hạn thì nhận gấp đôi lòng tin; thần đến trước nhận công.
- **Lời cầu nhỏ nhen** (ví dụ "Xin cho ruộng làng bên mất mùa"): làm theo thì được lòng làng cầu nhưng bị làng kia thù. Đây là lựa chọn đạo đức nhỏ, dễ thành meme.
- Lời cầu cũng là kênh tutorial và là đòn bẩy tạo kịch tính: khi ván nhàm, Đạo diễn kịch tính đẩy lời cầu gây tranh chấp.

### 5.3 Quyền năng (8 phép + 3 combo)

| Nhóm | Quyền năng | Tác dụng chính | Hệ quả |
| --- | --- | --- | --- |
| Phước | Mưa | Tưới ruộng, dập lửa, làm đất ướt | Đất ướt là nền cho combo |
| Phước | Bội Thu | Ruộng trong vùng cho gấp đôi lương thực | Tốn nhiều Hương khói |
| Phước | Mọc Rừng | Trồng/tái sinh rừng | Rừng dễ cháy |
| Hoạ | Sét | Sát thương điểm, có thể gây cháy | Làng sinh thù nếu thấy màu bạn |
| Hoạ | Lửa | Đốt vùng thực vật, lan theo gió | Khó kiểm soát |
| Hoạ | Thiên Thạch | "Chiêu cuối", hồi chiêu dài, tạo hố + cháy | Rất dễ thành clip |
| Nhỏ nhen | Đổ tội | Phép kế tiếp của bạn mang màu một thần khác | Có xác suất bị lộ nếu gần Đền của nạn nhân |
| Nhỏ nhen | Cướp công | Trong 10 giây, phép lạ của thần khác được tính cho bạn | Nếu bị lộ, cả hai làng biết |

**Combo (cần 2 phép trong cửa sổ 5 giây; nếu 2 thần khác nhau cùng làm thì cả hai được công và hiệu ứng mạnh hơn):**

| Combo | Điều kiện | Hiệu ứng |
| --- | --- | --- |
| Hồ Quang (Storm Arc) | Mưa → Sét | Sét lan theo ô đất ướt, quét quái và đám cháy trong vùng |
| Tro Tái Sinh (Ember Rebirth) | Mọc Rừng → Lửa | Đốt có kiểm soát, tạo đất tro màu mỡ, chặn đường cháy rừng |
| Mưa Vàng | Mưa → Bội Thu | Cả vùng được mùa; cứu hạn hán nhanh nhất |

**Bốn thần** dùng chung bộ phép trên, chỉ khác màu và một nội tại (dữ liệu, không thêm code lớn): Thần Sấm (Sét rẻ hơn), Thần Lúa (Bội Thu lan rộng hơn), Thần Lửa (Lửa ít bị quy kết hơn), Thần Rừng (Mọc Rừng hồi nhanh). Chiêu riêng cho từng thần để dành P1.

### 5.4 Sấm Truyền (6 thẻ chính sách)

Sấm Truyền là cách thần ra chính sách dài hạn cho làng mình đang giữ. Bản MVP dùng **6 thẻ bấm** thay vì gõ chữ tự do: dễ hiểu hơn, không có lỗi hiểu sai câu.

| Thẻ | Dân làm gì |
| --- | --- |
| Giữ Rừng | Giảm chặt cây, trồng thêm |
| Mở Đất | Ưu tiên lập làng mới, xây nhà |
| Tích Trữ | Gom lương thực/gỗ, giữ ngưỡng dự trữ |
| Phòng Thủ | Xây chòi canh, tuần tra, trú ẩn |
| Thờ Phụng | Xây/sửa Đền, tăng Hương khói |
| Truyền Đạo | Gửi người sang làng khác giảng đạo (cướp tín đồ) |

- Mỗi làng chỉ theo một thẻ tại một thời điểm, đổi thẻ có hồi chiêu.
- Thẻ chỉ cộng điểm vào Utility AI, không ghi đè sinh tồn: dân đói vẫn đi kiếm ăn.
- **P1:** ô gõ lệnh tự nhiên tiếng Việt/Anh, dùng bộ phân tích từ khoá (của GODFORGE) để chọn thẻ phù hợp nhất, luôn hiện diễn giải để người chơi xác nhận trước khi áp dụng.

### 5.5 Văn minh thích nghi (Sổ Mối Đe Doạ)

Mỗi làng cộng điểm theo loại tai hoạ đã chịu, điểm cũ phai dần. Vượt ngưỡng thì làng "nghiên cứu" một phản ứng, sau một thời gian và đủ tài nguyên thì mở khoá.

| Mối đe doạ | Phản ứng mở khoá |
| --- | --- |
| Sét | Cột thu lôi: hút sét trong bán kính, giảm sát thương |
| Lửa / cháy rừng | Dải chống cháy, dời nhà khỏi rừng |
| Hạn hán (P1) | Kho lương, đào giếng, dời làng gần nước |

Thông báo luôn ghi rõ lý do. Hệ thống này vừa chống spam một chiêu vừa tạo khoảnh khắc "dân học cách chống lại mình" rất đáng clip. Đây là thích nghi theo luật, không phải Q-Learning, và tài liệu sẽ không tuyên bố khác.

### 5.6 Ký ức làng và tin đồn

Ký ức lưu theo **làng** (của GODFORGE) thay vì từng người dân (của v1), để rẻ CPU và dễ hiển thị.

- Mỗi làng giữ tối đa 16 ký ức: loại sự kiện, thần liên quan, mức độ, thời điểm, độ quan trọng. Ký ức yếu phai theo thời gian.
- Từ ký ức, làng tính **cảm tình** với từng thần, sinh ra lòng tin, nỗi sợ, thù hoặc mang ơn.
- **Tin đồn:** khi thương nhân hoặc người truyền đạo đi qua làng khác, ký ức mạnh nhất được chép sang làng đó (nhẹ hơn bản gốc). Nhờ vậy một tia sét có thể khiến cả vùng ghét bạn.
- **Danh xưng làng gán cho thần:** "Đấng Che Chở", "Kẻ Huỷ Diệt", "Thần Giữ Rừng". Danh xưng xuất hiện trong báo và Biên niên sử.

### 5.7 Khủng hoảng

- **Hạn hán:** ruộng giảm sản lượng, lời cầu mưa tăng vọt. Giải nhanh nhất bằng Mưa Vàng.
- **Cháy rừng:** lửa lan theo gió từ rìa bản đồ. Giải bằng Mưa, Hồ Quang và Tro Tái Sinh làm đường chặn lửa.
- Mỗi Kiếp có cả hai khủng hoảng theo thứ tự ngẫu nhiên. Khủng hoảng thứ ba (dịch bệnh hoặc quái vật) để dành P1.

### 5.8 Biên niên sử và Báo Thần Giới

- Đạo diễn kịch tính chấm điểm mỗi sự kiện (số người chết, bất ngờ, đảo chiều, người chơi liên quan) và chọn 5–8 khoảnh khắc hay nhất.
- Văn bản sinh bằng ngữ pháp kiểu Tracery kết hợp kho mẫu Việt/Anh, ví dụ: *"Làng Bánh Đa bị sét đánh 14 lần, dân làng quyết định chuyển sang thờ con bò."*
- Cuối ván có **thẻ Báo Thần Giới** (PNG 1:1 và 9:16) với tiêu đề, danh hiệu từng người và mã thế giới. Đây là P0 vì rẻ và là kênh lan truyền chính.

## 6. Thế giới và mô phỏng

| Thành phần | MVP |
| --- | --- |
| Lưới | 96×96 ô (cấu hình được) |
| Biome | Đồng bằng, Rừng, Đất tro |
| Địa hình | Cỏ, Nước, Rừng, Núi, Tro, Ruộng |
| Tài nguyên | Lương thực, Gỗ, Đá |
| Công trình | Nhà, Ruộng, Đền, Chòi canh, Cột thu lôi |
| Tộc dân | 2 tộc chỉ khác trọng số Utility AI: dân đồng bằng (đông, sinh nhanh) và dân rừng (ít, bền, ghét chặt cây) |
| Thời gian | Tick mô phỏng 10 lần/giây, hiển thị nội suy 60 FPS. Sandbox chơi đơn có Pause/x1/x2/x5; online thì host quyết định tốc độ |

**Utility AI của dân:** `Điểm = Ưu tiên gốc + Nhu cầu + Tính cách tộc + Thẻ Sấm Truyền + Cảm tình − Rủi ro`. Mỗi thành phần đều có trần và sàn; sinh tồn luôn có trọng số tối thiểu. Cập nhật luân phiên theo nhóm, tìm kiếm lân cận bằng spatial grid, cache đường đi.

## 7. Hệ thống AI 0 đồng

| Tầng | Kỹ thuật | MVP? |
| --- | --- | --- |
| Não dân | Utility AI + state machine đơn giản | P0 |
| Ký ức & tin đồn | Sổ ký ức theo làng, phai dần, sao chép khi giao lưu | P0 |
| Thích nghi | Sổ Mối Đe Doạ + ngưỡng + mở khoá theo luật | P0 |
| Sấm Truyền | 6 thẻ chính sách → cộng điểm Utility | P0 (gõ chữ tự nhiên: P1) |
| Đạo diễn kịch tính & văn bản | Chấm điểm sự kiện + ngữ pháp Tracery + kho mẫu JSON | P0 |
| Thần bot | Utility AI cấp cao, 4 tính cách: Hiền, Bạo, Nhỏ nhen, Lười | P0 |
| ML/LLM local | Sentis/ONNX hoặc LLM nhỏ qua llama.cpp để viết lại tiêu đề báo | P2, chỉ khi có benchmark |

**Cam kết:** gameplay không gọi API cloud, không cần API key; mọi AI cốt lõi chạy được offline. Multiplayer vẫn cần mạng qua Steam.

**Ngân sách hiệu năng:** AI ≤ 4 ms/khung với 150 dân trên PC tầm trung; bản đồ dùng một Texture2D, chỉ cập nhật ô thay đổi; dân vẽ bằng GPU instancing. Mọi con số chỉ công bố sau khi đo.

## 8. Multiplayer

- **Host-authoritative listen server qua Steam.** Host chạy mô phỏng; client chỉ gửi *Command* ("dùng Sét tại ô x,y"). Chơi đơn cũng đi qua đúng đường này (host offline), nên chỉ có một bộ code.
- **Command Bus làm từ tuần 1**, cho cả người chơi, bot, và sau này là chat Twitch. Mỗi lệnh có ID, người gửi, tick và kết quả, ghi log để phát lại lỗi.
- **Đồng bộ tự viết:** địa hình gửi seed + ô đã đổi; dân gửi vị trí/trạng thái lượng tử hoá ~6 byte, 10 Hz, chỉ trong vùng camera; sự kiện gửi qua kênh reliable. Không dùng NetworkObject cho từng dân.
- **Transport:** chốt sau spike tuần 1–2, chọn giữa (a) Facepunch.Steamworks với Steam Networking Sockets tự viết lớp tin nhắn, hoặc (b) Mirror + FizzySteamworks. Ưu tiên (a) nếu spike chạy được, vì việc đồng bộ đằng nào cũng tự viết. Test bằng AppID 480 cho tới khi có AppID riêng.
- **Lobby & mời bạn:** Steam Lobby + overlay. Khi chơi với bot có nút "Thần bot đang giữ chỗ – mời bạn vào thay".
- **Ngoài MVP:** host migration, matchmaking công khai, dedicated server, chống gian lận nâng cao.
- **Cần kiểm tra:** cho bản Demo miễn phí vào chung phòng với bản đầy đủ (kiểu "Friend Pass"). Nếu Steam cho phép thì đây là đòn bẩy viral mạnh nhất.

## 9. Viral và cộng đồng

| Kênh | Cách làm | Mức |
| --- | --- | --- |
| Thẻ Báo Thần Giới + Biên niên sử | PNG 1:1/9:16, nút copy/lưu | P0 |
| Đánh dấu khoảnh khắc | Đạo diễn kịch tính gắn marker vào Steam Game Recording qua Timeline API (cần kiểm tra phiên bản SDK); người chơi tự cắt clip bằng công cụ của Steam, mình không phải viết bộ ghi video | P1 |
| Mã thế giới | Chuỗi ngắn mã hoá seed + Thiên Mệnh, ví dụ `PP-7K3-LUA` | P0 |
| Daily Kiếp | Seed theo ngày + Steam Leaderboard | P1 |
| Đặt tên dân theo bạn bè | Nhập danh sách tên → gán cho dân | P1 |
| Stream Mode | Đọc chat Twitch: `!join`, `!pray`, `!vote` thảm hoạ | P2 |
| Clip MP4 tự cắt (FFmpeg) | Bộ đệm vòng 30 giây, xuất video dọc | P2 |
| Workshop | Chia sẻ thế giới và bộ Thiên Mệnh | P2 |

**Tiếp thị song song khi code:** từ tuần 2, đăng 2–3 clip devlog mỗi tuần (TikTok, YouTube Shorts, Reddit r/godgames, r/IndieGaming); mở trang Steam Coming Soon ở tuần 8; gửi key cho streamer co-op và god-sim; nhắm Steam Next Fest đầu tiên sau khi có demo ổn định.

## 10. Art, âm thanh, UI

- **Pixel art top-down**, silhouette rõ khi zoom xa, palette cố định 32–64 màu để asset từ nhiều nguồn trông đồng bộ.
- **Chất dân gian Á Đông:** đình, cây đa, ruộng bậc thang, lồng đèn, giọng hài phổ quát.
- **Juice:** rung màn hình, khựng hình khi sét đánh, dân chạy tán loạn, bong bóng thoại. Clip chỉ lan khi từng cú đánh trông đã mắt.
- **Âm thanh:** SFX CC0 (Kenney, Freesound CC0); giọng dân líu lo tự sinh bằng đổi cao độ âm tiết; 3–4 bài nhạc ngũ cung có license.
- **UI** (UI Toolkit): trên là Hương khói, tín đồ và đồng hồ Kiếp; trái là thanh 8 quyền năng; phải là danh sách lời cầu; dưới là dải tin Báo Thần Giới. Bấm vào làng mở bảng ký ức, thẻ Sấm Truyền và tình trạng thích nghi.

## 11. Kiến trúc kỹ thuật và quy tắc vibecode

**Nguyên tắc vàng:** Sim Core bằng C# thuần, không tham chiếu UnityEngine. Mọi đầu vào đi qua Command Bus; mọi đầu ra đi qua Event Bus.

```
Người chơi / Bot / (Twitch) ──► Command Bus ──► Sim Core (C# thuần, tick 10 Hz)
                                                   │
                                                   ▼
                                               Event Bus ──► Hiển thị · Âm thanh · Đạo diễn kịch tính · Mạng · Telemetry
```

| Module | Trách nhiệm |
| --- | --- |
| WorldSystem | Sinh bản đồ, biome, ô, tài nguyên |
| CitizenSystem | Nhu cầu, Utility AI, di chuyển |
| VillageSystem | Làng, công trình, kinh tế tối giản, thẻ Sấm Truyền |
| FaithSystem | Hương khói, quy kết, đổi đạo |
| MemorySystem | Ký ức làng, tin đồn, danh xưng |
| AdaptationSystem | Sổ Mối Đe Doạ, mở khoá phản ứng |
| PowerSystem | 8 phép, hồi chiêu, combo |
| CrisisSystem | Hạn hán, cháy rừng, Thiên Mệnh |
| DirectorSystem | Chấm kịch tính, Biên niên sử, báo |
| BotGodSystem | Thần bot |
| NetworkSystem | Lobby, gửi lệnh, đồng bộ, xác thực |
| SaveSystem | JSON có version cho thế giới và cấu hình |

Dữ liệu cân bằng (giá phép, ngưỡng, mẫu văn bản, Thiên Mệnh) để trong JSON/ScriptableObject, chỉnh không cần sửa code.

**Quy tắc vibecode:**

1. Git từ ngày 1; một tính năng một commit; thử nghiệm lớn làm trên nhánh riêng.
2. File `CLAUDE.md` ghi kiến trúc trên và các luật cấm: Sim Core không dùng UnityEngine; mọi input qua Command Bus; không NetworkObject cho từng dân; không thêm dependency cloud; không sửa ngoài phạm vi task.
3. Mỗi prompt một tính năng nhỏ. AI phải nêu file sẽ sửa và cách test trước khi code → chạy test → chơi thử 5 phút → commit.
4. Sim Core có unit test và test headless 10.000 tick để bắt crash, tài nguyên âm, dân kẹt, công trình trên ô cấm.
5. Test 2 cửa sổ multiplayer mỗi ngày từ tuần 2.
6. Mở Profiler mỗi tuần. Ngân sách: 60 FPS, RAM < 1,5 GB.
7. Mỗi tuần dành 2–3 giờ đọc lại và giải thích code AI đã viết (chuẩn bị cho buổi bảo vệ).

## 12. Phạm vi theo mức ưu tiên

| Mức | Tính năng |
| --- | --- |
| **P0 – Bắt buộc** | Command Bus + host-authoritative 2–4 người; bản đồ 96×96; dân Utility AI; làng và 5 công trình; Hương khói + quy kết; lời cầu; 8 phép + 3 combo; Sấm Truyền 6 thẻ; Thích nghi (Sét, Lửa); Ký ức làng + tin đồn; 2 khủng hoảng; luật Một Kiếp (thắng, Tận Thế, Lãng Quên); thần bot; Biên niên sử + thẻ báo PNG; mã thế giới; onboarding bằng lời cầu; tiếng Anh + tiếng Việt |
| **P1 – Nếu kịp** | Sandbox đầy đủ + Save/Load; Daily Kiếp + Leaderboard; Steam Timeline markers; gõ Sấm Truyền bằng chữ; thích nghi Hạn hán; khủng hoảng thứ 3; chiêu riêng cho từng thần; Achievements; đặt tên dân theo bạn bè; 20 thẻ Thiên Mệnh (MVP: 8 thẻ) |
| **P2 – Sau 12 tuần** | Stream Mode Twitch; clip MP4; Workshop; LLM/ML local; Remote Play Together; bản Android; tộc, quái và công trình mới |

**Luật đóng băng:** sau tuần 6, mỗi tính năng thêm vào P0 phải kèm một tính năng P0 bị đẩy xuống.

**Thứ tự cắt khi trễ:** Daily Kiếp → Timeline markers → combo thứ 3 → Thần Bị Lãng Quên → thần thứ 3 và 4 (giữ 2 thần) → Sandbox. **Không bao giờ cắt:** multiplayer, quy kết theo màu, ký ức + thích nghi, khủng hoảng chung, thẻ báo cuối ván.

## 13. Lộ trình 12 tuần (16/11/2026 – 07/02/2027)

Tuần 12 trùng Tết Đinh Mùi (06/02/2027), nên build cuối chốt ngày **01/02/2027**; tuần cuối chỉ dành cho báo cáo.

| Tuần | Bắt đầu | Công việc | Kết quả kiểm tra được |
| --- | --- | --- | --- |
| 1 | 16/11 | Project Unity, Sim Core rỗng, Command/Event Bus, render lưới, test headless; đăng ký Steamworks + trả phí Steam Direct; spike transport | Repo build được; 10.000 tick không crash |
| 2 | 23/11 | Sinh bản đồ 96×96, camera; 2 máy gửi Command qua Steam (AppID 480); chốt transport | Hai máy thả Sét lên cùng một thế giới |
| 3 | 30/11 | Dân: nhu cầu, Utility AI, kiếm ăn, làng, nhà/ruộng; đồng bộ dân | **Cổng 1 (06/12):** 2 người online cùng thấy làng tự sống |
| 4 | 07/12 | Hương khói, quy kết theo màu, đổi đạo, lời cầu | Bấm phép → làng đổi màu, đổi cảm xúc |
| 5 | 14/12 | 8 phép (VFX thô), hồi chiêu, Đổ tội/Cướp công | Ván thử 2 người có tranh tín đồ |
| 6 | 21/12 | Ký ức làng, tin đồn, danh xưng; thần bot cơ bản | **Cổng 2 (27/12):** ván 1 người vs 1 bot vui được 10 phút |
| 7 | 28/12 | Sấm Truyền 6 thẻ; Thích nghi (Sét, Lửa) | Làng dựng cột thu lôi sau khi bị spam sét |
| 8 | 04/01 | 2 khủng hoảng, 3 combo, luật Một Kiếp, Thiên Mệnh; **gửi trang Steam Coming Soon** | Ván 4 người trọn vẹn, có Tận Thế |
| 9 | 11/01 | Biên niên sử + thẻ báo PNG, danh hiệu, mã thế giới; 4 tính cách bot | **Cổng 3 (17/01):** ván 4 người 18 phút không lỗi chặn |
| 10 | 18/01 | Juice, âm thanh, UI, onboarding bằng lời cầu, telemetry ẩn danh có hỏi đồng ý | Người mới dùng được phép đầu tiên trong 30 giây |
| 11 | 25/01 | Playtest 15–30 người (dữ liệu khoá luận), sửa lỗi, đo hiệu năng | Báo cáo playtest + build ứng viên |
| 12 | 01/02 | **Chốt build 01/02**; viết báo cáo, slide, video demo | Bảo vệ khoá luận |

**Đường găng:**

- Cuối tuần 2 mà hai máy chưa trao đổi được Command thì dừng mọi tính năng và chỉ xử lý mạng.
- Cuối tuần 6 mà ván chơi đơn chưa vui thì cắt Sấm Truyền và Thích nghi xuống mức tối thiểu, dồn sức cho quy kết, lời cầu và phép.
- Trễ một cổng quá 3 ngày thì cắt theo thứ tự ở mục 12, không dời cổng tiếp theo.

## 14. QA – Definition of Done

- [ ] 4 người qua Steam Lobby chơi trọn một Kiếp 18 phút, không có lỗi chặn hay lệch trạng thái nghiêm trọng (test 3 lần).
- [ ] Chơi đơn với 3 bot hoàn thành một ván.
- [ ] Dân tự kiếm ăn, xây dựng, phản ứng với nguy hiểm; test 10.000 tick không có tài nguyên âm hay dân kẹt vô hạn.
- [ ] Đủ 8 phép và 3 combo, mỗi cái có VFX + âm thanh riêng.
- [ ] Làng đổi đạo vì ký ức và ghi rõ lý do; tin đồn lan được tới làng thứ hai.
- [ ] Ít nhất 2 phản ứng thích nghi mở được trong một ván bình thường.
- [ ] Thẻ báo cuối ván xuất được PNG, văn bản đúng ngữ pháp ở cả hai ngôn ngữ.
- [ ] Người mới hiểu luật thắng sau 3 phút (≥ 70% người playtest).
- [ ] Build Windows chạy độc lập, có cài đặt cơ bản và hướng dẫn điều khiển.

**Test mạng:** client spam lệnh, mất gói, vào/ra giữa trận, host tạm dừng. **Test hiệu năng:** 60/100/150 dân × 1/2/4 client, nhiều đám cháy cùng lúc.

## 15. Kinh doanh và phát hành

- **Mô hình:** premium, không pay-to-win. Giá giả thuyết **7,99–9,99 USD** (co-op friendslop thường ở mức này; WorldBox 19,99 USD có nhiều nội dung hơn hẳn). Bật giá vùng của Steam. Chỉ chốt giá sau playtest.
- **Lộ trình phát hành:** trả phí Steam Direct (100 USD) và hoàn tất thuế ngay tuần 1, vì có thời gian chờ 21 ngày cho sản phẩm đầu tiên và xác minh thuế có thể mất tới 30 ngày. Trang Coming Soon ở tuần 8 (trang phải công khai ≥ 2 tuần trước khi phát hành). Sau tuần 12 làm demo/Steam Playtest → Next Fest → Early Access khi có nội dung cho khoảng 10 giờ chơi. **Không bán trả phí ở tuần 12.**
- **Doanh thu sau ra mắt:** Supporter Pack 3–5 USD (nhạc nền, skin, tên trong credits); DLC mỹ phẩm (skin thần, bộ Thiên Mệnh); bản Android cân nhắc sau 6 tháng.
- **Chi phí:** Steam Direct 100 USD; asset pixel 0–150 USD; nhạc 0–200 USD; server và API AI 0 USD.
- **Ví dụ minh hoạ (không phải dự báo):** 3.000 wishlist × ~13% chuyển đổi tuần đầu ≈ 400 bản tuần đầu. Game cần nhiều wishlist trước ra mắt hơn, nên Next Fest và streamer là bắt buộc.

**KPI (đã hạ cho sát thực tế):**

| Giai đoạn | Chỉ số | Mục tiêu |
| --- | --- | --- |
| Tuần 12 | Wishlist | ≥ 300 (vượt mức: 1.000) |
| Playtest | Thời gian chơi trung vị | ≥ 30 phút (≈ 2 ván) |
| Playtest | Tỉ lệ bấm "Kiếp mới" sau ván đầu | ≥ 60% (chỉ số gây nghiện chính) |
| Playtest | Hiểu luật sau 3 phút | ≥ 70% |
| Next Fest | Demo → wishlist | ≥ 20% (trung vị ~19%) |
| Mọi giai đoạn | Tỉ lệ ván có lưu thẻ báo | ≥ 15% |
| Mọi giai đoạn | Tỉ lệ ván có ≥ 2 người thật | ≥ 40% |
| Ra mắt EA | Đánh giá tích cực | ≥ 80% |

## 16. Góc khoá luận

**Đề tài gợi ý:** *"Kiến trúc AI lai chi phí bằng không cho mô phỏng xã hội đa tác tử và kể chuyện nổi sinh trong game thần nhiều người chơi."*

**Đóng góp có thể bảo vệ:**

1. Mô hình ký ức – cảm tình – tin đồn ở cấp làng, cho phép làng đổi đạo và lan truyền danh tiếng trong một ngân sách CPU cố định.
2. Thích nghi theo luật (Sổ Mối Đe Doạ) như một giải pháp thay thế có thể giải thích được cho học tăng cường trong game.
3. Kiến trúc host-authoritative + Command Bus cho mô phỏng nhiều tác tử, có số đo băng thông.
4. Đánh giá tính **dễ đọc** của mô phỏng: người chơi có tự giải thích được vì sao dân làm vậy không.

**Phương pháp đánh giá:**

| Câu hỏi | Cách đo | Cỡ mẫu |
| --- | --- | --- |
| Mô phỏng đủ nhanh? | ms/tick, FPS theo 60/100/150/300 dân | 3 cấu hình máy |
| Mạng đủ nhẹ? | KB/s mỗi client theo 2/3/4 người | 10 phiên |
| Người chơi hiểu mô phỏng? | Sau ván, hỏi "Vì sao làng X bỏ thần Y?" và so với log | 15–30 người |
| Ký ức + thích nghi có tăng hứng thú? | So sánh A/B: bật và tắt hệ thống, đo GEQ + tỉ lệ chơi lại | 15–30 người |
| Game có gây muốn chơi tiếp? | Tỉ lệ "Kiếp mới", thời gian chơi, phỏng vấn ngắn | Toàn bộ người playtest |

**Cấu trúc báo cáo:** (1) Giới thiệu, (2) Cơ sở lý thuyết: god game, utility AI, emergent narrative, netcode, (3) Thiết kế, (4) Hiện thực, (5) Đánh giá, (6) Kết luận.

**Lưu ý:** hỏi giảng viên và quy định của trường về việc dùng AI sinh code ngay từ đầu, và ghi rõ trong báo cáo.

## 17. Rủi ro và giảm thiểu

| Rủi ro | Mức | Giảm thiểu |
| --- | --- | --- |
| Phạm vi quá lớn | Rất cao | Bảng P0/P1/P2, luật đóng băng, thứ tự cắt sẵn |
| Mạng tích hợp muộn hoặc lỗi | Rất cao | Command Bus tuần 1, cổng mạng tuần 2–3, test 2 cửa sổ mỗi ngày, log lệnh để phát lại |
| Bán-hợp-tác gây ức chế (bạn phá, không ai hợp tác) | Cao | Luật Tận Thế, combo chia công, Lãng Quên vẫn vui; chỉnh qua playtest từ tuần 6 |
| Game khó hiểu như Reus 2 | Cao | Trụ cột "10 giây", onboarding bằng lời cầu, KPI hiểu luật ≥ 70% |
| Mô phỏng chậm | Trung bình | Bắt đầu 60 dân, time-slicing, Profiler mỗi tuần |
| Bị xem là bản nhái WorldBox | Trung bình | Bán-hợp-tác nhiều người, art dân gian Á Đông, không dùng tên/tộc/UI tương tự |
| Steam bị chặn tại Việt Nam | Trung bình | Mặc định tiếng Anh, thị trường quốc tế; người chơi Việt chủ yếu để playtest và devlog |
| Thủ tục Steamworks chậm | Trung bình | Đăng ký và trả phí tuần 1 |
| Giấy phép asset/nhạc/thư viện | Thấp | `LICENSES.md` ghi nguồn từng thứ ngay khi thêm |
| Kiệt sức | Trung bình | Tuần cuối mỗi tháng giảm tải; cắt phạm vi thay vì cắt giấc ngủ |

## 18. Đã lấy gì từ hai bản

| Hạng mục | Lấy từ | Thay đổi trong v3 |
| --- | --- | --- |
| Giọng hài, thần nhỏ nhen, Đổ tội/Cướp công | Petty Pantheon | Giữ 2 phép nhỏ nhen thay vì 4 |
| Combo phép, khủng hoảng chung | GODFORGE | Combo cho cả hai thần được công; khủng hoảng đặt vào giữa mỗi Kiếp |
| Tài nguyên | Cả hai | Gộp Lòng tin/Nỗi sợ và Divine Energy thành **một** Hương khói; tính chất "sợ" chuyển thành thù trong ký ức |
| Ký ức | Cả hai | Ký ức theo làng (GODFORGE) + tin đồn (Petty Pantheon) |
| Thích nghi | GODFORGE | Giữ nguyên ý tưởng, gắn với quy kết theo màu thần |
| Sấm Truyền | GODFORGE | MVP dùng 6 thẻ bấm; gõ chữ tự nhiên chuyển xuống P1 |
| Lời cầu nguyện | Petty Pantheon | Đồng thời làm tutorial |
| Chế độ chơi | Cả hai | Thêm Một Kiếp 15–20 phút làm chế độ chính (mới) |
| Quy mô | GODFORGE | 96×96 ô, 60–150 dân thay vì 256×256 và 1.500 |
| Mạng | Petty Pantheon | Command Bus + cổng mạng ở tuần 1–3 |
| QA, Steam, tuyên bố phạm vi | GODFORGE | Giữ; hạ KPI theo số liệu thị trường |
| Khoá luận | Petty Pantheon | Thêm đánh giá tính dễ đọc và A/B ký ức |
| Mới hoàn toàn | — | Thiên Mệnh, Tận Thế, móc giữ chân, chiến lược thị trường quốc tế |

## 19. Câu hỏi mở

1. Nhóm bao nhiêu người? Có ai vẽ pixel art được không?
2. Bạn đã dùng Unity/C# bao lâu, đã làm multiplayer chưa?
3. Ngày bảo vệ chính xác là khi nào? Trường có cho phép dùng AI sinh code không?
4. Tên chính thức: giữ *Petty Pantheon* (dễ nhớ, nói được ngay ý tưởng nhỏ nhen) hay dùng *GODFORGE*? Đề xuất giữ Petty Pantheon và tra trùng nhãn hiệu trước khi lập trang Steam.
5. Ngân sách tối đa cho asset và nhạc?
6. Bạn đã có kênh TikTok/YouTube hay cộng đồng Discord nào để đăng devlog chưa?

## Nguồn tham khảo thị trường

- WorldBox: [Raijin](https://raijin.gg/app/1206560/WorldBox__God_Simulator), [Gamalytic](https://gamalytic.com/game/1206560), [Steam Charts](https://steamcharts.com/app/1206560)
- God game mới: [Fata Deum trên Steam](https://store.steampowered.com/app/1330360/Fata_Deum__The_God_Sim/), [Godcraft Simulator](https://store.steampowered.com/app/4326090/Godcraft_Simulator/), [Island God Simulator](https://store.steampowered.com/app/4603270)
- Reus 2: [Raijin](https://raijin.gg/app/1875060/Reus_2), [Vaporlens tổng hợp đánh giá](https://vaporlens.app/app/1875060/reus_2)
- Co-op và indie 2026: [Superjump – State of Indie 2026](https://www.superjumpmagazine.com/state-of-indie-2026-part-1/), [Steam Q1 2026 report](https://gameindustrylibrary.com/documents/2026-q1-games)
- Friendslop: [How To Market A Game – Is Friendslop Saturated?](https://howtomarketagame.com/2026/07/30/is-friendslop-saturated), [Game World Observer](https://gameworldobserver.com/2026/08/03/analyst-there-are-many-games-in-the-friendslap-niche-but-it-is-not-oversaturated), [AppMagic](https://appmagic.rocks/blog/friendslop-steam-games-2025)
- Sandbox/Simulation: [Automaton – thể loại bán chạy trên Steam](https://automaton-media.com/en/news/study-of-best-selling-genres-on-steam-shows-sandbox-games-continue-to-stand-out-in-revenue/), [How To Market A Game – What happened in 2025](https://howtomarketagame.com/2026/01/27/what-the-hell-happened-in-2025/)
- Wishlist và Next Fest: [Cinevva – Next Fest 2/2026](https://app.cinevva.com/news/2026-03-05-steam-next-fest-february-2026), [How To Market A Game – Benchmarks](https://howtomarketagame.com/benchmarks/), [Steam Page Analyzer – conversion](https://www.steampageanalyzer.com/blog/steam-wishlist-conversion-rates)
- Steam tại Việt Nam: [Inven Global](https://www.invenglobal.com/articles/26798/steam-effectively-blocked-in-vietnam-issues-extend-to-downloads-and-updates), [24hStore](https://24hstore.vn/cong-nghe/su-that-ve-lenh-cam-steam-o-viet-nam-n8534)
- Thị trường game Việt Nam: [Vietnam News](https://vietnamnews.vn/economy/1782291/gaming-industry-grows-rapidly-needs-strong-ecosystem-for-global-competitiveness), [Digital in Asia](https://digitalinasia.com/2026/03/07/vietnams-gaming-market-in-5-data-points/)

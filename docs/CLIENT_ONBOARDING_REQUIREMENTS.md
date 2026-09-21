# DANH MỤC DỮ LIỆU & TÀI LIỆU CẦN THU THẬP TỪ KHÁCH HÀNG (GIAI ĐOẠN 1)
**Dự án:** CRM F&B Equipment & Supplies (Máy móc, Thiết bị & Nguyên phụ liệu quán F&B)

Tài liệu này được lập để gửi trực tiếp cho Khách hàng/Ban Giám đốc doanh nghiệp F&B nhằm chuẩn bị các mẫu dữ liệu thực tế, giúp đội ngũ kỹ thuật thiết kế chuẩn Database, cơ chế chống trùng, engine đối chiếu kho Excel và các tool AI MCP.

---

## 1. BỘ CÁC FILE EXCEL / GOOGLE SHEETS MẪU

Khách hàng chỉ cần trích xuất khoảng **5 - 10 dòng dữ liệu mẫu** thực tế từ các file đang theo dõi hiện tại và tải lên một thư mục Google Drive:

### File 1: Danh sách Khách hàng & Lead đang quản lý
Dùng để thiết kế bảng cơ sở dữ liệu khách hàng, cấu hình thuật toán phát hiện trùng quán/trùng số điện thoại:
- **Thông tin liên hệ:** Họ tên người đại diện/chủ quán, Số điện thoại (chính & phụ), Link Facebook/Zalo, Email.
- **Thông tin nhận diện quán F&B:**
  - Tên quán / Tên thương hiệu (Brand name).
  - Mô hình quán: Quán truyền thống, Specialty Coffee, Trà sữa/Take-away, Nhà hàng, Chuỗi nhượng quyền (Franchise), Khách sạn (HORECA).
  - Tình trạng: Quán sắp mở mới (cần setup trọn gói từ máy móc đến nguyên liệu) hay Quán đang hoạt động (cần đổi máy/mua thêm/mua nguyên liệu).
  - Địa chỉ quán (Tỉnh/Thành, Quận/Huyện, Địa chỉ chi tiết để điều phối giao lắp máy & kỹ thuật).
  - Công suất phục vụ dự kiến (ước tính số ly/ngày - ví dụ: 150-200 ly/ngày để tư vấn máy 1 group hay 2 group).
- **Thông tin phân công & trạng thái:**
  - Nguồn khách (Facebook Ads, Bạn bè giới thiệu, Triển lãm F&B, Website, Vãng lai...).
  - Nhân viên kinh doanh đang phụ trách (Sale Owner).
  - Trạng thái chăm sóc (Mới tiếp cận, Khảo sát quán, Đã gửi báo giá, Đang thử hạt/demo máy, Đã chốt, Tạm dừng...).

### File 2: Danh mục Sản phẩm & Tồn kho Thiết bị - Nguyên liệu
Dùng để xây dựng **Engine đối chiếu chênh lệch kho Excel (Excel Diff Engine)** và nạp tri thức cho **AI MCP**:
- **Nhóm Máy móc & Thiết bị:**
  - Mã SKU / Model máy (Ví dụ: `EXP-MINI-01`, `FAEMA-E98-02`).
  - Tên sản phẩm (Ví dụ: *Máy pha cà phê Faema E98 Auto 2 Group*).
  - Phân loại: Máy pha cà phê, Máy xay cà phê, Máy dập nắp, Máy ép chậm, Máy đun nước nóng, Máy làm đá...
  - Thương hiệu & Xuất xứ (Ý, Tây Ban Nha, Đài Loan, Trung Quốc...).
  - Số lượng tồn kho vật lý hiện tại.
  - Quản lý số Serial/IMEI (Có quản lý theo từng máy riêng biệt hay quản lý theo số lượng chung?).
  - Thời hạn bảo hành tiêu chuẩn (tháng) và chu kỳ bảo dưỡng khuyến nghị.
  - Giá nhập/giá vốn (phân quyền bảo mật chỉ Giám đốc/Kế toán thấy) và Giá niêm yết bán lẻ/đại lý.
- **Nhóm Nguyên phụ liệu tiêu hao (Cà phê hạt, bột trà, siro):**
  - Tên nguyên liệu (Ví dụ: *Cà phê hạt Gu Đậm 70/30, Bột Trà xanh Matcha Uji...*).
  - Quy cách đóng gói & Đơn vị tính (Gói 1kg, Thùng 10kg, Chai 700ml...).
  - Mức tiêu hao ước tính của 1 quán thông thường (ví dụ: 1 quán trung bình dùng 15-30kg hạt/tháng).
  - Hạn sử dụng (Shelf life).

### File 3: Mẫu Báo giá Combo / Đơn hàng thực tế hiện tại
Dùng để thiết kế luồng tạo báo giá thông minh (CPQ) và xuất file PDF/In ấn:
- Mẫu báo giá thực tế mà nhân viên Sales đang gửi cho các chủ quán:
  - Cấu trúc Combo mở quán (Gồm máy pha + máy xay + phụ kiện bar: tamper nén, thảm tamper, knockbox gõ bã, ca đánh sữa...).
  - Các chính sách quà tặng đi kèm: Tặng bao nhiêu kg cà phê ban đầu, tặng khóa đào tạo Barista, hỗ trợ trả góp/đặt cọc.
  - Quy định thanh toán: Tỷ lệ đặt cọc, thanh toán khi giao máy, thanh toán sau nghiệm thu.

---

## 2. QUY CHẾ VẬN HÀNH & PHÂN QUYỀN BẢO MẬT (DẠNG VĂN BẢN/NOTE)

### 1. Phân quyền Nhân sự & Bảo mật dữ liệu
Khách hàng làm rõ các vai trò và phạm vi xem dữ liệu:
- **Ban Giám đốc:** Toàn quyền xem báo cáo tổng thể, doanh số, lợi nhuận, chi phí giá vốn, quản trị hệ thống.
- **Trưởng phòng Kinh doanh:** Xem toàn bộ khách hàng và deal của cả phòng ban; phân bổ khách hàng cho nhân viên; duyệt báo giá có chiết khấu cao vượt thẩm quyền.
- **Nhân viên Kinh doanh (Sales):** Chỉ xem khách hàng được phân công cho mình. Có cần ẩn (Masking) số điện thoại của khách (ví dụ: `098****321`) để phòng ngừa việc nhân viên đem tệp khách hàng sang công ty đối thủ không?
- **Kế toán & Thủ kho:** Thao tác nhập/xuất kho, cập nhật giá bán, tải file Excel đối chiếu kho, kiểm duyệt công nợ và thanh toán.
- **Kỹ thuật & Bảo hành:** Xem danh sách máy đã bán, số serial, lịch giao lắp và bảo trì định kỳ, ghi chú tình trạng máy.

### 2. Quy chế KPI & Cơ chế Cảnh báo Sớm Ngày 29
Khách hàng cung cấp công thức hoặc chỉ tiêu cụ thể:
- **Các tiêu chí đánh giá KPI tháng:**
  - Doanh số chốt máy & thiết bị (VNĐ).
  - Doanh số bán nguyên liệu lặp lại (VNĐ).
  - Số lượng khách hàng mới mang về trong tháng.
- **Quy tắc cảnh báo sớm:**
  - Ngày 25: Cảnh báo nước rút 5 ngày cho các deal tiềm năng đang đàm phán.
  - Ngày 29: Cảnh báo những nhân viên chưa đạt KPI tối thiểu, hoặc nhân viên sắp chạm mốc bậc thưởng tiếp theo (còn thiếu bao nhiêu tiền) để kích thích tinh thần chốt số phút chót.

### 3. Quy tắc Chăm sóc Tự động & Marketing (Automation Rules)
- Chu kỳ tiêu hao: Sau khi quán mua cà phê hạt, hệ thống mặc định sau **bao nhiêu ngày** sẽ tự động bắn nhắc việc cho Sales gọi lại tiếp tế nguyên liệu? (Ví dụ: 15 ngày hay 20 ngày).
- Chu kỳ bảo dưỡng máy: Sau **bao nhiêu tháng** kể từ ngày giao máy thì kích hoạt lịch bảo dưỡng định kỳ thay gioăng, tẩy cặn? (Ví dụ: 3 tháng hay 6 tháng).

---

## 3. DỮ LIỆU & YÊU CẦU BỘ PHẬN MARKETING CẦN CUNG CẤP

Để hệ thống CRM đo lường được hiệu quả của từng đồng ngân sách quảng cáo và tự động hóa khâu giữ chân khách hàng mua cà phê hạt, Bộ phận Marketing của MADG cần chuẩn bị:

### 1. Danh sách các Kênh Tiếp Cận Khách Hàng (Lead Sources)
Cung cấp danh sách các kênh mà MADG đang tìm kiếm khách hàng mở quán F&B:
- **Facebook Ads:** Đang chạy các chiến dịch nào? (Ví dụ: Chiến dịch "Setup quán cà phê trọn gói", Chiến dịch "Combo máy pha Faema giá sốc").
- **Kênh Zalo OA / Zalo ZNS / Nhóm Khách Quen:** Dùng để thông báo ưu đãi và chăm sóc khách cũ.
- **Sự kiện Triển lãm ngành F&B:** Triển lãm Vietfood & Beverage, triển lãm Cafe Show hàng năm (thu thập danh thiếp, quét mã QR).
- **Website & Hotline:** Form đăng ký tư vấn trên website MADG, số hotline tổng đài.
- **Khách hàng cũ giới thiệu & Đối tác nhượng quyền.**

### 2. Các Chương Trình Khuyến Mại & Ưu Đãi Mở Quán
- Chính sách tặng hạt cà phê ban đầu khi mua máy (ví dụ: mua máy pha tặng 5kg hạt Robusta + ca đánh sữa).
- Chính sách chiết khấu khi chủ quán mở chi nhánh thứ 2, thứ 3.
- Chính sách hỗ trợ trả góp hoặc đặt cọc giữ máy.

### 3. Kịch Bản Tự Động Hóa Chăm Sóc & Giữ Chân (Marketing Automation)
- **Kịch bản nhắc tiếp tế hạt cà phê (Chu kỳ 15 - 20 ngày):** Quán cà phê thường dùng hết 1 đợt hạt trong 2-3 tuần. Hệ thống CRM sẽ tự động phát cảnh báo nhắc nhân viên Sales gọi lại hoặc tự động gửi tin nhắn Zalo ZNS/SMS gửi mã ưu đãi tiếp tế hạt.
- **Kịch bản bảo dưỡng máy định kỳ (Chu kỳ 90 ngày):** Máy pha cà phê sau 3 tháng cần thay gioăng cao su, vệ sinh họng pha và tẩy cặn canxi boiler. Hệ thống tự động tạo lịch hẹn kỹ thuật đến quán hỗ trợ.

---

## 4. THÔNG TIN HẠ TẦNG KẾT NỐI & CẢNH BÁO

1. **Kênh nhận cảnh báo nội bộ:** Doanh nghiệp ưu tiên nhận thông báo (cảnh báo trùng khách, cảnh báo KPI ngày 29, thông báo đơn mới) qua đâu:
   - Nhóm Telegram riêng của công ty MADG? (Miễn phí, bảo mật cao, khuyên dùng).
   - Zalo OA / Nhóm Zalo?
   - Hay hiển thị trực tiếp trên Notification của CRM Web?
2. **Kỳ vọng giao tiếp AI MCP:**
   - Nhân sự ra lệnh thêm khách hàng bằng giọng nói hoặc tin nhắn ngắn: Sẽ gõ qua giao diện web CRM hay tích hợp qua Bot Telegram/Zalo ngoài thị trường?

---

## BẢNG TỔNG HỢP CHECKLIST CẦN GỬI (5 HẠNG MỤC)

| STT | Hạng mục cần cung cấp | Định dạng | Tác dụng trong Giai đoạn 1 |
| :---: | :--- | :--- | :--- |
| **1** | File danh sách khách hàng & lead mẫu (5-10 dòng) | Excel / Google Sheet | Thiết kế Database khách hàng, cài thuật toán chống trùng quán & giấu số điện thoại. |
| **2** | File danh mục sản phẩm & tồn kho máy/nguyên liệu | Excel / Google Sheet | Cài đặt tính năng Đối chiếu Kho (Excel Diff) và nạp dữ liệu cho AI MCP tra cứu giá. |
| **3** | Mẫu Báo giá Combo mở quán thực tế (1 bản) | Excel / PDF | Thiết kế tính năng tạo báo giá nhanh và xuất file PDF trong 30 giây. |
| **4** | Quy chế KPI & Cơ chế Cảnh báo Sớm Ngày 29 | Ghi chú văn bản | Cài đặt cảnh báo nước rút trước kỳ phát lương ngày 10 (chốt ngày 30). |
| **5** | **Dữ liệu Kênh Marketing & Kịch bản Tự động hóa** | **Ghi chú văn bản** | **Đo lường ROI từng kênh quảng cáo, kịch bản Zalo tiếp tế hạt (15 ngày) & bảo dưỡng máy (90 ngày).** |

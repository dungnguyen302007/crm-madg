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

## 2. VAI TRÒ TRÁCH NHIỆM, DANH SÁCH TẠO TÀI KHOẢN & MA TRẬN CHE/MỞ DỮ LIỆU

### 1. Vai Trò & Trách Nhiệm Từng Bộ Phận Trên CRM
- **Ban Giám Đốc (Admin):** Toàn quyền kiểm soát hệ thống; xem doanh thu toàn công ty, chi phí giá vốn thiết bị, lợi nhuận gộp; duyệt các chính sách chiết khấu lớn; kiểm tra Audit Log (nhật ký truy cập và thao tác dữ liệu).
- **Trưởng Phòng Kinh Doanh (Sales Manager):** Phân bổ Lead cho nhân viên Sales; theo dõi bảng giám sát cảnh báo KPI ngày 29; duyệt báo giá theo hạn mức; xử lý khiếu nại tranh chấp trùng quán giữa các Sales.
- **Nhân Viên Kinh Doanh (Sales Executive):** Tiếp nhận và chăm sóc quán được phân công; tạo báo giá combo mở quán; cập nhật lịch sử cuộc gọi/demo; nhận cảnh báo nhắc khách tái mua hạt cà phê sau 15 ngày.
- **Bộ Phận Marketing:** Đổ Lead từ Facebook Ads, Zalo, Cafe Show vào CRM; đo lường chi phí/doanh số từng kênh (ROI); trích xuất Lead chưa chốt để chạy kịch bản nuôi dưỡng tự động.
- **Kế Toán & Thủ Kho:** Tải file Excel đối chiếu kho để cập nhật số lượng tồn và giá bán; xuất kho máy khi có đơn hàng; theo dõi tiến độ thanh toán và công nợ.
- **Kỹ Thuật & Bảo Hành:** Xem lịch giao lắp đặt máy pha; quản lý số Serial từng máy; thực hiện lịch bảo dưỡng định kỳ 90 ngày (thay gioăng cao su, tẩy cặn boiler).

### 2. Ma Trận Phân Loại Dữ Liệu & Nguyên Tắc Che / Mở (Data Masking)
Nhằm chống thất thoát dữ liệu khách hàng và bảo mật bí mật kinh doanh khi nhân viên nghỉ việc:

| Loại Dữ Liệu Nhạy Cảm | Ban Giám Đốc | Trưởng Phòng Sales | Nhân Viên Sales | Kế Toán / Kho | Kỹ Thuật |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Số điện thoại khách hàng** | Mở 100% | Mở (Cả phòng ban) | **Mở khách mình / Che `090****456` khách khác** | Mở khi có lệnh giao | Mở khi có lịch bảo trì |
| **Giá vốn / Giá nhập máy** | Mở 100% | **KHÓA** | **KHÓA TUYỆT ĐỐI** | Mở 100% | **KHÓA** |
| **Bảng lương & Hoa hồng** | Toàn công ty | Chỉ xem phòng ban | Chỉ xem của bản thân | Xem để làm lương | **KHÓA** |
| **Xuất file Excel ra ngoài** | Toàn quyền | Cần Giám đốc duyệt | **KHÓA (Chống tuồn data)** | Xuất báo cáo kho | **KHÓA** |
| **Xóa dữ liệu khách hàng** | Chỉ Lưu Trữ (Archive) | **KHÓA** | **KHÓA** | **KHÓA** | **KHÓA** |

### 3. Bảng Mẫu Danh Sách Nhân Sự MADG Cần Cấp Tài Khoản
MADG cung cấp danh sách nhân viên tham gia vận hành CRM theo các cột sau:

| Họ và Tên | Email Đăng Nhập | Số Điện Thoại | Phòng Ban | Vai Trò Gán Quyền | Khu Vực Phụ Trách |
| :--- | :--- | :--- | :--- | :--- | :--- |
| *Nguyễn Văn A (Mẫu)* | *giamdoc@madg.vn* | *0909 111 222* | *Ban Giám Đốc* | *Ban Giám Đốc (Admin)* | *Toàn quốc* |
| *Bùi Anh Tuấn (Mẫu)* | *tuan.ba@madg.vn* | *0912 345 678* | *Phòng Kinh Doanh* | *Nhân Viên Sales* | *Hà Nội & Miền Bắc* |
| *Nguyễn Thu Mai (Mẫu)* | *mai.kt@madg.vn* | *0988 555 666* | *Kế Toán - Kho* | *Kế Toán & Thủ Kho* | *Kho Tổng TP.HCM* |

### 4. Quy Chế Cảnh Báo KPI Nước Rút Ngày 29
- Mức chỉ tiêu KPI tháng thông thường của 1 nhân viên Sales (Doanh số máy & Doanh số hạt).
- Hệ thống tự động quét vào **ngày 25 và 29 hàng tháng** để cảnh báo nhân viên nguy cơ rớt KPI và gợi ý danh sách deal chốt nước rút.

---

## 3. VAI TRÒ MARKETING TRÊN CRM: DỰA VÀO ĐÂU & LẤY GÌ RA ĐỂ HÀNH ĐỘNG?

Nhân sự Marketing của MADG làm việc trên CRM hoàn toàn xoay quanh việc **khai thác tệp Lead (Khách hàng tiềm năng)** để không lãng phí ngân sách quảng cáo và nuôi dưỡng quán mua hạt cà phê định kỳ:

### A. Nhân sự Marketing DỰA VÀO ĐÂU trên CRM?
Marketing căn cứ vào **4 trường dữ liệu cốt lõi của Lead** đã được lưu trong hệ thống:
1. **Dựa vào "Nguồn Lead" (Lead Source):** Khách đến từ Facebook Ads (chiến dịch nào), Triển lãm Cafe Show, Zalo OA hay Khách quen?
2. **Dựa vào "Trạng Thái Lead" (Lead Stage):** Khách mới nhận / Đang tìm mặt bằng / Chê giá đắt / Đang phân vân combo máy / Đã mua máy?
3. **Dựa vào "Mô Hình Quán & Nhu Cầu Thiết Bị":** Quán sắp mở mới (cần setup trọn gói) hay Quán đang chạy (chỉ cần lấy hạt cà phê/đổi máy)?
4. **Dựa vào "Ngày Mua Gần Nhất":** Quán đã lấy cà phê hạt cách đây bao nhiêu ngày (15 hay 20 ngày)? Máy pha đã lắp đặt được bao nhiêu tháng (đã đến mốc 90 ngày chưa)?

### B. Nhân sự Marketing LẤY DỮ LIỆU GÌ RA để làm việc?
Từ các trường trên, Marketing lọc và **xuất 4 danh sách cụ thể** để hành động:
1. **Lấy ra Danh sách "Lead chưa chốt máy" (Lead đang ngủ quên):** Lọc các quán chưa chốt vì chưa có mặt bằng hoặc phân vân giá $\rightarrow$ Marketing gửi kịch bản Zalo cẩm nang mở quán, video review máy, voucher giảm 2 triệu để kích thích Sales chốt lại.
2. **Lấy ra Danh sách "Quán sắp hết hạt cà phê" (Mốc 15 - 20 ngày):** Lọc các quán đã mua hạt quá 15 ngày $\rightarrow$ Tự động gửi tin nhắn Zalo kèm mã ưu đãi freeship hoặc tặng 1kg khi mua thùng 10kg để giữ chân quán, không để mất khách về tay đối thủ.
3. **Lấy ra Danh sách "Máy pha đã chạy đủ 90 ngày":** Lọc các máy đến hạn 3 tháng $\rightarrow$ Bắn tin nhắn thông báo cử kỹ thuật qua thay gioăng cao su, kiểm tra áp suất boiler miễn phí nhằm tạo sự chuyên nghiệp vượt trội.
4. **Lấy ra Báo cáo "Hiệu Quả Tiền Quảng Cáo (ROI)":** Xuất bảng đối chiếu: Bỏ 15 triệu chạy Facebook mang về bao nhiêu quán, chốt được bao nhiêu máy pha $\rightarrow$ Báo cáo Sếp duyệt ngân sách tháng tiếp theo.

---

## 4. THÔNG TIN HẠ TẦNG KẾT NỐI & CẢNH BÁO

1. **Kênh nhận cảnh báo nội bộ:** Doanh nghiệp ưu tiên nhận thông báo (cảnh báo trùng khách, cảnh báo KPI ngày 29, thông báo đơn mới) qua đâu:
   - Nhóm Telegram riêng của công ty MADG? (Miễn phí, bảo mật cao, khuyên dùng).
   - Zalo OA / Nhóm Zalo?
   - Hay hiển thị trực tiếp trên Notification của CRM Web?
2. **Kỳ vọng giao tiếp AI MCP:**
   - Nhân sự ra lệnh thêm khách hàng bằng giọng nói hoặc tin nhắn ngắn: Sẽ gõ qua giao diện web CRM hay tích hợp qua Bot Telegram/Zalo ngoài thị trường?

---

## BẢNG TỔNG HỢP CHECKLIST CẦN GỬI (ĐẦY ĐỦ 6 HẠNG MỤC)

| STT | Hạng mục cần cung cấp | Định dạng | Tác dụng trong Giai đoạn 1 |
| :---: | :--- | :--- | :--- |
| **1** | File danh sách khách hàng & lead mẫu (5-10 dòng) | Excel / Google Sheet | Thiết kế Database khách hàng, cài thuật toán chống trùng quán & giấu số điện thoại. |
| **2** | File danh mục sản phẩm & tồn kho máy/nguyên liệu | Excel / Google Sheet | Cài đặt tính năng Đối chiếu Kho (Excel Diff) và nạp dữ liệu cho AI MCP tra cứu giá. |
| **3** | Mẫu Báo giá Combo mở quán thực tế (1 bản) | Excel / PDF | Thiết kế tính năng tạo báo giá nhanh và xuất file PDF trong 30 giây. |
| **4** | Quy chế Phân quyền bảo mật & Cảnh báo KPI 29 | Ghi chú văn bản | Cài đặt ma trận che/mở SĐT chống lộ data và quét KPI nước rút ngày 29. |
| **5** | Dữ liệu Kênh Marketing & Kịch bản Tự động hóa | Ghi chú văn bản | Đo lường ROI từng kênh quảng cáo, kịch bản Zalo tiếp tế hạt (15 ngày) & bảo dưỡng máy (90 ngày). |
| **6** | **Danh Sách Nhân Sự MADG Cần Tạo Tài Khoản** | **Excel / Ghi chú** | **Cấp tài khoản đăng nhập CRM, gán đúng vai trò và chi nhánh cho từng nhân sự ban đầu.** |

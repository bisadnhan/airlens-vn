# 🌿 AirLens VN - Urban Air Quality & Weather Monitor

**Hệ thống Giám sát Chất lượng Không khí & Thời tiết Đô thị Thời gian thực**  
Ứng dụng Web tĩnh (Single Page Application) sử dụng dữ liệu mở từ **Open-Meteo API & Copernicus Atmosphere Monitoring Service (CAMS)**.

---

## 🌟 Điểm nổi bật & Cập nhật mới (Features)

1. **Giao diện sáng (Clean Weather Light Theme) hiện đại, dễ quan sát:**
   - Thiết kế tinh gọn, trang nhã tương tự các ứng dụng thời tiết chuyên nghiệp (Apple Weather / AccuWeather).
   - Tông màu xanh da trời (Sky Blue), trắng sạch và xanh ngọc (Emerald).
   - Thẻ AQI và các chỉ số vi khí hậu được phân màu sắc nét, dễ đọc trên cả máy tính và điện thoại.

2. **Tích hợp 25+ tỉnh thành khắp 3 miền Việt Nam:**
   - **Miền Trung & Tây Nguyên:** Đà Nẵng, Thừa Thiên Huế, Nha Trang, Đà Lạt, Quy Nhơn, Phan Thiết, Pleiku, Buôn Ma Thuột, TP. Vinh, Đồng Hới.
   - **Miền Bắc:** Hà Nội (Thủ đô), Hải Phòng, Hạ Long (Quảng Ninh), Sa Pa (Lào Cai), Ninh Bình, Bắc Ninh, Thái Nguyên, Hải Dương, Lạng Sơn.
   - **Miền Nam:** TP. Hồ Chí Minh, Cần Thơ, Vũng Tàu, Phú Quốc (Kiên Giang), Bình Dương, Đồng Nai, Long An, Mỹ Tho, Cà Mau.
   - Hỗ trợ **chạm hoặc click vào bất kỳ tọa độ nào trên bản đồ** để đo vi khí hậu tại điểm đó.

3. **Mục thời gian rõ ràng (Live Clock & Timestamps):**
   - **Đồng hồ số thời gian thực (Live Clock):** Chạy liên tục từng giây theo múi giờ Việt Nam (GMT+7) hiển thị Thứ, Ngày Tháng Năm và Giờ Phút Giây.
   - **Mốc thời gian cập nhật của trạm:** Hiển thị chính xác thời điểm dữ liệu được Open-Meteo đo lường và làm mới.

4. **Bản đồ tương tác Leaflet.js tối ưu:**
   - Sử dụng lớp bản đồ sáng **OpenStreetMap** và **Carto Voyager** siêu mượt, tải nhanh và không bao giờ bị lỗi hiển thị.
   - Cắm sẵn trạm quan sát khắp cả nước kèm hiệu ứng ghim vị trí đang chọn.

5. **Chỉ số AQI & Vi khí hậu toàn diện:**
   - Chỉ số **AQI (US EPA Standard)** kèm thanh thước đo mức độ nguy hại.
   - **Bụi mịn $PM_{2.5}$** ($\mu g/m^3$) & **Bụi thô $PM_{10}$** đối chiếu khuyến nghị của Tổ chức Y tế Thế giới (WHO).
   - **Nhiệt độ bề mặt (°C)** và **Độ ẩm tương đối (%)**.
   - **Đồ thị diễn biến $PM_{2.5}$ 24 giờ trong ngày** dạng đường Area Gradient (Chart.js).

6. **Khuyến nghị hành động đô thị thông minh:**
   - Tự động thay đổi nội dung 3 thẻ sức khỏe theo thời gian thực: Đi lại & Đeo khẩu trang, Thể thao ngoài trời, và Bảo vệ không gian sống trong nhà.

---

## 🌐 Chạy Local hay Người khác cũng xem được?

* **Khi bạn mở trực tiếp file `index.html` trên máy tính:** Chỉ máy tính của bạn xem được (chạy môi trường Local).
* **Làm sao để người khác trên toàn thế giới cùng xem được?**
  Khi bạn đưa lên **GitHub Pages** (hoàn toàn miễn phí), GitHub sẽ xuất bản thành một trang web chính thức trên Internet dạng:
  👉 **`https://bisadnhan.github.io/airlens-vn/`**
  Khi đó, bất kỳ ai dùng điện thoại hay máy tính đều có thể truy cập đường link trên và xem được dữ liệu thời gian thực mà bạn không cần phải mở máy tính!

---

## 🚀 Các bước đưa lên GitHub Pages

Mở PowerShell tại thư mục `d:\Airlens` và chạy lệnh sau để đẩy code lên GitHub:

```powershell
git push -u origin main --force
```

Sau đó:
1. Vào repository trên GitHub: `https://github.com/bisadnhan/airlens-vn`
2. Chọn tab **Settings** -> mục **Pages** (ở cột bên trái).
3. Tại phần **Build and deployment** -> **Branch**:
   - Chọn nhánh: `main`
   - Chọn thư mục: `/ (root)`
   - Nhấn **Save**.
4. Chờ khoảng 1–2 phút, bạn sẽ nhận được đường link website:
   `https://bisadnhan.github.io/airlens-vn/`

---
© 2026 **AirLens VN** - Nguồn dữ liệu mở Open-Meteo & Copernicus CAMS.

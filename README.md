# 🌿 AirLens VN - Urban Air Quality Monitor

**Hệ thống Giám sát Chất lượng Không khí & Vi khí hậu Đô thị Thời gian thực**  
Ứng dụng Web tĩnh (Single Page Application) sử dụng dữ liệu mở từ **Open-Meteo API & Copernicus Atmosphere Monitoring Service (CAMS)**.

---

## 🌟 Điểm nổi bật (Features)

1. **Kiến trúc siêu tinh gọn (Zero Backend / Single File):**
   - Toàn bộ giao diện, bản đồ, biểu đồ và logic xử lý API gói gọn trong đúng **1 file duy nhất** `index.html`.
   - Chạy 100% Client-side trên trình duyệt, không cần Node.js, không cần build step, không phụ thuộc máy chủ backend.
   - Sẵn sàng đưa lên **GitHub Pages**, **Vercel**, **Netlify** hoặc bất kỳ dịch vụ web tĩnh nào chỉ trong vài giây.

2. **Bản đồ tương tác không gian (Leaflet.js):**
   - Ghim sẵn các trạm tại 5 đô thị trọng điểm: **Hà Nội, TP. Hồ Chí Minh, Đà Nẵng, Hải Phòng, Cần Thơ**.
   - Cho phép **chạm / click vào bất kỳ điểm nào trên bản đồ Việt Nam hoặc thế giới** để tự động ghim tọa độ và tải dữ liệu vi khí hậu thời gian thực.
   - Hỗ trợ đổi chế độ bản đồ **Dark Matter** (Chế độ Tối công nghệ) và **Voyager** (Bản đồ Sáng chi tiết).

3. **Chỉ số AQI & Vi khí hậu thời gian thực:**
   - **Thẻ AQI động lớn:** Tự động đổi màu và cấp độ cảnh báo (Xanh lá $\le 50$, Vàng $51-100$, Cam $101-150$, Đỏ $>150$).
   - **4 thông số đo môi trường:**
     - $PM_{2.5}$ ($\mu g/m^3$) kèm đối chiếu tiêu chuẩn khuyến nghị của WHO.
     - $PM_{10}$ ($\mu g/m^3$).
     - Nhiệt độ bề mặt (°C).
     - Độ ẩm tương đối (%).
   - **Biểu đồ xu hướng 24h (Chart.js):** Đường biến thiên nồng độ $PM_{2.5}$ từ 0h đến 23h trong ngày hôm nay với hiệu ứng mượt mà.

4. **Khuyến nghị hành động đô thị (Smart Health Insights):**
   - 3 nhóm thẻ thông minh tự động thay đổi lời khuyên theo ngưỡng AQI thực tế:
     - 🚲 **Đi lại & Di chuyển:** Khuyến nghị phương tiện, khẩu trang lọc bụi mịn N95 khi cần.
     - 🏃 **Thể thao Ngoài trời:** Lời khuyên chạy bộ, vận động hoặc chuyển vào trong nhà.
     - 🏠 **Không gian Sống & Nhà cửa:** Hướng dẫn mở cửa đón khí tươi hay đóng kín bật máy lọc không khí.

5. **Định vị GPS thông minh:**
   - Nút *"Vị trí của tôi"* sử dụng HTML5 Geolocation API để định vị vị trí hiện tại của người dùng và đo vi khí hậu xung quanh.

---

## 🚀 Thư viện CDN sử dụng

| Công nghệ | Thư viện CDN | Mục đích |
|-----------|--------------|----------|
| **Styling** | [Tailwind CSS v3 CDN](https://cdn.tailwindcss.com) | Thiết kế Dark Mode hiện đại, Glassmorphism, chuẩn responsive |
| **Bản đồ** | [Leaflet.js v1.9.4](https://unpkg.com/leaflet@1.9.4/) | Hiển thị bản đồ vector & raster tile, ghim tương tác |
| **Biểu đồ** | [Chart.js](https://cdn.jsdelivr.net/npm/chart.js) | Render đồ thị xu hướng 24h |
| **Icons** | [Lucide Icons](https://unpkg.com/lucide@latest) | Bộ icon hiện đại, tối giản, thanh thoát |
| **Dữ liệu** | [Open-Meteo Air Quality & Weather API](https://open-meteo.com) | Nguồn API mở miễn phí, không cần đăng ký API key |

---

## 💻 Hướng dẫn chạy thử nghiệm tại máy cá nhân (Local)

Bạn có thể chạy dự án ngay lập tức bằng một trong các cách sau:

### Cách A: Mở trực tiếp bằng trình duyệt
Nhấp đúp chuột trực tiếp vào file `index.html` để mở trong trình duyệt Chrome, Edge, Firefox hoặc Safari.

### Cách B: Chạy qua Live Server (Khuyến nghị cho trải nghiệm mượt nhất)
Nếu bạn có Python trên máy:
```bash
python -m http.server 8000
```
Sau đó truy cập: `http://localhost:8000`

---

## 🌐 Hướng dẫn đưa lên GitHub Pages (Trong vòng 3 phút)

### Bước 1: Khởi tạo Git và Commit
Mở terminal tại thư mục `d:\Airlens` và chạy:
```bash
git init
git add index.html README.md
git commit -m "feat: Khoi tao du an AirLens VN - Giam sat chat luong khong khi do thi"
```

### Bước 2: Tạo Repository trên GitHub và đẩy mã nguồn
1. Truy cập [GitHub](https://github.com/new) và tạo một repo mới (ví dụ đặt tên là `airlens-vn`), chọn **Public**.
2. Liên kết và push lên GitHub:
```bash
git branch -M main
git remote add origin https://github.com/<tai-khoan-cua-ban>/airlens-vn.git
git push -u origin main
```

### Bước 3: Kích hoạt GitHub Pages
1. Tại giao diện Repository trên GitHub, vào **Settings** > **Pages** (ở thanh menu bên trái).
2. Tại mục **Build and deployment** -> **Branch**:
   - Chọn nhánh: `main`
   - Chọn thư mục: `/ (root)`
3. Bấm **Save**.
4. Chờ 1–2 phút, trang web sẽ được kích hoạt tại địa chỉ:
   `https://<tai-khoan-cua-ban>.github.io/airlens-vn/`

---

## 📡 Chi tiết API sử dụng

1. **Air Quality API:**
   ```http
   GET https://air-quality-api.open-meteo.com/v1/air-quality?latitude={lat}&longitude={lng}&current=european_aqi,us_aqi,pm10,pm2_5&hourly=pm2_5,us_aqi&timezone=auto&forecast_days=1
   ```
2. **Weather Forecast API (Nhiệt độ & Độ ẩm):**
   ```http
   GET https://api.open-meteo.com/v1/forecast?latitude={lat}&longitude={lng}&current=temperature_2m,relative_humidity_2m&timezone=auto
   ```

---

## 📜 Tiêu chuẩn minh bạch dữ liệu
- Dữ liệu vi khí hậu và nồng độ chất ô nhiễm được tính toán dựa trên mô hình khí quyển **Copernicus Atmosphere Monitoring Service (CAMS)** của Liên minh Châu Âu kết hợp dữ liệu từ các trạm quan trắc mặt đất thông qua dịch vụ **Open-Meteo**.
- Phù hợp với tiêu chuẩn đánh giá chỉ số AQI của EPA (Hoa Kỳ) và khuyến nghị nồng độ phơi nhiễm bụi mịn của Tổ chức Y tế Thế giới (WHO).

---
© 2026 **AirLens VN Team** - Giải pháp giám sát môi trường thông minh cho đô thị bền vững.

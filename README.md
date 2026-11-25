# 🌿 AirLens VN - Giám sát chất lượng không khí, vi khí hậu và sức khỏe đô thị

**Hệ thống giám sát chất lượng không khí, vi khí hậu và cẩm nang sức khỏe đô thị thời gian thực**  
Ứng dụng Web hiện đại (Single Page Application) sử dụng dữ liệu mở từ **Open-Meteo API và Copernicus Atmosphere Monitoring Service (CAMS)**.

---

## 📖 Giới thiệu dự án

**AirLens VN** là giải pháp công nghệ số phục vụ cộng đồng và mục tiêu phát triển đô thị bền vững. Ứng dụng cung cấp bức tranh toàn diện và minh bạch về hiện trạng chất lượng không khí (AQI), nồng độ bụi mịn ($PM_{2.5}$, $PM_{10}$), các yếu tố vi khí hậu (nhiệt độ, độ ẩm) cùng lịch theo dõi tháng và cẩm nang bảo vệ sức khỏe cho người dân đô thị Việt Nam.

Toàn bộ ứng dụng được xây dựng theo kiến trúc Web tĩnh nhẹ, tối ưu trải nghiệm người dùng, tải dữ liệu trực tiếp từ các mô hình khí quyển chuẩn quốc tế mà không cần hệ thống máy chủ trung gian.

---

## 🌟 Các phân hệ tính năng chính

Ứng dụng được tổ chức khoa học với thanh điều hướng đa tính năng:

### 1. 🌤️ Xem hôm nay (Today Overview)
* **Bản đồ không gian mở tương tác (Leaflet.js):**
  * Tích hợp sẵn danh bạ hơn **25 đô thị trọng điểm** trải dài khắp 3 miền: Miền Bắc, Miền Trung và Tây Nguyên, Miền Nam.
  * Tích hợp tính năng **"Vị trí của tôi"** (HTML5 Geolocation) để tự động định vị GPS của người dùng.
  * Cho phép **click hoặc chạm vào bất kỳ tọa độ nào trên bản đồ** để đo thông số vi khí hậu tức thì tại điểm đó.
  * Hỗ trợ chuyển đổi linh hoạt giữa bản đồ chi tiết Esri World Street Map và bản đồ cộng đồng OpenStreetMap.
* **Đồng hồ thời gian thực (Live Clock):**
  * Hiển thị Thứ, Ngày Tháng Năm và Giờ Phút Giây chạy trực tiếp theo múi giờ Việt Nam (GMT+7).
  * Mốc thời gian cập nhật số liệu của trạm quan trắc.
* **Chỉ số AQI chuẩn quốc tế (US EPA):**
  * Thẻ hiển thị lớn với màu sắc biến đổi động theo ngưỡng ô nhiễm: *Tốt (Xanh lá $\le 50$)*, *Trung bình (Vàng $51-100$)*, *Kém / Nhạy cảm (Cam $101-150$)*, *Xấu / Nguy hại (Đỏ/Tím $>150$)*.
  * Thanh thước đo trực quan thể hiện vị trí kim đo trong thang giá trị 0 – 300+.
* **Bộ 4 thông số đo vi khí hậu:**
  * Bụi mịn $PM_{2.5}$ ($\mu g/m^3$) đối chiếu khuyến nghị của Tổ chức Y tế Thế giới (WHO: $\le 15$).
  * Bụi thô $PM_{10}$ ($\mu g/m^3$) đối chiếu chuẩn WHO ($\le 45$).
  * Nhiệt độ bề mặt (°C) và cảm nhận ngoài trời.
  * Độ ẩm tương đối của không khí (%).
* **Biểu đồ xu hướng 24 giờ (Chart.js):**
  * Đường diễn biến nồng độ $PM_{2.5}$ từ 0h đến 23h trong ngày với hiệu ứng Area Gradient mượt mà.
* **Khuyến nghị nhanh:** Tóm tắt 3 hướng dẫn hành động về Đi lại, Thể thao và Không gian nhà ở.

---

### 2. 📅 Lịch theo dõi tháng (Monthly Calendar)
* **Giao diện lịch tháng thông minh:**
  * Thể hiện toàn bộ các ngày trong tháng dưới dạng lưới 7 cột trực quan.
  * Mỗi ô ngày hiển thị rõ chỉ số AQI phân màu cảnh báo, nồng độ bụi $PM_{2.5}$ trung bình và nhiệt độ trong ngày.
  * Đánh dấu nổi bật ngày hiện tại.
* **Thống kê tổng kết tháng:**
  * Tự động tổng hợp số lượng ngày Không khí Tốt, ngày Trung bình, ngày Kém và ngày Cảnh báo Ô nhiễm trong tháng.
* **Bảng chi tiết ngày được chọn:**
  * Khi bấm vào bất kỳ ngày nào trên lịch, hệ thống sẽ mở bảng phân tích chi tiết: Nồng độ chất ô nhiễm, nhiệt độ, đánh giá chất lượng và lời khuyên sinh hoạt tương ứng cho ngày đó.
* **Điều hướng thời gian:** Dễ dàng chuyển đổi giữa các tháng để theo dõi xu hướng biến đổi môi trường theo mùa.

---

### 3. ❤️ Cẩm nang sức khỏe và hoạt động đô thị (Health & Activities)
* **Hướng dẫn chi tiết cho 4 nhóm đối tượng đặc thù:**
  1. 🏃 **Vận động viên và thể thao ngoài trời:** Khung giờ vàng để chạy bộ/đạp xe tại công viên; ngưỡng AQI cần chuyển bài tập vào phòng trong nhà; hướng dẫn bổ sung nước bảo vệ niêm mạc phế quản.
  2. 👶 **Nhóm nhạy cảm và trẻ nhỏ:** Ngưỡng cảnh báo sớm cho trẻ em và người có tiền sử hen suyễn; hướng dẫn sử dụng khẩu trang lọc bụi mịn chuẩn N95, KN95, KF94 thay thế khẩu trang y tế; phương pháp súc họng, rửa mũi bằng nước muối sinh lý.
  3. 🛵 **Người tham gia giao thông và giao hàng, tài xế:** Nhận diện vùng phơi nhiễm khói bụi cao (nút giao thông, hầm chui); giải pháp che chắn mắt và hệ hô hấp.
  4. 🏠 **Không gian sống và nơi làm việc:** Tiêu chuẩn chọn máy lọc không khí màng HEPA; cách kết hợp cây xanh thanh lọc độc tố trong nhà (Trầu bà, Lan ý, Lưỡi hổ).
* **Bảng quy chuẩn phân cấp AQI quốc tế (US EPA):**
  * Tra cứu đầy đủ các dải điểm AQI từ 0 đến trên 300, phân loại màu sắc, mức độ tác động sinh học và hành vi phòng ngừa tương ứng.

---

## 🛠️ Công nghệ xây dựng

| Thành phần | Công nghệ / Thư viện | Vai trò |
|------------|----------------------|---------|
| **Cốt lõi** | HTML5, CSS3, JavaScript ES6+ | Kiến trúc Single Page Application thuần túy, không cần build step |
| **Giao diện** | [Tailwind CSS v3 CDN](https://cdn.tailwindcss.com) | Thiết kế Clean Weather Light Theme, linh hoạt và đáp ứng tốt mọi kích thước màn hình |
| **Bản đồ** | [Leaflet.js v1.9.4](https://unpkg.com/leaflet@1.9.4/) | Hiển thị bản đồ số Esri World Street Map và OpenStreetMap, ghim trạm đo tương tác |
| **Biểu đồ** | [Chart.js](https://cdn.jsdelivr.net/npm/chart.js) | Vẽ đồ thị biến thiên $PM_{2.5}$ 24 giờ sắc nét |
| **Nguồn dữ liệu** | [Open-Meteo Air Quality & Weather API](https://open-meteo.com) | Dữ liệu mở cập nhật liên tục từ mô hình Copernicus CAMS và quan trắc khí tượng |

---

## 🌿 Tiêu chuẩn minh bạch dữ liệu

* **Mô hình dự báo và quan trắc:** Dữ liệu vi khí hậu và chất lượng không khí được tổng hợp từ dịch vụ **Copernicus Atmosphere Monitoring Service (CAMS)** của Liên minh Châu Âu kết hợp trạm quan trắc mặt đất thông qua Open-Meteo API.
* **Tiêu chuẩn tính toán AQI:** Áp dụng công thức quy đổi chỉ số chất lượng không khí dựa trên tiêu chuẩn của **Cục Bảo vệ Môi trường Hoa Kỳ (US EPA)**.
* **Ngưỡng an toàn bụi mịn:** Tham chiếu hướng dẫn nồng độ phơi nhiễm khuyến nghị của **Tổ chức Y tế Thế giới (WHO 2021)**: $PM_{2.5} \le 15\,\mu g/m^3$ (trung bình 24h) và $PM_{10} \le 45\,\mu g/m^3$.

---

© 2026 **AirLens VN** — Giải pháp quan trắc môi trường và hỗ trợ sức khỏe cộng đồng thông minh.

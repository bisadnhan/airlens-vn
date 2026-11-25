# 🌿 AirLens VN - Giám sát chất lượng không khí, vi khí hậu và sức khỏe đô thị

**AirLens VN** là ứng dụng web thời gian thực (Single Page Application) giúp người dân đô thị theo dõi hiện trạng không khí (AQI), nồng độ bụi mịn ($PM_{2.5}$, $PM_{10}$), nhiệt độ, độ ẩm và các khuyến nghị bảo vệ sức khỏe hữu ích. Toàn bộ dữ liệu được kết nối trực tiếp từ **Open-Meteo API** và mô hình khí quyển **Copernicus CAMS** của Liên minh Châu Âu.

🔗 **Trang web trực tuyến (Live Demo):** [https://bisadnhan.github.io/airlens-vn/](https://bisadnhan.github.io/airlens-vn/)

---

## 🚀 Hướng dẫn cài đặt và chạy thử (Installation)

Ứng dụng được thiết kế theo kiến trúc Web tĩnh hiện đại (HTML5 + Tailwind CSS + Vanilla JS ES6+), **không yêu cầu cài đặt môi trường phức tạp hay build step**. Bạn có thể khởi chạy theo các cách sau:

### Cách 1: Tải về và mở trực tiếp (Đơn giản nhất)
1. Tải toàn bộ mã nguồn về máy (hoặc nhấn nút **Code** > **Download ZIP** trên GitHub rồi giải nén).
2. Nhấp đúp chuột vào file `index.html` để mở ngay trên trình duyệt bất kỳ (Google Chrome, Microsoft Edge, Safari, Firefox,...).

---

### Cách 2: Chạy qua Git và Local Server (Khuyên dùng cho lập trình viên)

1. **Clone dự án về máy tính:**
   ```bash
   git clone https://github.com/bisadnhan/airlens-vn.git
   cd airlens-vn
   ```

2. **Khởi chạy Local Server:**
   * **Cách A - Dùng Visual Studio Code:**
     Cài extension **Live Server** > Chuột phải vào file `index.html` > Chọn **Open with Live Server** (cổng mặc định `http://127.0.0.1:5500`).
   * **Cách B - Dùng Python (có sẵn trên máy):**
     ```bash
     python -m http.server 8000
     ```
     Sau đó truy cập trình duyệt theo địa chỉ: `http://localhost:8000`
   * **Cách C - Dùng Node.js (npx):**
     ```bash
     npx serve .
     ```

---

## 📖 Hướng dẫn sử dụng chi tiết (User Guide)

### 1. Quan trắc không khí hôm nay (`Hôm nay`)
* **Chọn khu vực quan trắc:** Sử dụng menu thả xuống ở thanh công cụ để chọn nhanh hơn **25 tỉnh, thành phố trọng điểm** trên cả 3 miền (Hà Nội, Đà Nẵng, TP. Hồ Chí Minh, Hải Phòng, Huế, Đà Lạt, Cần Thơ,...).
* **Định vị vị trí hiện tại (GPS):** Bấm nút **"Định vị GPS"** và cho phép trình duyệt truy cập vị trí của bạn để tự động lấy số liệu không khí tức thì tại nơi bạn đang đứng.
* **Đo điểm bất kỳ trên bản đồ:** Bạn có thể **click chuột hoặc chạm tay vào bất kỳ điểm nào trên bản đồ**, hệ thống sẽ tự động ghim vị trí và gọi API tính toán chỉ số chất lượng không khí tại tọa độ đó.
* **Đổi kiểu bản đồ:** Bấm nút **"Bản đồ chi tiết" / "Bản đồ cộng đồng"** ở góc phải bản đồ để chuyển đổi qua lại giữa bản đồ vệ tinh/đường phố Esri và OpenStreetMap.
* **Xem chỉ số AQI và bụi mịn:**
  * **AQI (US EPA):** Thẻ số lớn có thanh đo màu phân cấp (Xanh $\le 50$: Tốt, Vàng $51-100$: Trung bình, Cam $101-150$: Kém/Nhạy cảm, Đỏ $>150$: Nguy hại).
  * **$PM_{2.5}$ và $PM_{10}$:** Đối chiếu trực tiếp với quy chuẩn nồng độ an toàn 24h của Tổ chức Y tế Thế giới (WHO 2021).
  * **Biểu đồ 24 giờ:** Theo dõi đường diễn biến nồng độ bụi từ 0h đến 23h trong ngày.
  * **Làm mới dữ liệu:** Bấm nút **"Làm mới"** để kéo dữ liệu quan trắc mới nhất từ vệ tinh.

### 2. Xem lịch theo dõi tháng (`Lịch theo dõi`)
* Bấm vào tab **"Lịch theo dõi"** trên thanh điều hướng.
* **Theo dõi lưới tháng:** Mỗi ô ngày hiển thị rõ chỉ số AQI đổi màu, nồng độ bụi $PM_{2.5}$ trung bình và nhiệt độ.
* **Bấm vào từng ngày:** Xem bảng đánh giá chi tiết tình trạng ô nhiễm và các khuyến nghị vận động dành riêng cho ngày đó.
* **Tính minh bạch dữ liệu:** Các ngày trong tương lai chưa có dữ liệu quan trắc thực tế sẽ được hiển thị dạng `--` (chưa có dự báo) nhằm đảm bảo số liệu chính xác và trung thực.

### 3. Cẩm nang sức khỏe và hoạt động (`Sức khỏe và hoạt động`)
* Bấm vào tab **"Sức khỏe và hoạt động"** để xem hướng dẫn phòng ngừa phơi nhiễm ô nhiễm cho 4 nhóm đối tượng:
  1. **Vận động viên & người tập thể thao:** Khung giờ chạy bộ, tập luyện ngoài trời an toàn.
  2. **Trẻ nhỏ & người có bệnh hô hấp:** Khuyến nghị khẩu trang lọc bụi mịn chuẩn N95/KF94, cách vệ sinh mũi họng.
  3. **Người tham gia giao thông & tài xế:** Nhận diện điểm đen khói bụi và biện pháp bảo vệ.
  4. **Không gian sống & văn phòng:** Hướng dẫn chọn máy lọc không khí chuẩn HEPA và cây xanh thanh lọc khí trong nhà.

---

## 🛠️ Hướng dẫn cập nhật và đẩy code lên GitHub (Git Workflow)

Mỗi khi bạn chỉnh sửa xong mã nguồn và muốn cập nhật ngay lên trang web GitHub Pages, bạn thực hiện các bước sau:

```bash
# 1. Gom tất cả các file đã thay đổi
git add .

# 2. Lưu lại phiên bản với ghi chú mô tả
git commit -m "Mo ta nhung gi ban vua sua doi"

# 3. Đẩy lên nhánh chính (main) trên GitHub
git push origin main
```

> **Gợi ý gộp lệnh trong PowerShell:**
> ```powershell
> git add . ; git commit -m "cap nhat web" ; git push origin main
> ```

*Nếu bạn muốn đẩy lên một nhánh thử nghiệm khác (ví dụ: `dev`):*
```bash
git checkout -b dev
git add .
git commit -m "thu nghiem tinh nang moi"
git push -u origin dev
```

---

## ⚙️ Cấu trúc thư mục dự án

```text
airlens-vn/
├── index.html        # Giao diện chính và toàn bộ mã nguồn ứng dụng (HTML/JS/CSS)
├── assets/           # Tài nguyên hình ảnh, biểu tượng
│   ├── logo-icon.png # Biểu tượng logo AirLens chuẩn độ phân giải cao
│   ├── logo.png      # Logo nhận diện thương hiệu hoàn chỉnh
│   └── logo.jpg      # Bản gốc logo tải lên
└── README.md         # Tài liệu dự án và hướng dẫn sử dụng
```

---

## 🔬 Tiêu chuẩn kỹ thuật và nguồn dữ liệu

* **Dữ liệu khí tượng & khí quyển:** [Open-Meteo Open Data API](https://open-meteo.com/) tổng hợp từ chương trình Copernicus CAMS của Liên minh Châu Âu kết hợp trạm quan trắc mặt đất.
* **Tiêu chuẩn tính toán AQI:** Chuẩn tính toán chỉ số chất lượng không khí của Cục Bảo vệ Môi trường Hoa Kỳ (**US EPA**).
* **Khuyến nghị nồng độ phơi nhiễm:** Dựa theo hướng dẫn chất lượng không khí toàn cầu của Tổ chức Y tế Thế giới (**WHO 2021**): $PM_{2.5} \le 15\,\mu g/m^3$, $PM_{10} \le 45\,\mu g/m^3$.
* **Thư viện giao diện:** Tailwind CSS CDN, Leaflet.js v1.9.4, Chart.js.

---

© 2026 **AirLens VN** — Giải pháp quan trắc môi trường và hỗ trợ sức khỏe cộng đồng thông minh.

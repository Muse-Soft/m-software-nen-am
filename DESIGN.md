# DESIGN.md — Landing page tiệm nến thơm thủ công Nến Ấm

- Nguồn: yêu cầu web MSR-27, Epic TEC-212, task Thiết kế TEC-213.
- Phạm vi: đúng 1 landing page, 1 file `index.html`, không backend.
- Mọi quyết định dưới đây là BẮT BUỘC cho task Dev (TEC-214) và là căn cứ kiểm thử cho task QA (TEC-215). Thiếu một điểm trong mục 1–3 coi như chưa đạt.

## 1. Bảng màu (mã hex kèm vai trò từng màu)

| Mã hex | Vai trò |
|---|---|
| `#FBF7F0` | Nền chính toàn trang (nền ấm sáng) |
| `#F1E9DC` | Nền phụ — khối xen kẽ, nền thẻ phụ |
| `#FFFFFF` | Nền thẻ, nền ô nhập form |
| `#2E2620` | Chữ chính — tiêu đề và nội dung |
| `#7A6A58` | Chữ phụ — chú thích, ghi chú, mô tả phụ |
| `#C07A3E` | Màu nhấn chính — nút chính, giá, liên kết, nhãn khối |
| `#E5DCCB` | Kẻ mảnh, viền thẻ |
| `#241C15` | Nền tối — footer và lớp phủ trên ảnh hero |

Quy tắc: không dùng thêm màu chủ đạo ngoài bảng trên. Ảnh hero dùng lớp phủ `#241C15` ở độ mờ 45% và chữ trắng `#FFFFFF` trên đó — đây là ngoại lệ có chủ đích để chữ đọc được trên ảnh tối, không phải lỗi lệch màu.

## 2. Font chữ (cụ thể, không chung chung)

- Tiêu đề: **Playfair Display**, weight 500 / 600 / 700, chữ thường, không viết hoa toàn bộ.
  - H1 hero: 56px desktop, 36px mobile.
  - H2 tên khối: 36px desktop, 28px mobile.
  - H3 tên thẻ: 22px.
- Nội dung: **Be Vietnam Pro**, weight 400 / 500 / 700, cỡ 16–17px, line-height 1.7.
- Nạp qua Google Fonts `css2` với `display=swap` và subset tiếng Việt; fallback: tiêu đề `Georgia, serif`, nội dung `system-ui, sans-serif`.
- Nhãn khối nhỏ (eyebrow trên H2): Be Vietnam Pro 700, 13px, viết hoa, letter-spacing 0.18em, màu nhấn `#C07A3E`.

## 3. Phong cách tham chiếu (chỉ một)

**Warm Minimalism** — tối giản, ấm áp, nhiều khoảng trắng. Cụ thể: ảnh lớn làm nội dung chính, ít chữ, một màu nhấn duy nhất, không icon stock, không họa tiết rườm rà, không khối màu chói. Mọi khối đều có khoảng trắng lớn bao quanh (xem mục 4).

## 4. Bố cục và nhịp chung

- Chiều rộng nội dung tối đa 1120px, căn giữa; padding dọc mỗi khối 96px desktop, 64px mobile.
- Header dính (sticky): cao 64px, nền `#FBF7F0`, logo chữ "Nến Ấm" (Playfair Display 600, 24px), menu neo tới `#bo-suu-tap`, `#quy-trinh`, `#goi-y`, `#bang-gia`, `#lien-he`, nút chính "Đặt hàng" neo tới `#lien-he`.
- Breakpoint mobile 768px: mọi lưới chuyển về 1 cột, menu thu gọn bằng nút bấm (không giấu hẳn menu).
- Thứ tự khối không được đổi (mục 5).

## 5. Nội dung trang — 8 khối theo đúng thứ tự

### Khối 1 — Header (neo, không tính là khối nội dung ảnh)

Như mục 4. Không có ảnh.

### Khối 2 — Hero: ảnh lớn toàn màn hình

- Ảnh: một hũ nến đang cháy trong không gian tối ấm, khung **16:9 full-bleed**, lớp phủ tối `#241C15` 45%.
- Tiêu đề H1: "Ánh nến ấm cho tổ ấm".
- Phụ đề (1 câu): "Nến đổ tay từ sáp đậu nành — mỗi hũ một mùi hương ấm cho góc nhà của bạn."
- 2 nút: nút chính "Xem bộ sưu tập" (nền `#C07A3E`, chữ trắng) neo tới `#bo-suu-tap`; nút phụ "Quy trình làm nến" (viền trắng) neo tới `#quy-trinh`.
- Chữ trên hero là trắng `#FFFFFF` (ngoại lệ có chủ đích, xem mục 1).

### Khối 3 — Bộ sưu tập mùi hương theo mùa (`#bo-suu-tap`)

- Lưới 3 thẻ desktop, 1 cột mobile; ảnh thẻ khung **4:5**, đồng tông ấm, ánh nến vàng dịu.
- 3 mùi chính (tên + mô tả 1 câu + mùa gợi ý, tất cả là nội dung mẫu):
  - Gỗ đàn hương — ấm, sâu, gỗ nhẹ — gợi ý mùa Thu–Đông.
  - Vani — ngọt dịu, êm — gợi ý quanh năm.
  - Cam bergamot — tươi sáng, vỏ cam nhẹ — gợi ý mùa Xuân–Hè.
- Mỗi thẻ ghi chú "(ảnh mẫu)" trong thuộc tính alt của ảnh.

### Khối 4 — Quy trình làm nến thủ công (`#quy-trinh`)

- 4 bước theo đúng thứ tự, lưới 4 cột desktop, 1 cột mobile; ảnh minh họa khung **3:2** cho cả khối (một ảnh lớn trên, 4 bước dưới dạng thẻ chữ):
  1. Chọn sáp đậu nành — sáp sạch, cháy đều.
  2. Đổ tay và cắm bấc — từng hũ đổ bằng tay, căn bấc giữa.
  3. Ủ và hoàn thiện — để sáp đông tự nhiên, cắt bấc, lau hũ.
  4. Đóng gói — hộp giấy, kèm thiệp ghi tay (mẫu).
- Không ghi thời gian ủ cụ thể bằng số nếu chưa có dữ liệu thật; chỉ ghi "ủ tự nhiên".

### Khối 5 — Gợi ý chọn nến theo không gian (`#goi-y`)

- Lưới 3 thẻ desktop, 1 cột mobile; ảnh thẻ khung **4:3**:
  - Phòng ngủ — mùi dịu (Vani), thắp buổi tối, ánh thấp.
  - Phòng tắm — mùi tươi (Cam bergamot), thắp khi thư giãn.
  - Bàn làm việc — mùi gỗ nhẹ (Gỗ đàn hương), thắp khi cần tập trung.
- Mỗi thẻ: tên không gian + mùi gợi ý + 1 câu lý do. Đây là gợi ý mẫu, không phải tư vấn chuyên môn.

### Khối 6 — Bảng giá mẫu theo size hũ (`#bang-gia`)

- Bảng 3 cột desktop, 1 cột mobile (dạng thẻ xếp dọc, không dùng bảng cuộn ngang):
  - Hũ nhỏ — 120g — 180.000đ — thời gian cháy mẫu ~25 giờ.
  - Hũ vừa — 200g — 260.000đ — thời gian cháy mẫu ~40 giờ.
  - Hũ lớn — 320g — 360.000đ — thời gian cháy mẫu ~60 giờ.
- Dòng ghi chú bắt buộc, đặt ngay dưới bảng, nguyên văn: "Tất cả giá trên trang là giá mẫu."
- Không dùng ảnh trong khối này, chỉ chữ và màu nhấn cho giá.

### Khối 7 — Form liên hệ / đặt hàng (`#lien-he`)

- Chỉ giao diện, KHÔNG gửi dữ liệu thật. Các trường: Họ tên, Số điện thoại, Mùi muốn đặt, Size hũ, Ghi chú (tùy chọn).
- Nút gửi: "Gửi yêu cầu" (nền `#C07A3E`, chữ trắng). Khi bấm, chỉ ngăn gửi form (preventDefault) và hiện đúng dòng: "Bản demo — form chưa gửi dữ liệu thật."
- Không gắn liên kết `tel:` nào khi chưa có số điện thoại thật; không hứa "sẽ liên hệ xác nhận".

### Khối 8 — Footer

- Nền tối `#241C15`, chữ `#FBF7F0`: tên "Nến Ấm", câu "Nến đổ tay từ sáp đậu nành", địa chỉ `[CẦN BỔ SUNG]`, điện thoại `[CẦN BỔ SUNG]`.
- Dòng cuối: "Ảnh trên trang là ảnh mẫu. Trang này là bản demo giới thiệu."

## 6. Quy tắc hình ảnh (áp cho mọi ảnh)

- Ảnh mẫu chất lượng cao, đồng tông ấm, ánh nến vàng dịu; cấm ảnh tông lạnh, xanh, hoặc ảnh lệch tông.
- Tỉ lệ khung bắt buộc: hero 16:9, bộ sưu tập 4:5, quy trình 3:2, gợi ý 4:3; khối bảng giá và form không dùng ảnh.
- Ảnh là nội dung chính: ảnh hero full-bleed, ảnh thẻ rộng tối thiểu 320px trên mobile và 520px trên desktop (trừ ảnh quy trình 3:2).
- Mọi ảnh đều có alt kết thúc bằng "(ảnh mẫu)" và được khai báo là ảnh mẫu trong mã nguồn (comment hoặc chú thích).
- Không dùng ảnh có logo, chữ, hoặc thương hiệu thật của bên khác.

## 7. Dữ liệu thật và dữ liệu mẫu — phân biệt rạch ròi

- Dữ liệu thật chưa có → để nguyên `[CẦN BỔ SUNG]`: địa chỉ, điện thoại. Tuyệt đối không bịa số điện thoại, địa chỉ, hoặc tên người thật.
- Dữ liệu mẫu (được phép, phải ghi rõ là mẫu): toàn bộ giá (kèm dòng "Tất cả giá trên trang là giá mẫu."), thời gian cháy (~25/~40/~60 giờ), tên mùi và mô tả, gợi ý theo không gian, ảnh mẫu.
- Form chỉ giao diện (mục 5, khối 7); không có backend, không có lời hứa liên hệ.

## 8. Checklist nghiệm thu cho Dev và QA (đối chiếu DESIGN.md này)

- [ ] Đủ 8 khối, đúng thứ tự, đúng neo `#bo-suu-tap`, `#quy-trinh`, `#goi-y`, `#bang-gia`, `#lien-he`.
- [ ] Đủ 8 mã hex ở mục 1 đúng vai trò; màu nhấn duy nhất là `#C07A3E`.
- [ ] Font Playfair Display (tiêu đề) + Be Vietnam Pro (nội dung), subset tiếng Việt, đúng cỡ mục 2.
- [ ] Phong cách Warm Minimalism thể hiện bằng ảnh lớn + khoảng trắng (mục 3–4), không icon stock.
- [ ] Ảnh đúng tỉ lệ khung và tông ấm (mục 6), alt kết thúc "(ảnh mẫu)".
- [ ] Giá kèm dòng "Tất cả giá trên trang là giá mẫu."; địa chỉ/điện thoại là `[CẦN BỔ SUNG]`; form chỉ hiện "Bản demo — form chưa gửi dữ liệu thật.".
- [ ] Mobile 768px: 1 cột, header dính 64px, menu mở được bằng nút bấm.
- [ ] Kiểm tra thẩm mỹ (OPERATIONS.md §16.4): đối chiếu thị giác với DESIGN.md này; không chụp được màn hình thì ghi rõ "chưa kiểm thị giác — mới kiểm mức code", không kết luận đạt thẩm mỹ.

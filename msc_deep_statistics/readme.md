# HƯỚNG DẪN SỬ DỤNG CÁC MODULE PHÂN TÍCH ĐẤU THẦU THUỐC

**Dành cho người dùng cuối**  
**Phạm vi:** tra cứu kết quả đấu thầu thuốc, phân tích công ty sản xuất, phân tích người mua/bệnh viện/bên mời thầu.  
**Ngôn ngữ giao diện:** mặc định Tiếng Việt, có lựa chọn English.  
**Khuyến nghị:** khi phân tích chính thức, chọn nguồn dữ liệu trực tiếp và đặt giới hạn tải bằng `0` để không giới hạn số dòng.

---

## 1. Tổng quan bộ module

Bộ module phân tích đấu thầu thuốc giúp người dùng trả lời nhanh các câu hỏi quan trọng trong kinh doanh, nghiên cứu thị trường, quản lý danh mục sản phẩm và phân tích cạnh tranh.

### 1.1. Ba module chính

| Module | Mục đích chính | Người dùng phù hợp |
|---|---|---|
| Tra cứu kết quả đấu thầu thuốc | Tìm nhanh dữ liệu theo từ khóa | Người cần xem nhanh thuốc, hoạt chất, công ty, bệnh viện, mã thầu |
| Phân tích công ty sản xuất thuốc | Phân tích tình hình đấu thầu theo nhà sản xuất | Kinh doanh, quản lý sản phẩm, phân tích cạnh tranh |
| Phân tích người mua/bệnh viện | Phân tích hành vi mua sắm của bệnh viện, Sở Y tế, bên mời thầu | Kinh doanh, market access, tender team, quản lý bán hàng |

### 1.2. Nhóm dữ liệu có thể phân tích

- Thuốc tân dược.
- Dược liệu.
- Vị thuốc cổ truyền.
- Thiết bị, vật tư y tế.
- Hàng hóa khác trong dữ liệu đấu thầu.

### 1.3. Các trường dữ liệu thường gặp

- Tên thuốc, hoạt chất, hàm lượng, dạng bào chế, đường dùng.
- Số lượng, đơn giá, đơn vị tính, quy cách đóng gói.
- Cơ sở sản xuất, nước sản xuất, xuất xứ.
- Bên mua/bệnh viện/bên mời thầu.
- Ngày đăng tải, số quyết định, mã thông báo mời thầu.
- Hình thức lựa chọn nhà thầu, địa điểm, nhóm thuốc.

---

## 2. Nguyên tắc sử dụng quan trọng

### 2.1. Chọn đúng phạm vi lọc

Khi phân tích công ty sản xuất, nên chọn:

```text
Chỉ cơ sở sản xuất
```

Khi phân tích bệnh viện hoặc bên mua, nên chọn:

```text
Chỉ bên mua
```

Nếu chọn tìm trên toàn bộ nội dung, kết quả có thể rộng hơn nhưng dễ có dữ liệu nhiễu.

### 2.2. Chọn đúng kiểu khớp từ khóa

| Kiểu khớp | Khi nào nên dùng | Ví dụ |
|---|---|---|
| Đúng cụm từ / ranh giới từ | Khuyến nghị mặc định | Tìm `Imexpharm` nhưng không lấy `Agimexpharm` |
| Đúng toàn bộ giá trị trường | Khi cần chính xác tuyệt đối | Chỉ lấy đúng `Bệnh viện Bạch Mai` |
| Chứa tất cả từ | Khi muốn tìm rộng/thăm dò | Tìm `Bạch Mai` để xem tất cả đơn vị liên quan |

### 2.3. Dùng giới hạn tải bằng 0 khi phân tích chính thức

Trong các module phân tích sâu, nếu có mục giới hạn tải, nhập:

```text
0
```

Ý nghĩa: lấy toàn bộ dòng phù hợp để phân tích, không cắt ở 2.000 dòng.

### 2.4. Luôn kiểm tra biến thể tên

Một công ty hoặc bệnh viện có thể xuất hiện dưới nhiều cách viết. Ví dụ:

```text
Công ty Cổ phần Dược Hậu Giang
CTCP Dược Hậu Giang
DHG Pharma
Công ty cổ phần dược Hậu Giang - CN nhà máy DP DHG tại Hậu Giang
```

Vì vậy trước khi kết luận, nên xem tab **Biến thể tên**.

---

# PHẦN A. MODULE TRA CỨU KẾT QUẢ ĐẤU THẦU THUỐC

## 3. Mục đích

Module tra cứu dùng để tìm nhanh dữ liệu đấu thầu theo từ khóa. Đây là module nên dùng đầu tiên khi người dùng chưa chắc cần phân tích theo công ty hay theo người mua.

Module giúp trả lời các câu hỏi:

- Thuốc này đã xuất hiện trong kết quả đấu thầu chưa?
- Hoạt chất này có những sản phẩm nào?
- Công ty này có những mặt hàng nào trong dữ liệu?
- Bệnh viện này mua các thuốc nào?
- Sản phẩm nào có giá thấp nhất hoặc cao nhất?
- Có bao nhiêu dòng dữ liệu liên quan đến một từ khóa?

## 4. Các bước thao tác

### Bước 1. Chọn ngôn ngữ

Chọn `VN` để dùng tiếng Việt hoặc `EN` để dùng tiếng Anh.

### Bước 2. Chọn nguồn tìm kiếm

Có thể chọn một trong các nguồn:

- Thuốc tân dược.
- Dược liệu.
- Vị thuốc cổ truyền.
- Thiết bị, vật tư y tế.
- Hàng hóa khác.
- Tất cả nguồn.

Ví dụ: nếu tìm thuốc viên, thuốc tiêm hoặc hoạt chất, chọn **Thuốc tân dược**. Nếu chưa chắc dữ liệu thuộc nhóm nào, chọn **Tất cả nguồn**.

### Bước 3. Nhập từ khóa

Ví dụ từ khóa đơn:

```text
Nexium
```

```text
Esomeprazole
```

```text
Traphaco
```

```text
Bệnh viện Bạch Mai
```

Ví dụ nhiều từ khóa, mỗi dòng một từ khóa:

```text
Traphaco
Boganic
Cebraton
Dưỡng cốt
```

Hoặc dùng dấu phẩy:

```text
Traphaco, Boganic, Cebraton, Dưỡng cốt
```

### Bước 4. Chọn kiểu tìm kiếm

- **Chứa tất cả từ:** phù hợp khi muốn tìm rộng.
- **Đúng cụm từ:** phù hợp khi biết chính xác cụm cần tìm.
- **Đúng cụm từ / ranh giới từ:** phù hợp để tránh nhầm tên ngắn với tên dài.
- **Đúng toàn bộ giá trị trường:** phù hợp khi muốn kết quả thật chặt.

### Bước 5. Chọn giới hạn kết quả

- Dùng `500` hoặc `1000` để thử nhanh.
- Dùng `0` nếu muốn lấy toàn bộ kết quả phù hợp trong bản không giới hạn.

### Bước 6. Chọn sắp xếp

- **Mới nhất trước:** xem kết quả gần đây nhất.
- **Giá thấp trước:** tìm lựa chọn giá thấp.
- **Giá cao trước:** phát hiện các dòng giá trị cao hoặc bất thường.

### Bước 7. Lọc theo ngày nếu cần

Ví dụ muốn xem kết quả năm 2026:

```text
Từ ngày: 2026-01-01
Đến ngày: 2026-12-31
```

## 5. Các khu vực kết quả

### 5.1. Bảng kết quả dễ đọc

Hiển thị các cột quan trọng như tên thuốc, hoạt chất, hàm lượng, dạng bào chế, đơn giá, nhà sản xuất, bên mua và ngày đăng tải.

### 5.2. Thẻ kết quả

Hiển thị từng dòng theo dạng dễ đọc hơn, phù hợp khi cần xem từng kết quả.

### 5.3. Tóm tắt nhanh

Có thể gồm:

- Số dòng kết quả.
- Giá thấp nhất.
- Giá trung vị.
- Giá cao nhất.
- Top tên thuốc.
- Top nhà sản xuất.
- Top bên mua.
- Top nước sản xuất/xuất xứ.

### 5.4. Tải kết quả

Có thể tải kết quả dạng CSV hoặc Excel để lưu trữ hoặc phân tích tiếp.

## 6. Ví dụ sử dụng module tra cứu

### Ví dụ 1. Tìm hoạt chất Esomeprazole

Thiết lập:

```text
Nguồn: Thuốc tân dược
Từ khóa: Esomeprazole
Sắp xếp: Giá thấp trước
```

Câu hỏi có thể trả lời:

- Esomeprazole có những sản phẩm nào?
- Nhà sản xuất nào tham gia?
- Bệnh viện nào mua?
- Giá thấp nhất và cao nhất là bao nhiêu?

### Ví dụ 2. Tìm sản phẩm Boganic

Thiết lập:

```text
Nguồn: Tất cả nguồn
Từ khóa: Boganic
Kiểu tìm kiếm: Đúng cụm từ
```

Câu hỏi có thể trả lời:

- Boganic xuất hiện ở những bên mua nào?
- Đơn giá theo từng dòng là bao nhiêu?
- Sản phẩm thuộc nhà sản xuất nào?

### Ví dụ 3. Tìm dữ liệu liên quan Bệnh viện Bạch Mai

Nếu nhập:

```text
Bạch Mai
```

có thể ra nhiều đơn vị liên quan. Nếu muốn đúng bệnh viện, nên nhập:

```text
Bệnh viện Bạch Mai
```

và chọn kiểu khớp chính xác hơn.

---

# PHẦN B. MODULE PHÂN TÍCH CÔNG TY SẢN XUẤT THUỐC

## 7. Mục đích

Module phân tích công ty sản xuất dùng để đánh giá tình hình đấu thầu của một nhà sản xuất thuốc hoặc một nhóm tên nhà sản xuất.

Module giúp trả lời:

- Công ty có bao nhiêu dòng trúng thầu?
- Tổng giá trị ước tính là bao nhiêu?
- Sản phẩm nào đóng góp giá trị lớn nhất?
- Hoạt chất nào là nhóm chủ lực?
- Bên mua nào mua nhiều nhất?
- Giá có biến động bất thường không?
- Công ty có phụ thuộc vào một vài sản phẩm không?
- Xu hướng theo tháng tăng hay giảm?
- Dự báo các tháng tới ra sao?

## 8. Nguồn dữ liệu

### 8.1. Dữ liệu đấu thầu trực tiếp

Đây là lựa chọn khuyến nghị. Module đọc trực tiếp từ dữ liệu đã chuẩn bị trong hệ thống, giúp phân tích đầy đủ hơn và không phụ thuộc file Excel export.

### 8.2. Tải lên file Excel/CSV

Dùng khi người dùng có file export riêng, ví dụ:

```text
Traphaco_medicine_tender_search_results.xlsx
```

```text
DHG_medicine_tender_search_results.xlsx
```

### 8.3. Mở thư mục export đã lưu

Dùng khi hệ thống đã lưu sẵn file export. Đường dẫn nội bộ được ẩn với người dùng cuối. Người dùng chỉ chọn kiểu file `*.xlsx` hoặc `*.csv` rồi bấm tải.

## 9. Quy trình phân tích một công ty

1. Mở module **Phân tích công ty sản xuất thuốc**.
2. Chọn ngôn ngữ `VN`.
3. Chọn nguồn dữ liệu **Dữ liệu đấu thầu trực tiếp**.
4. Nhập tên công ty.
5. Chọn phạm vi lọc **Chỉ cơ sở sản xuất**.
6. Chọn kiểu khớp **Đúng cụm từ / ranh giới từ**.
7. Đặt giới hạn tải là `0`.
8. Bấm tải dữ liệu/phân tích.
9. Xem các tab tổng quan, sản phẩm, người mua, xu hướng, dự báo, giá, tín hiệu chiến lược.
10. Xuất Excel nếu cần báo cáo.

## 10. Ví dụ phân tích công ty

### Ví dụ 1. Traphaco

Thiết lập:

```text
Từ khóa: Traphaco
Phạm vi lọc: Chỉ cơ sở sản xuất
Kiểu khớp: Đúng cụm từ / ranh giới từ
Giới hạn tải: 0
```

Câu hỏi phân tích:

- Traphaco có những sản phẩm chủ lực nào?
- Sản phẩm nào đóng góp giá trị cao nhất?
- Bệnh viện/Sở Y tế nào mua nhiều nhất?
- Giá các sản phẩm chủ lực có ổn định không?
- Dự báo 6 tháng tới tăng hay giảm?

### Ví dụ 2. Dược Hậu Giang / DHG

Thiết lập:

```text
Từ khóa: Dược Hậu Giang
Phạm vi lọc: Chỉ cơ sở sản xuất
Kiểu khớp: Đúng cụm từ / ranh giới từ
Giới hạn tải: 0
```

Có thể thử thêm:

```text
DHG
```

Cần xem tab **Biến thể tên công ty** để biết dữ liệu có nhiều cách ghi khác nhau hay không.

### Ví dụ 3. Imexpharm tránh nhầm Agimexpharm

Thiết lập đúng:

```text
Từ khóa: Imexpharm
Phạm vi lọc: Chỉ cơ sở sản xuất
Kiểu khớp: Đúng cụm từ / ranh giới từ
```

Không nên dùng kiểu tìm quá rộng nếu muốn tránh lấy nhầm:

```text
Agimexpharm
```

Nếu muốn chặt hơn nữa, chọn:

```text
Đúng toàn bộ giá trị trường
```

## 11. Các tab chức năng của module công ty

### 11.1. Tab Tổng quan

Hiển thị các chỉ số chính:

- Số dòng dữ liệu.
- Tổng giá trị ước tính.
- Số sản phẩm.
- Số hoạt chất.
- Số bên mua.
- Số tháng có hoạt động.
- Giá thấp nhất, trung vị, cao nhất.

Cách đọc: nếu số dòng lớn, nhiều sản phẩm và nhiều buyer, công ty có độ phủ tốt. Nếu tổng giá trị cao nhưng số sản phẩm ít, công ty có thể phụ thuộc vào một vài sản phẩm chủ lực.

### 11.2. Tab Biến thể tên công ty

Cho biết cùng một công ty đang được ghi bằng những tên nào. Tab này rất quan trọng để tránh bỏ sót hoặc phân tách dữ liệu sai.

### 11.3. Tab Sản phẩm

Phân tích:

- Top sản phẩm theo giá trị.
- Top sản phẩm theo số dòng.
- Top hoạt chất.
- ABC/Pareto sản phẩm.
- Treemap sản phẩm/hoạt chất.
- Scatter số lượng và giá trung vị.

Ứng dụng: xác định sản phẩm nhóm A, sản phẩm chủ lực và sản phẩm có rủi ro phụ thuộc doanh thu.

### 11.4. Tab Người mua

Phân tích:

- Top bên mua theo giá trị.
- Top bên mua theo số dòng.
- Buyer mua lặp lại nhiều tháng.
- Số sản phẩm theo từng buyer.
- Giá trị trung bình mỗi tháng theo buyer.

Ứng dụng: xác định khách hàng chiến lược và buyer có nhu cầu ổn định.

### 11.5. Tab Xu hướng

Hiển thị theo tháng:

- Tổng giá trị.
- Số dòng.
- Số buyer.
- Giá trung vị.

Ứng dụng: xem xu hướng tăng/giảm, mùa vụ, tháng đột biến và chu kỳ đấu thầu.

### 11.6. Tab Dự báo

Dự báo theo 3, 6, 12 hoặc 18 tháng cho các chỉ tiêu:

- Giá trị đấu thầu ước tính.
- Số dòng kết quả.
- Số buyer.
- Giá trung vị.

Có thể có 3 kịch bản:

- Conservative: thận trọng.
- Base: cơ sở.
- Optimistic: tích cực.

Lưu ý: dự báo chỉ mang tính tham khảo, đặc biệt khi dữ liệu lịch sử ít.

### 11.7. Tab Phân khúc

Có thể gồm:

- Ma trận buyer x sản phẩm.
- Heatmap giá trị.
- Cơ cấu dạng bào chế.
- Cơ cấu đường dùng.
- Cơ cấu nước sản xuất/xuất xứ.

Ứng dụng: biết sản phẩm nào đi vào buyer nào và nhóm dạng bào chế nào chiếm tỷ trọng lớn.

### 11.8. Tab Giá và bất thường

Phân tích:

- Outlier giá theo IQR.
- Biến động giá theo sản phẩm.
- Price spread.
- Hệ số biến thiên giá.

Ứng dụng: phát hiện dòng giá quá cao/quá thấp, sai đơn vị, khác quy cách hoặc dữ liệu bất thường.

### 11.9. Tab Tín hiệu chiến lược

Gợi ý tự động về:

- Mức độ phụ thuộc sản phẩm.
- Mức độ phụ thuộc buyer.
- Tăng trưởng gần đây.
- Rủi ro biến động giá.
- Cơ hội mở rộng buyer hoặc sản phẩm.

### 11.10. Xuất báo cáo Excel

Excel thường gồm nhiều sheet:

- Summary.
- Manufacturer variants.
- Products by value.
- Product ABC.
- Buyers by value.
- Monthly trend.
- Forecast.
- Price outliers.
- Raw data.

---

# PHẦN C. MODULE PHÂN TÍCH NGƯỜI MUA / BỆNH VIỆN / BÊN MỜI THẦU

## 12. Mục đích

Module người mua dùng để phân tích hành vi mua sắm của bệnh viện, Sở Y tế, trung tâm mua sắm hoặc bên mời thầu.

Module giúp trả lời:

- Đơn vị này mua những thuốc nào nhiều nhất?
- Tổng giá trị mua sắm ước tính là bao nhiêu?
- Nhà sản xuất nào chiếm tỷ trọng lớn?
- Hoạt chất nào được mua nhiều?
- Dạng bào chế nào chiếm ưu thế?
- Giá mua có bất thường không?
- Xu hướng mua sắm tăng hay giảm?
- Dự báo nhu cầu các tháng tới?

## 13. Quy trình phân tích một người mua

1. Mở module **Phân tích người mua / bệnh viện**.
2. Chọn nguồn **Dữ liệu đấu thầu trực tiếp**.
3. Nhập tên bệnh viện hoặc bên mua.
4. Chọn phạm vi lọc **Chỉ bên mua**.
5. Chọn kiểu khớp **Đúng cụm từ / ranh giới từ**.
6. Nếu cần chính xác tuyệt đối, chọn **Đúng toàn bộ giá trị trường**.
7. Đặt giới hạn tải là `0`.
8. Xem các tab phân tích.
9. Xuất Excel nếu cần báo cáo.

## 14. Ví dụ phân tích người mua

### Ví dụ 1. Bệnh viện Bạch Mai

Thiết lập:

```text
Từ khóa: Bệnh viện Bạch Mai
Phạm vi lọc: Chỉ bên mua
Kiểu khớp: Đúng cụm từ / ranh giới từ
Giới hạn tải: 0
```

Câu hỏi phân tích:

- Bệnh viện Bạch Mai mua nhóm thuốc nào nhiều nhất?
- Nhà sản xuất nào chiếm tỷ trọng lớn?
- Có phụ thuộc vào một vài nhà sản xuất không?
- Dạng bào chế nào chiếm giá trị cao?
- Giá sản phẩm nào bất thường?
- Dự báo nhu cầu 6 tháng tới như thế nào?

### Ví dụ 2. Tránh nhiễu khi tìm Bạch Mai

Nếu nhập:

```text
Bạch Mai
```

có thể ra:

```text
Bệnh viện Bạch Mai
Trạm Y tế phường Bạch Mai
Trường Mẫu giáo Bạch Mai
```

Để chính xác hơn, nhập:

```text
Bệnh viện Bạch Mai
```

và chọn:

```text
Phạm vi lọc: Chỉ bên mua
Kiểu khớp: Đúng toàn bộ giá trị trường
```

### Ví dụ 3. Sở Y tế Hà Nội

Thiết lập:

```text
Từ khóa: Sở Y tế Hà Nội
Phạm vi lọc: Chỉ bên mua
Kiểu khớp: Đúng cụm từ / ranh giới từ
Giới hạn tải: 0
```

Câu hỏi phân tích:

- Sở Y tế Hà Nội mua nhiều hoạt chất nào?
- Nhà sản xuất nào có tỷ trọng lớn?
- Xu hướng mua sắm theo tháng ra sao?
- Có mùa vụ mua sắm rõ ràng không?

## 15. Các tab chức năng của module người mua

### 15.1. Tab Tổng quan

Hiển thị:

- Số dòng dữ liệu.
- Tổng giá trị mua sắm ước tính.
- Số sản phẩm.
- Số hoạt chất.
- Số nhà sản xuất.
- Số tháng có dữ liệu.
- Giá thấp nhất, trung vị, cao nhất.

### 15.2. Tab Biến thể tên người mua

Giúp kiểm tra cùng một buyer/bệnh viện có nhiều cách viết hay không.

Ví dụ:

```text
Bệnh viện Bạch Mai
BV Bạch Mai
Bệnh viện Bạch Mai - Cơ sở 2
```

### 15.3. Tab Sản phẩm

Phân tích:

- Top sản phẩm theo giá trị.
- Top hoạt chất.
- ABC/Pareto danh mục sản phẩm.
- Cơ cấu dạng bào chế.
- Cơ cấu đường dùng.

### 15.4. Tab Nhà sản xuất

Phân tích:

- Top nhà sản xuất theo giá trị.
- Top nhà sản xuất theo số dòng.
- Số sản phẩm của từng nhà sản xuất.
- Số tháng hoạt động của từng nhà sản xuất.
- HHI concentration.
- Top 1, Top 3, Top 5, Top 10 share.

### 15.5. HHI là gì?

HHI là chỉ số đo mức độ tập trung. Cách hiểu đơn giản:

- HHI thấp: buyer mua từ nhiều nhà sản xuất, ít phụ thuộc.
- HHI cao: buyer tập trung vào ít nhà sản xuất, có thể có rủi ro phụ thuộc nguồn cung.

Ví dụ:

```text
Top 3 nhà sản xuất chiếm 65% tổng giá trị
```

Ý nghĩa: danh mục mua sắm đang tập trung mạnh vào một số nhà sản xuất.

### 15.6. Tab Xu hướng mua sắm

Hiển thị theo tháng:

- Tổng giá trị mua.
- Số dòng kết quả.
- Số sản phẩm.
- Số nhà sản xuất.
- Giá trung vị.

Ứng dụng:

- Xem chu kỳ mua sắm.
- Phát hiện tháng cao điểm.
- So sánh 3 tháng gần nhất với giai đoạn trước.
- Theo dõi tăng/giảm nhu cầu.

### 15.7. Tab Dự báo nhu cầu

Dự báo 3, 6, 12 hoặc 18 tháng cho:

- Giá trị mua sắm.
- Số dòng.
- Số sản phẩm.
- Giá trung vị.

Ứng dụng:

- Lập kế hoạch bán hàng.
- Chuẩn bị hồ sơ thầu.
- Dự kiến tồn kho.
- Theo dõi cơ hội tiếp cận bệnh viện.

### 15.8. Tab Phân khúc

Có thể gồm:

- Ma trận nhà sản xuất x sản phẩm.
- Heatmap giá trị.
- Route/dosage-form mix.
- Country/origin mix.
- Tender method mix.

### 15.9. Tab Giá và bất thường

Phát hiện:

- Giá quá cao.
- Giá quá thấp.
- Biến động giá bất thường.
- Sản phẩm cùng tên nhưng giá khác xa.
- Dữ liệu có thể sai đơn vị hoặc khác quy cách.

### 15.10. Tab Tín hiệu chiến lược người mua

Gợi ý:

- Buyer có danh mục rộng hay hẹp.
- Buyer phụ thuộc nhiều vào một vài nhà sản xuất hay không.
- Buyer có xu hướng tăng mua hay giảm mua.
- Có cơ hội tiếp cận sản phẩm mới hay không.

---

# PHẦN D. BIỂU ĐỒ VÀ TÙY CHỌN TÔNG MÀU

## 16. Mục đích của biểu đồ

Biểu đồ giúp người dùng nhìn nhanh xu hướng, cơ cấu, mức độ tập trung và bất thường.

Các dạng biểu đồ thường có:

- Bar chart.
- Line chart.
- Scatter chart.
- Treemap.
- Heatmap.
- Forecast chart.

## 17. Chọn tông màu

Người dùng có thể chọn tông màu biểu đồ trong danh sách.

### 17.1. Tông nóng / premium

| Palette | Mô tả | Gợi ý sử dụng |
|---|---|---|
| Inferno | Tím - đỏ - cam - vàng | Dashboard cao cấp, tương phản mạnh |
| Magma | Tím đậm - hồng - cam nhạt | Sang, dịu hơn Inferno |
| Plasma | Tím - hồng - vàng | Hiện đại, nổi bật |
| YlOrRd | Vàng - cam - đỏ | Heatmap cổ điển, dễ nhìn |
| Hot | Đen - đỏ - vàng - trắng | Cường độ nổi bật |

### 17.2. Tông mát / chuyên nghiệp

| Palette | Mô tả | Gợi ý sử dụng |
|---|---|---|
| Viridis | Xanh tím - xanh lá - vàng | Phổ biến, dễ đọc |
| Cividis | Xanh xám - vàng | Thân thiện hơn với người mù màu |
| Tealgrn | Xanh ngọc - xanh lá | Sạch, hợp data science |
| Blues | Xanh dương đơn sắc | Tối giản, hợp báo cáo |
| YlGnBu | Vàng - xanh lá - xanh dương | Cân bằng, dễ nhìn |

### 17.3. Tông rực / dashboard

| Palette | Mô tả | Gợi ý sử dụng |
|---|---|---|
| Turbo | Rất rực | Dùng khi cần nổi bật mạnh |
| Rainbow | Cầu vồng | Vui mắt, nên dùng cẩn thận |
| Electric | Neon hiện đại | Dashboard trình chiếu |
| Jet | Classic | Dùng cẩn thận vì dễ gây hiểu nhầm mức độ |

### 17.4. Tông sang / tối / cinematic

| Palette | Mô tả | Gợi ý sử dụng |
|---|---|---|
| Blackbody | Đen - đỏ - vàng - trắng | Cinematic, hợp nền tối |
| Greys | Xám đơn sắc | Báo cáo in, tối giản |
| Burg | Đỏ rượu vang | Sang trọng nếu Plotly hỗ trợ |

## 18. Gợi ý chọn màu nhanh

- Báo cáo chuyên nghiệp: `Viridis`, `Cividis`, `Blues`.
- Báo cáo quản trị: `YlGnBu`, `Tealgrn`, `Magma`.
- Dashboard trình chiếu: `Inferno`, `Plasma`, `Electric`.
- Heatmap giá trị: `YlOrRd`, `Viridis`, `Cividis`.
- Báo cáo in: `Greys`, `Blues`.

---

# PHẦN E. DIỄN GIẢI KẾT QUẢ VÀ LƯU Ý

## 19. Tổng giá trị ước tính

Tổng giá trị thường được tính theo:

```text
Số lượng x Đơn giá
```

Nếu dòng dữ liệu thiếu số lượng hoặc đơn giá, tổng giá trị có thể thấp hơn thực tế.

## 20. Không so sánh giá nếu chưa kiểm tra quy cách

Cùng tên thuốc nhưng khác quy cách thì giá không thể so sánh trực tiếp.

Cần kiểm tra:

- Hàm lượng.
- Dạng bào chế.
- Đường dùng.
- Đơn vị tính.
- Quy cách đóng gói.
- Nước sản xuất.
- Nhà sản xuất.

## 21. Khi thấy giá bất thường cần làm gì?

Nếu một sản phẩm thường có giá 10.000 - 12.000 nhưng có một dòng 500.000, cần kiểm tra:

- Đơn vị tính.
- Quy cách đóng gói.
- Hàm lượng.
- Dạng bào chế.
- Số lượng.
- Mã gói thầu.
- Số quyết định.

## 22. Dự báo chỉ là tham khảo

Forecast giúp nhìn xu hướng nhưng không thay thế đánh giá chuyên môn. Cần kết hợp thêm:

- Kế hoạch đấu thầu thực tế.
- Chính sách mua sắm.
- Thay đổi danh mục thuốc.
- Tình hình tồn kho.
- Biến động giá nguyên liệu.
- Thay đổi quy định.

## 23. Khi nào nên xuất Excel?

Nên xuất Excel khi:

- Cần gửi báo cáo cho quản lý.
- Cần lưu kết quả theo từng công ty hoặc buyer.
- Cần làm Pivot Table.
- Cần kiểm tra dữ liệu gốc.
- Cần chia sẻ với nhóm kinh doanh hoặc phân tích.

---

# PHẦN F. QUY TRÌNH PHÂN TÍCH ĐỀ XUẤT

## 24. Quy trình phân tích một công ty

1. Mở module phân tích công ty.
2. Chọn dữ liệu trực tiếp.
3. Nhập tên công ty.
4. Chọn **Chỉ cơ sở sản xuất**.
5. Chọn **Đúng cụm từ / ranh giới từ**.
6. Đặt giới hạn tải bằng `0`.
7. Xem tổng quan.
8. Kiểm tra biến thể tên công ty.
9. Xem top sản phẩm.
10. Xem top người mua.
11. Kiểm tra xu hướng tháng.
12. Xem dự báo 6 hoặc 12 tháng.
13. Kiểm tra price outlier.
14. Xem tín hiệu chiến lược.
15. Xuất Excel.

## 25. Quy trình phân tích một người mua

1. Mở module phân tích người mua.
2. Chọn dữ liệu trực tiếp.
3. Nhập tên bệnh viện hoặc đơn vị mua.
4. Chọn **Chỉ bên mua**.
5. Chọn **Đúng cụm từ / ranh giới từ**.
6. Nếu cần chính xác tuyệt đối, chọn **Đúng toàn bộ giá trị trường**.
7. Đặt giới hạn tải bằng `0`.
8. Xem tổng quan.
9. Kiểm tra biến thể tên người mua.
10. Xem danh mục sản phẩm.
11. Xem top nhà sản xuất.
12. Xem ma trận nhà sản xuất x sản phẩm.
13. Kiểm tra xu hướng mua sắm.
14. Xem dự báo nhu cầu.
15. Kiểm tra biến động giá.
16. Xuất Excel.

## 26. Quy trình tra cứu nhanh một thuốc

1. Mở module tra cứu.
2. Chọn nguồn thuốc tân dược hoặc tất cả nguồn.
3. Nhập tên thuốc hoặc hoạt chất.
4. Chọn kiểu tìm kiếm phù hợp.
5. Sắp xếp theo giá hoặc ngày.
6. Xem bảng kết quả.
7. Tải Excel nếu cần.

---

# PHẦN G. CÂU HỎI THƯỜNG GẶP

## 27. Vì sao tìm một từ khóa lại ra nhiều kết quả không đúng?

Do từ khóa quá rộng hoặc kiểu tìm kiếm đang là tìm chứa chuỗi. Cách xử lý:

- Nhập tên đầy đủ hơn.
- Chọn đúng phạm vi: chỉ cơ sở sản xuất hoặc chỉ bên mua.
- Chọn đúng cụm từ / ranh giới từ.
- Chọn đúng toàn bộ giá trị trường nếu cần.

## 28. Vì sao Imexpharm bị lẫn Agimexpharm?

Vì tìm chứa chuỗi có thể xem `imexpharm` là một phần của `agimexpharm`. Cách xử lý:

```text
Kiểu khớp: Đúng cụm từ / ranh giới từ
```

hoặc:

```text
Kiểu khớp: Đúng toàn bộ giá trị trường
```

## 29. Vì sao tìm Bạch Mai ra Trạm Y tế hoặc Trường Mẫu giáo?

Vì từ khóa `Bạch Mai` là tên địa danh/khu vực, không chỉ riêng bệnh viện. Cách xử lý:

```text
Từ khóa: Bệnh viện Bạch Mai
Phạm vi lọc: Chỉ bên mua
Kiểu khớp: Đúng toàn bộ giá trị trường
```

## 30. Vì sao treemap không hiện?

Có thể dữ liệu đang chọn không có giá trị dương để vẽ, ví dụ thiếu đơn giá hoặc số lượng. Bảng dữ liệu vẫn có thể xem bình thường.

## 31. Vì sao dự báo không đáng tin khi dữ liệu ít?

Forecast cần dữ liệu lịch sử theo tháng. Nếu dữ liệu chỉ có vài tháng, kết quả dự báo chỉ nên dùng để tham khảo.

## 32. Vì sao tổng giá trị có thể khác giá trị hợp đồng chính thức?

Vì module ước tính từ số lượng và đơn giá trong dữ liệu hiện có. Một số dòng có thể thiếu thông tin hoặc có đơn vị/quy cách khác.

---

# PHẦN H. VÍ DỤ TỪ KHÓA NÊN DÙNG

## 33. Công ty sản xuất

```text
Traphaco
Dược Hậu Giang
DHG
Imexpharm
Pymepharco
Bidiphar
Agimexpharm
Domesco
Mekophar
OPC
Boston Pharma
```

## 34. Người mua / bệnh viện

```text
Bệnh viện Bạch Mai
Bệnh viện Chợ Rẫy
Bệnh viện Trung ương Huế
Bệnh viện Đại học Y Dược TP.HCM
Sở Y tế Hà Nội
Sở Y tế TP Hồ Chí Minh
Sở Y tế Đà Nẵng
Trung tâm mua sắm tập trung thuốc quốc gia
```

## 35. Hoạt chất / sản phẩm

```text
Esomeprazole
Paracetamol
Amoxicillin
Ceftriaxone
Metformin
Amlodipine
Atorvastatin
Omeprazole
Insulin
```

---

# PHẦN I. HOOK / QUOTE TEXT ĐĂNG FACEBOOK

## 36. Hook ngắn

1. Dữ liệu đấu thầu không chỉ để tra cứu - nếu biết phân tích, đó là bản đồ thị trường thuốc.
2. Một tên công ty có thể ẩn sau hàng nghìn dòng dữ liệu đấu thầu. Vấn đề là bạn có nhìn thấy xu hướng không.
3. Đừng chỉ hỏi thuốc trúng thầu ở đâu. Hãy hỏi: ai mua, mua bao nhiêu, giá biến động thế nào và xu hướng sắp tới ra sao.
4. Từ dữ liệu đấu thầu, có thể nhìn ra sản phẩm chủ lực, khách hàng chiến lược và cả rủi ro phụ thuộc thị trường.
5. Bệnh viện mua gì hôm nay có thể gợi ý nhu cầu thị trường trong những tháng tới.
6. Một dashboard tốt không chỉ hiển thị dữ liệu, mà giúp người dùng đặt câu hỏi tốt hơn.
7. Đấu thầu thuốc là nơi dữ liệu, chiến lược sản phẩm và cơ hội thị trường gặp nhau.
8. Khi dữ liệu đủ sâu, bảng Excel không còn là bảng Excel - nó trở thành công cụ ra quyết định.
9. Muốn hiểu thị trường thuốc, hãy bắt đầu từ câu hỏi: ai đang mua, mua của ai và giá đang đi về đâu.
10. Dữ liệu đấu thầu có thể rất khô, nhưng insight từ dữ liệu đó lại rất sống động.

## 37. Caption Facebook mẫu

### Caption 1

Dữ liệu đấu thầu thuốc không chỉ dùng để tìm kiếm một sản phẩm đã trúng thầu hay chưa.

Nếu phân tích đúng cách, dữ liệu này có thể cho thấy:

- Công ty nào đang tăng trưởng.
- Sản phẩm nào là nhóm chủ lực.
- Bệnh viện nào có nhu cầu mua sắm lớn.
- Nhà sản xuất nào đang chiếm ưu thế.
- Giá nào có dấu hiệu bất thường.
- Xu hướng mua sắm các tháng tới có thể ra sao.

Đó là lý do mình xây dựng các module phân tích đấu thầu theo hai hướng: theo công ty sản xuất và theo người mua/bệnh viện.

Dữ liệu tốt không chỉ trả lời câu hỏi. Dữ liệu tốt giúp chúng ta nhìn thấy cơ hội.

### Caption 2

Một từ khóa như “Imexpharm” nếu tìm không đúng có thể bị lẫn với “Agimexpharm”. Một từ khóa như “Bạch Mai” nếu tìm quá rộng có thể ra cả bệnh viện, trạm y tế và trường học.

Trong phân tích dữ liệu đấu thầu, tìm kiếm đúng là bước đầu tiên. Sau đó mới đến thống kê, biểu đồ, dự báo và insight chiến lược.

Module mới được thiết kế cho người dùng cuối: giao diện Việt/Anh, ẩn đường dẫn kỹ thuật, có khớp chính xác, có dự báo, có phân tích sản phẩm, buyer, nhà sản xuất, giá và bất thường.

Mục tiêu: biến dữ liệu đấu thầu thành công cụ hỗ trợ quyết định.

### Caption 3

Nếu bạn là người làm kinh doanh dược, market access, phân tích sản phẩm hoặc quản lý danh mục, dữ liệu đấu thầu có thể giúp trả lời nhiều câu hỏi:

- Bệnh viện nào mua nhiều nhất?
- Công ty nào đang có độ phủ tốt?
- Sản phẩm nào tạo giá trị lớn?
- Nhóm thuốc nào có nhu cầu tăng?
- Giá nào cần kiểm tra lại?
- 6 tháng tới xu hướng có thể đi theo hướng nào?

Khi dữ liệu được tổ chức đúng, insight không còn nằm rải rác trong hàng nghìn dòng Excel.

Insight nằm ngay trong dashboard.

## 38. Quote text ngắn để đặt trên ảnh

1. Từ dữ liệu đấu thầu đến insight thị trường.
2. Đọc dữ liệu đúng - thấy cơ hội sớm.
3. Đấu thầu thuốc: không chỉ là kết quả, mà là xu hướng.
4. Ai mua? Mua gì? Mua của ai? Giá ra sao?
5. Biến hàng nghìn dòng đấu thầu thành quyết định kinh doanh.
6. Dữ liệu tốt giúp thị trường bớt mơ hồ.
7. Phân tích đúng giúp nhìn thấy cơ hội trước người khác.
8. Dashboard không thay thế chuyên môn, nhưng làm chuyên môn sắc bén hơn.
9. Insight thị trường bắt đầu từ dữ liệu sạch.
10. Hiểu dữ liệu đấu thầu - hiểu chuyển động thị trường thuốc.

---

# PHẦN J. KẾT LUẬN

Bộ module phân tích đấu thầu thuốc giúp người dùng cuối đi từ tìm kiếm nhanh đến phân tích sâu:

- Module tra cứu giúp tìm dữ liệu theo từ khóa.
- Module công ty giúp đánh giá năng lực và xu hướng đấu thầu của nhà sản xuất.
- Module người mua giúp hiểu hành vi mua sắm của bệnh viện, Sở Y tế hoặc bên mời thầu.

Ba nguyên tắc quan trọng khi sử dụng:

1. Nhập từ khóa đủ cụ thể.
2. Chọn đúng phạm vi và kiểu khớp.
3. Kiểm tra biến thể tên, quy cách và dữ liệu gốc trước khi kết luận chính thức.

---

**PharmApp / PharmTender**  
Website thử nghiệm: www.pharmapp.dev  
Nội dung chính thức: www.nghiencuuthuoc.com

# HƯỚNG DẪN TRA CỨU KẾT QUẢ TRÚNG THẦU THEO CÔNG TY

## 1. Mục đích

Chức năng **Tra cứu kết quả đấu thầu thuốc** giúp người dùng tìm nhanh các mặt hàng thuốc đã trúng thầu theo:

* Tên công ty sản xuất hoặc cơ sở sản xuất
* Tên thuốc
* Hoạt chất
* Hàm lượng
* Dạng bào chế
* Đơn giá
* Số lượng
* Nguồn dữ liệu: thuốc tân dược, dược liệu, vị thuốc cổ truyền, thiết bị vật tư y tế, hàng hóa khác

Ví dụ: tra cứu các thuốc liên quan đến công ty **Stellapharm**.

---

## 2. Đăng nhập hệ thống

Người dùng có thể truy cập một trong hai địa chỉ sau:

* `https://pharmapp.dev`
* `https://pharmapp.vn`

### Các bước đăng nhập

1. Mở trình duyệt Chrome, Edge hoặc Firefox.
2. Nhập địa chỉ hệ thống:

   * `https://pharmapp.dev`
     hoặc
   * `https://pharmapp.vn`
3. Tại màn hình đăng nhập, nhập:

   * **Tên đăng nhập**
   * **Mật khẩu**
4. Nhấn **Đăng nhập**.
5. Sau khi đăng nhập thành công, hệ thống sẽ hiển thị giao diện PharmApp.
6. Nếu muốn thoát hệ thống, nhấn nút **Đăng xuất** ở thanh bên trái.

Lưu ý: tài khoản đăng nhập do quản trị viên cung cấp. Không chia sẻ tài khoản cho người khác.

---

## 3. Chọn workspace và chức năng tra cứu đấu thầu

Sau khi đăng nhập, ở thanh bên trái:

1. Tại mục **Workspace**, chọn **PharmApp**.
2. Trong danh sách workspace, chọn nhóm **Đấu Thầu Y Tế**.
3. Tại khu vực **Select Module** hoặc **Chức năng**, chọn một trong các module tra cứu đấu thầu, ví dụ:

   * **MSC Tender Search Export Excel**
   * **MSC Tender Search**
   * **MSC Tin Đấu Thầu**
   * **MSC Tender Deep Analytics**

Để tra cứu nhanh kết quả trúng thầu, nên dùng:

**MSC Tender Search Export Excel**

hoặc trang:

**Tra cứu kết quả đấu thầu thuốc**

---

## 4. Cách tra cứu công ty Stellapharm

Tại màn hình **Tra cứu kết quả đấu thầu thuốc**, thực hiện như sau:

### Bước 1: Chọn ngôn ngữ

Ở đầu trang, chọn:

* **VN** nếu muốn dùng tiếng Việt
* **EN** nếu muốn dùng tiếng Anh

Thông thường người dùng cuối nên chọn **VN**.

---

### Bước 2: Chọn chức năng

Tại mục **Chức năng**, chọn:

**Tìm kiếm**

---

### Bước 3: Chọn nguồn tìm kiếm

Tại mục **Nguồn tìm kiếm**, chọn nhóm dữ liệu phù hợp.

Nếu tra cứu thuốc thành phẩm, chọn:

**Thuốc tân dược**

Các lựa chọn khác gồm:

* **Dược liệu**
* **Vị thuốc cổ truyền**
* **Thiết bị, vật tư y tế**
* **Hàng hóa khác**
* **Tất cả nguồn**

Nếu chưa chắc dữ liệu thuộc nhóm nào, có thể chọn **Tất cả nguồn**.

---

### Bước 4: Nhập từ khóa công ty

Tại ô **Từ khóa**, nhập tên công ty hoặc một phần tên công ty.

Ví dụ:

```text
Stellapharm
```

Hoặc nhập ngắn hơn:

```text
Stella
```

Gợi ý:

* Nhập **Stellapharm** để tìm chính xác hơn.
* Nhập **Stella** để mở rộng kết quả, phòng trường hợp dữ liệu ghi tên công ty không đầy đủ hoặc có biến thể.

---

### Bước 5: Nhấn tìm kiếm

Sau khi nhập từ khóa, nhấn nút:

**Tìm kiếm**

Hoặc dùng tổ hợp phím nếu hệ thống hỗ trợ:

**Ctrl + Enter**

---

## 5. Xem kết quả tra cứu

Sau khi tìm kiếm, hệ thống hiển thị phần **Kết quả**.

Các thông tin tổng quan gồm:

* **Số kết quả**: số dòng dữ liệu tìm được
* **Giá thấp nhất**
* **Giá trung vị**
* **Giá cao nhất**
* **Từ khóa tìm kiếm**

Ví dụ khi tìm **Stellapharm**, hệ thống có thể hiển thị:

* Số kết quả: 300
* Giá thấp nhất: 330
* Giá trung vị: khoảng 2,100 hoặc 2,120
* Giá cao nhất: tùy dữ liệu tìm được

---

## 6. Cách đọc bảng kết quả

Bảng kết quả thường có các cột sau:

| Cột                    | Ý nghĩa                            |
| ---------------------- | ---------------------------------- |
| Nhóm dữ liệu           | Loại dữ liệu, ví dụ Thuốc tân dược |
| Tên thuốc              | Tên biệt dược hoặc tên sản phẩm    |
| Hoạt chất              | Thành phần hoạt chất               |
| Hàm lượng / tiêu chuẩn | Hàm lượng thuốc                    |
| Đường dùng             | Ví dụ uống, tiêm, dùng ngoài       |
| Dạng bào chế / mô tả   | Viên nén, viên nang, thuốc cốm...  |
| Đơn vị                 | Đơn vị tính, ví dụ viên, gói, lọ   |
| Số lượng               | Số lượng trúng thầu                |
| Đơn giá                | Giá trúng thầu                     |
| Cơ sở sản xuất         | Công ty/cơ sở sản xuất             |
| Nước sản xuất          | Quốc gia sản xuất                  |

Ví dụ trong kết quả có thể thấy các sản phẩm liên quan đến Stellapharm như:

* **Alumastad**
* **Metformin Stella 850mg**
* **Partamol Tab.**
* **Partamol 500 Cap**
* **Acyclovir Stella 800mg**
* **Pracetam 1200**

---

## 7. Cách lọc nâng cao

Nếu kết quả quá nhiều, mở mục:

**Bộ lọc tùy chọn**

Tùy theo phiên bản hệ thống, người dùng có thể lọc thêm theo:

* Tên thuốc
* Hoạt chất
* Đường dùng
* Dạng bào chế
* Giá thấp nhất / cao nhất
* Cơ sở sản xuất
* Nước sản xuất
* Nhóm dữ liệu

Sau khi chọn bộ lọc, nhấn lại **Tìm kiếm** để cập nhật kết quả.

---

## 8. Xuất dữ liệu ra Excel

Nếu đang dùng module **MSC Tender Search Export Excel**, sau khi có kết quả:

1. Kiểm tra lại từ khóa và bảng kết quả.
2. Tìm nút **Export Excel**, **Download Excel** hoặc **Tải Excel** nếu được hiển thị.
3. Nhấn nút tải để xuất dữ liệu.
4. Mở file Excel để phân tích thêm, lọc, sắp xếp hoặc lập báo cáo.

Nếu không thấy nút xuất Excel, có thể chuyển sang đúng module **MSC Tender Search Export Excel** ở thanh bên trái.

---

## 9. Khuyến nghị khi tìm theo tên công ty

Để kết quả đầy đủ hơn, nên thử nhiều biến thể từ khóa:

```text
Stellapharm
```

```text
Stella
```

```text
Công ty TNHH Liên doanh Stellapharm
```

```text
Stellapharm - Chi nhánh 1
```

Lý do: trong dữ liệu đấu thầu, tên công ty có thể được ghi theo nhiều cách khác nhau.

---

## 10. Lỗi thường gặp và cách xử lý

| Tình huống                 | Cách xử lý                                                      |
| -------------------------- | --------------------------------------------------------------- |
| Không có kết quả           | Thử nhập từ khóa ngắn hơn, ví dụ “Stella” thay vì “Stellapharm” |
| Kết quả quá nhiều          | Dùng bộ lọc tùy chọn để thu hẹp                                 |
| Không thấy module đấu thầu | Kiểm tra workspace đã chọn đúng **Đấu Thầu Y Tế** chưa          |
| Không đăng nhập được       | Kiểm tra tài khoản, mật khẩu hoặc liên hệ quản trị viên         |
| Trang tải chậm             | Chờ vài giây, làm mới trang hoặc kiểm tra kết nối internet      |
| Không xuất được Excel      | Chuyển sang module **MSC Tender Search Export Excel**           |

---

## 11. Quy trình nhanh

Tóm tắt thao tác:

1. Truy cập `https://pharmapp.dev` hoặc `https://pharmapp.vn`
2. Đăng nhập tài khoản
3. Chọn workspace **PharmApp**
4. Chọn nhóm **Đấu Thầu Y Tế**
5. Chọn module **MSC Tender Search Export Excel**
6. Chọn **Tìm kiếm**
7. Chọn nguồn **Thuốc tân dược**
8. Nhập từ khóa:

```text
Stellapharm
```

9. Nhấn **Tìm kiếm**
10. Xem bảng kết quả hoặc xuất Excel nếu cần

---

**PharmApp / PharmTender**
Dùng để tra cứu, phân tích và xuất dữ liệu kết quả trúng thầu thuốc phục vụ công tác nghiên cứu thị trường, tham khảo giá, phân tích sản phẩm và theo dõi hoạt động đấu thầu y tế.

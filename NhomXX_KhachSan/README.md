# NhomXX — Bài thực hành dữ liệu đặt phòng khách sạn

## 1. Thành viên và phân công

| Họ tên | MSSV | Phụ trách chính | Có thể giải thích thêm |
|---|---|---|---|
| *(bổ sung)* | *(bổ sung)* | Làm sạch dữ liệu | Phân tích và kiểm tra |
| *(bổ sung)* | *(bổ sung)* | Kiểm soát chất lượng | Làm sạch và truy vết |
| *(bổ sung)* | *(bổ sung)* | Phân tích và trực quan hóa | Insight và báo cáo |

## 2. Cách chạy lại

1. Giữ nguyên cấu trúc thư mục dự án.
2. Mở `hotel_analysis.ipynb` tại thư mục gốc và chọn **Restart & Run all**.
3. Notebook đọc `data/hotel_bookings_dirty.csv` và ghi các CSV, bảng, hình vào `outputs/`.
4. Kiểm tra cấu trúc đầu ra bằng:

   ```powershell
   python tools\kiem_tra_nop_bai.py .
   ```

Đã kiểm tra notebook chạy hết 104 cell và bộ kiểm tra tích hợp đạt 51/51 mục.

## 3. Môi trường và thư viện

| Thành phần | Phiên bản |
|---|---|
| Python | 3.12.16 |
| pandas | 3.1.1 |
| matplotlib | 3.11.2 |
| seaborn | Không dùng |
| Môi trường | Jupyter Notebook |

## 4. Nguồn dữ liệu

Antonio, N., de Almeida, A., & Nunes, L. (2019). *Hotel booking demand datasets*. Data in Brief, 22, 41–49. https://doi.org/10.1016/j.dib.2018.11.126 (CC BY 4.0). Bản dữ liệu thực hành `data/hotel_bookings_dirty.csv` gồm 10.325 dòng × 24 cột; dữ liệu gốc được giữ nguyên.

## 5. Quy tắc xử lý riêng và quyết định có truy vết

| # | Tình huống | Quy tắc nhóm chọn | Lý do | Ảnh hưởng đến kết quả |
|---|---|---|---|---|
| 1 | Xung đột khi gộp cùng `booking_id` | Với từng cột, lấy giá trị không thiếu từ dòng có `row_id` nhỏ nhất; ghi nhật ký riêng cho từng trường có xung đột. | Quy tắc xác định, lặp lại được, không tự suy đoán giá trị. | Có 7 nhóm xung đột `lead_time` và 8 nhóm xung đột `adr`; có thể ảnh hưởng riêng đến các phân tích tương ứng. |
| 2 | Bản ghi trùng 23 cột nghiệp vụ | Ghi nhận trước khi gộp; không xóa nguồn và giữ mọi `row_id` trong `row_lineage`. | Bảo toàn khả năng truy vết đủ 10.325 dòng đầu vào. | 180 dòng trùng tuyệt đối được quy về 10.000 booking duy nhất. |
| 3 | Ngày nằm trong `reservation_status` | Chỉ chuyển sang `reservation_status_date` nếu khớp `YYYY-MM-DD` và ô ngày trạng thái đang rỗng; trạng thái để thiếu. | Chỉ sửa khi có bằng chứng định dạng và không ghi đè. | 26 dòng được xử lý trước khi chuẩn hóa trạng thái. |
| 4 | Mâu thuẫn trạng thái | Khi `reservation_status` hợp lệ, tính lại `is_canceled` theo quy tắc Check-Out = 0, Canceled/No-Show = 1. | Trạng thái cuối là căn cứ được đề quy định. | 41 giá trị `is_canceled` được đồng bộ; tỷ lệ hủy dùng mẫu số có trạng thái đã biết. |
| 5 | ADR, thiếu và dữ liệu hiếm | Chuyển ký hiệu tiền và dấu phẩy thập phân; giữ `adr = 0`; giá sai/ngoài miền để thiếu, không điền trung bình. | Phân biệt dữ liệu thiếu, sai và giá trị hiếm hợp lệ. | ADR chỉ dùng cho đặt phòng không hủy có `adr > 0`; số 0 và thiếu được báo riêng. |

## 6. Tệp đầu ra

- [x] `hotel_analysis.ipynb` — notebook đã chạy từ đầu.
- [x] `Bao_cao_Khach_san.docx` — báo cáo theo khung.
- [x] `insights.md` — 6 insight có số liệu, mẫu số, so sánh, giới hạn và dẫn chiếu.
- [x] `data/hotel_bookings_dirty.csv` — dữ liệu gốc, không sửa.
- [x] `outputs/` — 5 tệp dữ liệu chính.
- [x] `outputs/tables/` — 14 bảng nguồn.
- [x] `outputs/figures/` — 8 hình PNG, 150 dpi.
- [x] `NhomXX_KhachSan.zip` — gói nộp dùng mã nhóm mẫu `XX`; đổi tên/thông tin nhóm trước khi nộp.
- [x] `hotel_student_starter_copy.ipynb` — bản notebook khung nguyên trạng để khôi phục, lưu ngoài ZIP ở thư mục dự án.

**Thông tin nhóm, thành viên và mã nhóm cần được bổ sung trước khi đóng gói nộp bài.**

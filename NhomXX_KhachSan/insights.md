# Sáu insight từ dữ liệu đặt phòng khách sạn

Các insight dưới đây được tính trên bảng một dòng mỗi `booking_id` đã làm sạch. Tỷ lệ hủy dùng số đặt phòng có `is_canceled` không thiếu làm mẫu số; không diễn giải mối liên hệ thành quan hệ nhân quả.

## Insight 1 — City Hotel có tỷ lệ hủy cao hơn Resort Hotel

- **Câu hỏi / chủ đề:** Câu 2 · Khách sạn và hủy phòng
- **Phát hiện chính:** Tỷ lệ hủy ở City Hotel cao hơn Resort Hotel 13,29 điểm phần trăm.
- **Số liệu, đơn vị và mẫu số:** City Hotel 2.801/6.702 (41,79%); Resort Hotel 940/3.298 (28,50%).
- **So sánh làm rõ phát hiện:** Chênh lệch 13,29 điểm phần trăm; City Hotel chiếm 67,02% số đặt phòng trong mẫu.
- **Ý nghĩa trong phạm vi dữ liệu:** Khác biệt mô tả hai khách sạn trong mẫu giai đoạn 2015–2017.
- **Giới hạn hoặc thông tin cần kiểm chứng:** Hai khách sạn khác loại hình/vị trí; dữ liệu không cho biết nguyên nhân hủy.
- **Bằng chứng:** Bảng `outputs/tables/q02_hotel_cancel.csv` · Hình `outputs/figures/fig01_hotel_cancel.png`

**Đoạn hoàn chỉnh (80–120 từ):**

> Trong mẫu 10.000 đặt phòng đã gộp, City Hotel có 2.801 lượt hủy trên 6.702 đặt phòng có trạng thái (41,79%), còn Resort Hotel có 940 trên 3.298 (28,50%); chênh lệch là 13,29 điểm phần trăm. City Hotel chiếm 67,02% tổng mẫu, nên số hủy tuyệt đối lớn hơn không tự nó phản ánh tỷ lệ cao hơn; so sánh tỷ lệ cho thấy khác biệt vẫn còn sau khi tính theo quy mô khách sạn. Kết quả mô tả hai khách sạn trong giai đoạn 2015–2017, không xác định nguyên nhân và không đại diện toàn ngành. (Bảng q02; Hình 1)

## Insight 2 — Tháng cao điểm khác nhau giữa hai khách sạn trong năm 2016

- **Câu hỏi / chủ đề:** Câu 3 · Mùa vụ
- **Phát hiện chính:** City Hotel đạt đỉnh đặt phòng tháng 10, còn Resort Hotel đạt đỉnh tháng 5.
- **Số liệu, đơn vị và mẫu số:** Năm 2016 có 12 tháng; City Hotel 360 đặt phòng tháng 10 và 117 tháng 1; Resort Hotel 162 tháng 5 và 62 tháng 1.
- **So sánh làm rõ phát hiện:** Số đặt phòng tháng đỉnh cao gấp khoảng 3,08 lần đáy ở City Hotel và 2,61 lần ở Resort Hotel.
- **Ý nghĩa trong phạm vi dữ liệu:** Mẫu cho thấy hai khách sạn có nhịp đặt phòng theo tháng khác nhau.
- **Giới hạn hoặc thông tin cần kiểm chứng:** Số đếm gồm cả đặt phòng hủy; chỉ năm 2016 đủ 12 tháng và không giải thích nguyên nhân mùa vụ.
- **Bằng chứng:** Bảng `outputs/tables/q03_monthly_arrivals_2016.csv` · Hình `outputs/figures/fig02_monthly_arrivals_2016.png`

**Đoạn hoàn chỉnh (80–120 từ):**

> Trong năm duy nhất có đủ 12 tháng, City Hotel ghi nhận 360 đặt phòng đến trong tháng 10, so với mức thấp nhất 117 vào tháng 1; Resort Hotel đạt đỉnh 162 vào tháng 5 và đáy 62 vào tháng 1. Mức tháng đỉnh cao gấp lần lượt khoảng 3,08 và 2,61 lần tháng đáy của từng khách sạn, gợi ý nhịp thời vụ khác nhau trong mẫu. Số đếm bao gồm đặt phòng đã hủy, nên không đại diện số lượt khách thực lưu trú. Tỷ lệ hủy theo tháng cũng dao động 22,35%–40,62%, nhưng dữ liệu không xác định nguyên nhân và không cho phép so tổng năm với các năm thiếu tháng. (Bảng q03; Hình 2)

## Insight 3 — Tỷ lệ hủy tăng theo nhóm lead time trong mẫu

- **Câu hỏi / chủ đề:** Câu 4 · Thời gian đặt trước
- **Phát hiện chính:** Nhóm đặt trước 181+ ngày có tỷ lệ hủy cao nhất; nhóm 0–7 ngày thấp nhất.
- **Số liệu, đơn vị và mẫu số:** 181+ ngày: 1.199/2.065 (58,06%); 0–7 ngày: 159/1.581 (10,06%).
- **So sánh làm rõ phát hiện:** Chênh lệch 48,00 điểm phần trăm.
- **Ý nghĩa trong phạm vi dữ liệu:** Có mối liên hệ quan sát giữa thời gian đặt trước và trạng thái hủy.
- **Giới hạn hoặc thông tin cần kiểm chứng:** Đây không phải bằng chứng rằng đặt sớm khiến khách hủy; có thể còn khác biệt về mùa, kênh và cơ cấu khách.
- **Bằng chứng:** Bảng `outputs/tables/q04_leadtime_stats.csv`, `outputs/tables/q04_leadtime_cancel.csv` · Hình `outputs/figures/fig03_leadtime_cancel.png`

**Đoạn hoàn chỉnh (80–120 từ):**

> Trong 9.969 đặt phòng có `lead_time` hợp lệ, nhóm đặt trước 181 ngày trở lên có 1.199 lượt hủy trên 2.065 đặt phòng (58,06%), trong khi nhóm 0–7 ngày có 159/1.581 (10,06%). Chênh lệch 48,00 điểm phần trăm là lớn trong mẫu và đi cùng xu hướng tỷ lệ tăng qua các nhóm lead time trung gian. Đây chỉ là mối liên hệ quan sát, không chứng minh đặt trước lâu khiến khách hủy; mùa đến, kênh bán hay cơ cấu khách có thể khác giữa các nhóm. `lead_time` tối đa hợp lệ là 800 ngày và các giá trị thiếu/sai đã bị loại riêng khỏi phép tính này. (Bảng q04; Hình 3)

## Insight 4 — Groups hủy nhiều hơn, dù Online TA chiếm tỷ trọng lớn nhất

- **Câu hỏi / chủ đề:** Câu 6 · Phân khúc thị trường
- **Phát hiện chính:** Online TA chiếm tỷ trọng lớn nhất; Groups có tỷ lệ hủy cao nhất trong các phân khúc.
- **Số liệu, đơn vị và mẫu số:** Online TA: 4.741/9.997 (47,42%); Groups: 1.054/1.703 lượt hủy (61,89%).
- **So sánh làm rõ phát hiện:** Tỷ lệ hủy của Groups cao hơn Online TA (36,98%) 24,91 điểm phần trăm.
- **Ý nghĩa trong phạm vi dữ liệu:** Quy mô phân khúc và tỷ lệ hủy không xếp hạng giống nhau.
- **Giới hạn hoặc thông tin cần kiểm chứng:** Aviation chỉ có 21 đặt phòng, nên tỷ lệ nhóm nhỏ kém ổn định; dữ liệu không chứng minh phân khúc gây hủy.
- **Bằng chứng:** Bảng `outputs/tables/q06_segment_cancel.csv` · Hình `outputs/figures/fig05_segment_cancel.png`

**Đoạn hoàn chỉnh (80–120 từ):**

> Trong 9.997 đặt phòng có phân khúc, Online TA lớn nhất với 4.741 đặt phòng (47,42%); tuy vậy, phân khúc có tỷ lệ hủy cao nhất là Groups: 1.054/1.703 (61,89%), cao hơn Online TA (1.753/4.741; 36,98%) 24,91 điểm phần trăm. Như vậy, phân khúc đóng góp nhiều đặt phòng nhất không đồng nghĩa có mức hủy cao nhất. Aviation chỉ có 21 đặt phòng, nên tỷ lệ 23,81% của nhóm này kém ổn định và cần thận trọng khi so sánh. Dữ liệu mô tả sự khác biệt trong mẫu, không chỉ ra việc thuộc phân khúc nào gây ra hủy phòng. (Bảng q06; Hình 5)

## Insight 5 — Non Refund gắn với tỷ trọng trạng thái Canceled rất cao

- **Câu hỏi / chủ đề:** Câu 7 · Loại đặt cọc và trạng thái
- **Phát hiện chính:** Ở nhóm Non Refund, 98,81% đặt phòng có trạng thái Canceled.
- **Số liệu, đơn vị và mẫu số:** Non Refund: 1.259 đặt phòng, trong đó 98,81% Canceled; No Deposit: 8.728 đặt phòng, 27,23% Canceled.
- **So sánh làm rõ phát hiện:** Chênh lệch 71,58 điểm phần trăm giữa hai nhóm.
- **Ý nghĩa trong phạm vi dữ liệu:** Hai nhóm có phân bố trạng thái rất khác nhau.
- **Giới hạn hoặc thông tin cần kiểm chứng:** Không kết luận đặt cọc làm khách hủy; Refundable chỉ có 13 đặt phòng; cần kiểm tra cách ghi nhận/chính sách và cơ cấu khách.
- **Bằng chứng:** Bảng `outputs/tables/q07_deposit_cancel.csv` · Hình `outputs/figures/fig06_deposit_cancel.png`

**Đoạn hoàn chỉnh (80–120 từ):**

> Trong 1.259 đặt phòng thuộc Non Refund, 98,81% được ghi trạng thái Canceled, trong khi tỷ lệ tương ứng ở No Deposit là 27,23% trên 8.728 đặt phòng, chênh 71,58 điểm phần trăm. Đây là khác biệt mô tả giữa hai nhóm, nhưng không thể diễn giải rằng đặt cọc khiến khách hủy: nhãn có thể phản ánh quy trình ghi nhận hoặc nhóm khách có đặc điểm khác. Refundable chỉ có 13 đặt phòng nên tỷ lệ của nhóm này rất kém ổn định. Trạng thái thiếu được trình bày là Unknown nhưng vẫn nằm trong mẫu số từng loại đặt cọc. Cần dữ liệu chính sách và giao dịch để kiểm chứng thêm. (Bảng q07; Hình 6)

## Insight 6 — Resort Hotel đổi loại phòng thường xuyên hơn trong nhóm Check-Out

- **Câu hỏi / chủ đề:** Câu 10 · Đổi loại phòng
- **Phát hiện chính:** Tỷ lệ đổi phòng của Resort Hotel cao hơn City Hotel 10,38 điểm phần trăm.
- **Số liệu, đơn vị và mẫu số:** Resort: 583/2.351 (24,80%); City: 561/3.891 (14,42%).
- **So sánh làm rõ phát hiện:** Chênh lệch 10,38 điểm phần trăm trong các đặt phòng Check-Out đủ cả hai mã phòng.
- **Ý nghĩa trong phạm vi dữ liệu:** Tần suất khác nhau giữa hai khách sạn trong mẫu.
- **Giới hạn hoặc thông tin cần kiểm chứng:** Không có lý do đổi phòng; mẫu số loại bỏ Check-Out thiếu một trong hai mã phòng.
- **Bằng chứng:** Bảng `outputs/tables/q10_room_change_by_hotel.csv` · Bảng `outputs/tables/q10_room_change_by_reserved_type.csv`

**Đoạn hoàn chỉnh (80–120 từ):**

> Trong các đặt phòng Check-Out có đủ cả mã phòng đã đặt và được xếp, Resort Hotel ghi nhận 583 trường hợp đổi phòng trên 2.351 đặt phòng (24,80%), so với 561/3.891 (14,42%) ở City Hotel; chênh lệch là 10,38 điểm phần trăm. Resort có tỷ lệ cao hơn dù số mẫu nhỏ hơn, nhưng số đếm và tỷ lệ chỉ áp dụng cho các trường hợp đủ thông tin phòng. Bảng dữ liệu không nêu lý do đổi—có thể do vận hành, nâng hạng hoặc yêu cầu khách—nên không thể chọn một cách giải thích. Chênh lệch không đại diện cho khách sạn ngoài hai cơ sở trong mẫu. (Bảng q10 theo khách sạn và loại phòng)

## Tự kiểm tra

- Sáu insight thuộc ít nhất sáu chủ đề; mỗi đoạn nằm trong khoảng 80–120 từ.
- Mọi tỷ lệ đều nêu số lượng/mẫu số hoặc điều kiện lọc.
- Không suy diễn nhân quả, không gọi ADR hay `revenue_est` là doanh thu thực.

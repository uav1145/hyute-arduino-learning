# BÁO CÁO KIỂM ĐỊNH THUẬT NGỮ — HYUTE ARDUINO v1.3

Ngày: 19-11-2026. Đối tượng: 23 trang HTML của bộ v1.2 (trang chủ, Bài 0, Bài 1–20 và bài luyện 10 đề).

## Phạm vi và phương pháp
- Trích xuất và đọc nội dung văn bản hiển thị, tiêu đề, bảng, câu hỏi và các mục thông tin trong HTML, bao gồm dữ liệu JS của bài luyện thi.
- Đối chiếu các khái niệm phụ thuộc bo mạch với Arduino Language Reference, tài liệu UNO R3 và tài liệu thư viện chính thức; giữ nguyên tên API và tên model.
- So sánh biến thể thuật ngữ, phân biệt tín hiệu điện–thuật toán–hành vi thiết bị, chuẩn hóa diễn đạt theo tiếng Việt kỹ thuật.
- Không sửa nội dung 10 tệp đề thi Word gốc; bài luyện Tinkercad là sản phẩm chuyển thể cho học tập.
- Không thay các số liệu, công thức, chân mạch hay chương trình chỉ dựa trên nghi vấn thuật ngữ. Chúng vẫn cần kiểm chứng độc lập khi triển khai thực hành.

## Tổng hợp lỗi theo mức độ
### CRITICAL — 0 nhóm vấn đề
Không phát hiện lỗi thuật ngữ ở mức này trong phạm vi rà soát; đây không phải kết luận toàn bộ nội dung kỹ thuật đều đã kiểm chứng.

### MAJOR — 3 nhóm vấn đề
| Vị trí | Hiện trạng | Quyết định hiệu chỉnh |
|---|---|---|
| Bài 12 | “Đa nhiệm không chặn” có thể bị hiểu là nhiều luồng song song | Giải thích rõ lập lịch hợp tác trên vòng loop(), không có đa luồng; tên bài giữ nguyên |
| Bài 16 | “Tải giả”/“quạt giả lập” dễ bị hiểu là xác nhận tải vật lý đã chạy | Đổi thành LED mô phỏng lệnh điều khiển tải; phân biệt tín hiệu lệnh và tín hiệu phản hồi |
| Bài 17 | “Lỗi cảm biến” bị suy diễn từ ADC ngoài miền | Gọi đúng dữ liệu ngoài miền hợp lệ; yêu cầu chẩn đoán trước khi kết luận nguyên nhân |

### MODERATE — 11 nhóm vấn đề
| Vị trí | Hiện trạng | Quyết định hiệu chỉnh |
|---|---|---|
| Bài 0 | Các thành phần được gọi chung là “lệnh Arduino” | Sửa tên bảng tra cứu và giải thích hàm/cấu trúc/kiểu/hằng |
| Bài 5 | Chân số (digital I/O) | Chân vào/ra số |
| Bài 7 | Ngõ ra/đầu ra lẫn nhau; IPO viết bằng tiếng Anh | Thống nhất đầu ra; giải thích Đầu vào–Xử lý–Đầu ra (Input–Process–Output) |
| Bài 8 | “Mức tốc độ” khi chỉ điều chỉnh PWM | Làm rõ mức lệnh điều khiển PWM không phải tốc độ quay đo được |
| Bài 9 | LCD được gọi bao quát như giao diện người–máy | Diễn đạt là màn hình hiển thị/giao tiếp người dùng, tránh đồng nhất với HMI công nghiệp |
| Bài 10 | “Hàm thuần dữ liệu” thiếu định nghĩa rõ | Phân biệt hàm xử lý ít phụ thuộc phần cứng với pure function |
| Bài 11 | “Lọc trung bình” chưa nêu phương pháp | Đổi sang lọc trung bình trượt |
| Bài 13 | “Dội phím” cho tiếp điểm nút nhấn | Đổi thành dội tiếp điểm nút nhấn |
| Bài 14, 19 | Hysteresis có thể bị nhầm với trễ thời gian | Định nghĩa dải trễ đóng–cắt và ranh giới 2 ngưỡng |
| Bài 18 | Giao thức Serial và thuật ngữ newline | Làm rõ giao thức bản tin qua Serial, ký tự LF và bộ đệm ký tự |
| Bài luyện 10 đề | Tên gọi từ đề gốc và phương án Tinkercad thay linh kiện | Giữ nội dung mục tiêu, bổ sung chú giải thuật ngữ và giới hạn tương đương |

### MINOR — 3 nhóm vấn đề
| Vị trí | Hiện trạng | Quyết định hiệu chỉnh |
|---|---|---|
| Bài 17, 20 | Test pass/bảng test trộn tiếng Anh | Dùng ca kiểm thử đạt/bảng kiểm thử |
| Bài 0 | Mô tả setup(), loop(), delay(), volatile() còn thiếu ranh giới | Bổ sung phạm vi, giới hạn và tính nguyên tử |
| Toàn bộ khóa học | Chưa có glossary dùng chung | Thêm trang thuat_ngu.html và liên kết từ các bài |

## Nguyên tắc thuật ngữ thống nhất

- Dùng **đầu vào/đầu ra** trong văn bản. Có thể gặp ngõ vào/ngõ ra khi trích nguyên văn datasheet.
- Dùng **dội tiếp điểm** và **chống dội nút nhấn**; “chống rung” trong tên đề gốc được giải thích như cách gọi cũ.
- Dùng **dải trễ đóng–cắt (hysteresis)**, không gọi là trễ thời gian.
- Dùng **mức lệnh PWM/tốc độ đặt**, không gọi là tốc độ quay đo được nếu không có cảm biến tốc độ.
- Dùng **mã ADC**, phân biệt mã số, điện áp cảm biến, điện áp tham chiếu và đại lượng vật lý được suy ra.
- Dùng **ca kiểm thử** và **kết quả dự kiến/kết quả quan sát** để phân biệt kiểm thử với quan sát cảm tính.
- **Arduino UNO R3** phải được nêu là phạm vi cho các khẳng định 10 bit ADC, PWM 8 bit, chân D2/D3 ngắt ngoài; không suy rộng mọi Arduino.
- **Chương trình Arduino** (sketch) dùng C++/API Arduino, không đồng nhất với ngôn ngữ C thuần.
- **Tinkercad** dùng cho thực hành mô phỏng mạch; mô phỏng logic của website không phải trình giả lập phần cứng.

## Thao tác hiệu chỉnh thực tế
- `bai_00_thuat_toan_ma_gia_luu_do_tra_cuu.html`: Đặt đúng phạm vi bảng tham chiếu (1 vị trí).
- `bai_00_thuat_toan_ma_gia_luu_do_tra_cuu.html`: Phân biệt loop() và cấu trúc lặp (1 vị trí).
- `bai_00_thuat_toan_ma_gia_luu_do_tra_cuu.html`: Chuẩn hóa sketch và reset (1 vị trí).
- `bai_00_thuat_toan_ma_gia_luu_do_tra_cuu.html`: Giải thích delay() chính xác (1 vị trí).
- `bai_00_thuat_toan_ma_gia_luu_do_tra_cuu.html`: Làm rõ volatile (1 vị trí).
- `bai_00_thuat_toan_ma_gia_luu_do_tra_cuu.html`: Phân biệt Serial và tốc độ (1 vị trí).
- `bai_05.html`: Tên chân digital I/O (1 vị trí).
- `bai_07.html`: Thống nhất ngõ ra/đầu ra (1 vị trí).
- `bai_07.html`: Mô tả đặc tính cảm biến (1 vị trí).
- `bai_07.html`: Thống nhất đầu ra trong bảng kết nối (1 vị trí).
- `bai_07.html`: Thống nhất đầu ra trong câu hỏi và mô phỏng (2 vị trí).
- `bai_07.html`: Chuẩn hóa mô hình IPO (1 vị trí).
- `bai_08.html`: Không đồng nhất lệnh PWM với tốc độ đo (1 vị trí).
- `bai_08.html`: Thuật ngữ tốc độ/PWM (1 vị trí).
- `bai_08.html`: Tên khối điều khiển (1 vị trí).
- `bai_08.html`: Nhãn điều khiển (1 vị trí).
- `bai_08.html`: Giá trị đặt PWM trong kiểm thử (1 vị trí).
- `bai_09.html`: Không đồng nhất LCD với HMI công nghiệp (1 vị trí).
- `bai_09.html`: Làm rõ hai phía của Serial (1 vị trí).
- `bai_10.html`: Phân biệt hàm xử lý dữ liệu với pure function (1 vị trí).
- `bai_11.html`: Nêu đúng dạng bộ lọc và đặc tính (1 vị trí).
- `bai_12.html`: Giới hạn đa nhiệm hợp tác (1 vị trí).
- `bai_13.html`: Chuẩn hóa hiện tượng debounce (2 vị trí).
- `bai_13.html`: Tên thuật toán chống dội (1 vị trí).
- `bai_14.html`: Làm rõ hysteresis (1 vị trí).
- `bai_14.html`: Phân biệt hysteresis với time delay (1 vị trí).
- `bai_15.html`: Không suy diễn lỗi phần cứng từ dữ liệu ngoài miền (1 vị trí).
- `bai_16.html`: Tải mô phỏng (2 vị trí).
- `bai_16.html`: Tín hiệu lệnh, không phải trạng thái vật lý (1 vị trí).
- `bai_16.html`: Nhãn tải mô phỏng (1 vị trí).
- `bai_16.html`: Thống nhất tải mô phỏng ở vận dụng (1 vị trí).
- `bai_16.html`: Phân biệt lệnh và phản hồi (1 vị trí).
- `bai_17.html`: Tránh kết luận nguyên nhân cảm biến thiếu căn cứ (2 vị trí).
- `bai_17.html`: Bỏ khẩu ngữ tiếng Anh (1 vị trí).
- `bai_17.html`: Thuật ngữ bảng kiểm thử (1 vị trí).
- `bai_17.html`: Thuật ngữ kết quả kiểm thử (1 vị trí).
- `bai_17.html`: Chẩn đoán lỗi theo bằng chứng (1 vị trí).
- `bai_18.html`: Phân biệt giao thức và giao diện Serial (2 vị trí).
- `bai_18.html`: Giải thích bộ đệm và ký tự kết thúc (1 vị trí).
- `bai_18.html`: Việt hóa newline (1 vị trí).
- `bai_19.html`: Hysteresis trong mục tiêu (2 vị trí).
- `bai_19.html`: Hysteresis trong mô tả (1 vị trí).
- `bai_20.html`: Phân biệt chỉ thị với tải (1 vị trí).
- `bai_20.html`: Chuẩn hóa test (2 vị trí).
- `bai_20.html`: Diễn đạt sư phạm (1 vị trí).
- `bai_21_on_thi.html`: Công bố ranh giới tương đương (1 vị trí).
- `bai_21_on_thi.html`: Giới hạn mô phỏng logic (1 vị trí).
- `bai_12.html`: Chú giải không chặn và RTC (1 vị trí).
- `bai_21_on_thi.html`: Phân biệt thuật ngữ đề gốc (1 vị trí).

- Đã tạo bảng tra cứu riêng gồm **59 thuật ngữ** và liên kết từ tất cả 22 bài học và trang chủ.

## Những điểm chưa được nghiệm thu
- Chưa thực thi mọi chương trình và 10 mạch luyện đề trực tiếp trong Tinkercad; kiểm tra HTML/JS không phải kiểm chứng mạch.
- Chưa xác minh mã màu xanh lá–vàng là bảng mã HEX chính thức từ bộ nhận diện HYUTE.
- Những ngưỡng cảm biến và chính sách điều khiển trong bài tập là giả thiết sư phạm, không phải giá trị định mức áp dụng công nghiệp.
- Nội dung không thay thế yêu cầu an toàn của thiết bị lạnh hoặc thiết bị điện ô tô thật.

## Nguồn xác minh
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)
- [Arduino UNO R3](https://docs.arduino.cc/hardware/uno-rev3/)
- [Arduino INPUT_PULLUP](https://docs.arduino.cc/language-reference/en/variables/constants/inputOutputPullup/)
- [Arduino attachInterrupt()](https://docs.arduino.cc/language-reference/en/functions/external-interrupts/attachInterrupt)
- [Arduino LiquidCrystal](https://docs.arduino.cc/libraries/liquidcrystal/)

## Trạng thái
**Đã chuẩn hóa thuật ngữ để giảng viên nghiệm thu bản v1.3. Chưa công bố READY FOR PUBLICATION do chưa hoàn thành kiểm chứng mọi mạch Tinkercad.**
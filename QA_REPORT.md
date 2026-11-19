# HYUTE Arduino Learning — Báo cáo kiểm định bản phát hành v1.0

## Phạm vi
- Gồm 5 module, 20 bài HTML liên kết từ trang chủ `index.html`.
- Bài 1–9 là các phiên bản trong hội thoại, giữ nội dung cũ và thêm thanh điều hướng về trang chủ/bài liền kề. Bài 5 lấy v1.4 không có sơ đồ điện tự vẽ.
- Bài 10–20 được biên soạn mới, mỗi bài 12 mục: mục tiêu, tình huống, kiến thức, thuật toán, tự thiết kế mạch, dự đoán, mã nguồn, Tinkercad, kiểm thử, quiz, rubric, nguồn.

## Kết quả kiểm tra tự động
1. 21 tệp HTML (1 trang chủ + 20 bài): kiểm tra cú pháp JavaScript; không có ID trùng trong từng trang; không có đường dẫn nội bộ trỏ tới tệp không tồn tại — PASS.
2. 11 tệp HTML mới (10–20): đủ 12 mục/bài, mỗi bài có 4 câu hỏi trắc nghiệm A/B/C/D, có phản hồi theo từng phương án — PASS.
3. 11 mã Arduino C++ được biên dịch kiểm tra cú pháp với g++ -std=c++11 và tệp khai báo mô phỏng các hàm Arduino — PASS. Kết quả này KHÔNG thay thế biên dịch bằng Arduino AVR core/Arduino IDE.
4. 11 mô hình trang DOM mô phỏng: tạo quiz, chọn đáp án đúng và chấm 4/4, mở tình huống — PASS.
5. Trang chủ DOM mô phỏng: đúng 5 module, 20 liên kết bài, cấu trúc bộ lọc — PASS.
6. Bài 18: chống giải mã nhầm dữ liệu sau khi tràn bộ đệm Serial đã được bổ sung và kiểm tra cú pháp — PASS.

## Hạn chế nghiệm thu
- Trình duyệt thực trong môi trường kiểm thử chặn điều hướng file:// và localhost; chưa xác nhận toàn bộ tương tác bằng Chrome/Edge thực qua trình duyệt tự động.
- Chưa chạy trực tiếp 11 mạch Tinkercad hoặc thực nghiệm trên Arduino UNO R3 thật.
- Các thông số ngưỡng và dải tín hiệu trong bài điều khiển là thông số GIẢ ĐỊNH phục vụ học tập, không phải đặc tính an toàn của hệ thống lạnh/ô tô thật.
- Các bài 1–9 giữ nguyên trạng thái nghiệm thu từ các phiên bản trước; chúng chưa được kiểm chứng lại bằng mạch Tinkercad trong đợt đóng gói này.
- Tiến độ localStorage là trên từng thiết bị/trình duyệt; chưa có tài khoản, xác thực, đồng bộ hoặc LMS.
- Cần giảng viên thử nghiệm trên Chrome/Edge và Tinkercad trước khi công bố rộng rãi ở mức READY FOR TEACHING.

## Triển khai
- Giải nén toàn bộ ZIP, giữ nguyên thư mục `assets` và `lessons`.
- Mở `index.html` hoặc đưa tất cả file vào một thư mục của máy chủ web tĩnh.
- Không trích riêng một file HTML từ 11 bài mới vì dùng CSS/JS dùng chung.
- Cần Internet và tài khoản có quyền sử dụng Tinkercad để thực hành mạch.


## BỔ SUNG V1.1 — BÀI 21: LUYỆN 10 ĐỀ THỰC HÀNH TRÊN TINKERCAD

**Phạm vi:** Một bài bổ sung, gồm 10 đề (nguồn De01…De10 do giảng viên cung cấp); không thay đổi tên hoặc thứ tự 20 bài chính.

**Quy định giao diện:** Xanh lá-vàng HYUTE; không có hình sơ đồ mạch điện AI vẽ; sinh viên tự lắp mạch trong Tinkercad. Không đính kèm tài liệu Word hoặc lời giải.

**Điều chỉnh so với đề nguồn:** Phiên bản ôn luyện không yêu cầu xuất .hex và không dùng phần mềm mô phỏng khác Tinkercad. Về linh kiện: Đề 2 có thể bỏ tầng đệm ULN2803A nếu dùng LED dòng nhỏ với điện trở hạn dòng và kiểm chứng tải của 74HC595; Đề 4 có phương án bốn chữ số 7 đoạn rời, KHÔNG kiểm tra giao thức TM1637; Đề 7 có thể dùng LCD song song 4 bit khi LCD I2C không tương thích thư viện; Đề 8 dùng L293D tương đương chức năng logic điều khiển, KHÔNG tương đương thông số điện L298N. Mọi điều chỉnh được công khai trong bài.

**Kiểm định hoàn thành:**
- 22 trang HTML (1 index + 20 bài gốc + 1 bài bổ sung): kiểm tra đường dẫn nội bộ và sự trùng lặp ID — PASS.
- Trang chủ: hiển thị 5 module + 1 khu bài bổ sung; liên kết Bài 21; tìm kiếm có thể lọc bài bổ sung — PASS.
- Bài 21: 10 mục đề, 10 mô phỏng logic và 20 câu hỏi trắc nghiệm — kiểm thử bằng Chromium Playwright `page.set_content` — PASS.
- Câu hỏi: 20 câu đã kiểm tra điểm 2/2 với đáp án cấu hình đúng; câu sai trả về phản hồi — PASS.
- Các thao tác mô phỏng chính từng đề: xem kết quả, điều chỉnh dữ liệu, trạng thái, chuyển bước, các mốc 9999→0000, 74HC595 AA/55, ADC quá ngưỡng — PASS trong bài học (không phải Tinkercad).
- JavaScript: Node.js --check đối với trang chủ và Bài 21 — PASS.
- Giao diện: ảnh chụp desktop và mobile trong Chromium Playwright — quan sát được.

**Giới hạn và điều kiện phát hành:**
- Công cụ điều hướng Chromium trong môi trường thử nghiệm chặn truy cập file:// và localhost; UI được thử qua `page.set_content`, chưa nghiệm thu đầy đủ đường đi bằng URL trình duyệt thực.
- Chưa thực hiện đăng nhập và chạy đủ 10 mạch trên chính Tinkercad. Chưa xác nhận model phần cứng của mọi phiên bản tài khoản, trong đó có giao tiếp với TM1637, L298N, LCD I2C.
- Bản cập nhật là RELEASE CANDIDATE cho thử nghiệm lớp học; cần thực nghiệm Tinkercad tối thiểu với những đề có thay thế phần tử và xác nhận thuật toán thực thi đúng trước phát hành rộng rãi.


## PHIÊN BẢN 1.2 — Bài 0 (19/11/2026)

- Bổ sung `lessons/bai_00_thuat_toan_ma_gia_luu_do_tra_cuu.html` trước Module 1; không đổi tên hoặc số thứ tự 20 bài chính và bài ôn 10 đề.
- Trang chủ: nút bắt đầu mở Bài 0; mục giới thiệu riêng có tìm kiếm và đánh dấu hoàn thành. Bài 1 có đường dẫn về Bài 0.
- Kiểm định tĩnh toàn bộ 23 trang HTML: PASS (không có liên kết nội bộ thiếu, ID trùng, lỗi cú pháp JavaScript trong tập kiểm).
- Kiểm thử bằng Chromium qua page.set_content: PASS đối với trang chủ, tra cứu 40+ mục, lọc, lần vết thuật toán T=30/31, sắp xếp thuật toán, ghép mã giả/C++, bảng kiểm thử ngưỡng, trắc nghiệm (7/7), hiển thị trên viewport di động. Không phát hiện JavaScript pageerror.
- Chương trình Arduino của Bài 0: PASS kiểm tra cú pháp C++ với API stub UNO R3 và g++ -std=c++11 -Wall -Wextra -Werror -fsyntax-only. Đây không phải biên dịch bằng Arduino core chính thức.
- Lưu đồ đã rà soát logic nhánh ĐÚNG/SAI và đường nhập luồng rồi quay lại vòng lặp.
- Không phát hành sơ đồ nguyên lý hay sơ đồ đấu dây do AI vẽ; SVG trong Bài 0 là lưu đồ thuật toán, không phải sơ đồ điện.
- Hạn chế: chưa chạy chương trình trên Tinkercad; chưa thử nghiệm người học thật; thao tác mở file trực tiếp bằng trình duyệt tự động bị chặn bởi chính sách môi trường, nên thử qua set_content.
- Không khẳng định đã nghiệm thu Tinkercad cho bộ 20 bài và 10 đề.

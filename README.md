# Cảm biến độ ẩm nhiệt độ MKE-S14 DHT11 Temperature Humidity Sensor

MKE-S14 DHT11 Temperature Humidity Sensor là cảm biến đo nhiệt độ và độ ẩm không khí sử dụng giao tiếp Digital 1-Wire, chỉ cần một chân tín hiệu để truyền dữ liệu, giúp việc kết nối với vi điều khiển trở nên đơn giản và thuận tiện. Cảm biến tích hợp phần tử đo nhiệt độ và độ ẩm cùng bộ xử lý tín hiệu bên trong, cho phép xuất dữ liệu đã được hiệu chuẩn dưới dạng số, giúp hệ thống đọc và xử lý nhanh chóng với độ ổn định cao.

**Lưu ý:** Cảm biến chỉ nên sử dụng trong môi trường đo độ ẩm không khí thông thường (hơi nước). Không nên sử dụng trong các môi trường ủ kín hoặc có nhiều vi khuẩn, nấm mốc (như ủ tỏi đen, ủ yếm khí, môi trường hữu cơ đậm đặc), vì các tác nhân này có thể bám lên bề mặt cảm biến và làm giảm độ chính xác hoặc gây hư hỏng cảm biến theo thời gian.

Sản phẩm phù hợp cho nhiều ứng dụng như đo nhiệt độ – độ ẩm môi trường, vườn thông minh, hệ thống giám sát không khí, thiết bị IoT và các dự án STEM. Mạch được thiết kế tối ưu về độ ổn định tín hiệu và khả năng chống nhiễu, đảm bảo hoạt động tin cậy trong cả môi trường học tập và ứng dụng thực tế.

Cảm biến độ ẩm nhiệt độ MKE-S14 DHT11 Temperature Humidity Sensor hỗ trợ điện áp giao tiếp 3.3V và 5VDC, cho phép kết nối trực tiếp và an toàn với các bo mạch điều khiển phổ biến như Arduino, Raspberry Pi, Jetson Nano, Micro:bit và nhiều nền tảng khác. Sản phẩm đi kèm cáp kết nối 4P XH2.54 – Dupont, đảm bảo kết nối chắc chắn, ổn định và thuận tiện trong quá trình lắp đặt và sử dụng.

## Thông số kỹ thuật
- Điện áp cấp nguồn: 5VDC
- Chuẩn tín hiệu điều khiển: Digital 1-Wire
- Điện áp giao tiếp: TTL 3.3 / 5VDC
- Cảm biến sử dụng: DHT11
- Dòng sử dụng: 2.5mA max (khi truyền dữ liệu).
- Khoảng đo độ ẩm: 20 - 90% RH (sai số 5% RH)
- Khoảng đo nhiệt độ: 0-50°C (sai số 2°C).
- Tần số lấy mẫu tối đa: 1Hz (1 giây 1 lần)
- Khả năng tương thích:
  - Arduino
  - Raspberry Pi
  - Jetson Nano
  - Micro:bit
  - Và các board điều khiển 3.3/5VDC khác
- Thiết kế mạch:
  - Ổn định, chống nhiễu
  - Phù hợp cho ứng dụng học tập và thực tế
- Đi kèm cáp kết nối: 3P XH2.54–Dupont

## Các chân tín hiệu
<table><thead>
  <tr>
    <th>MKE-S14</th>
    <th>Ghi chú</th>
  </tr></thead>
<tbody>
  <tr>
    <td>GND</td>
    <td>Chân cấp nguồn âm 0VDC</td>
  </tr>
  <tr>
    <td>5V</td>
    <td>Chân cấp nguồn dương 5VDC</td>
  </tr>
  <tr>
    <td>SIG</td>
    <td>Chân tín hiệu Digital</td>
  </tr>
</tbody>
</table>

## Hướng dẫn sử dụng
### Hướng dẫn kết nối
- Cấp nguồn 5VDC cho mạch qua hai chân GND và 5V.
- Kết nối chân SIG của cảm biến với chân điều khiển được khai báo trong chương trình.
### Hướng dẫn sử dụng với Arduino Uno / Vietduino Uno / ESP32
- Trong **Tools / Library Manager**, tìm và cài đặt bộ thư viện tổng hợp **"MKE_ONE" by MakerEdu.vn**
- Mở chương trình mẫu **"MKE_S14_DHT11_Serial_XXX"** tại **File / Examples / MAKEREDU / Module / MKE_S14_DHT11**
- Cấu hình board mạch tương ứng là **Arduino Uno / ESP32**, chọn đúng cổng **COM Port** của mạch và nhấn **Upload** để nạp chương trình.
- Cấp nguồn 5VDC cho mạch, kết nối chân SIG của cảm biến với chân điều khiển được khai báo trong chương trình.
- Xem kết quả mạch hoạt động theo chương trình đã nạp.

### Hướng dẫn lập trình với Micro:bit (kéo thả khối)

- Khởi động [Microsoft MakeCode](https://makecode.microbit.org/) và **Import** chương trình theo đường link sau: `https://github.com/makereduvn/mke_s14_dht11_microbit/`
- Kết nối mạch Micro:bit và **Download** chương trình.
- Cấp nguồn 5VDC cho mạch, kết nối chân SIG của cảm biến với chân điều khiển được khai báo trong chương trình.
- Xem kết quả mạch hoạt động theo chương trình đã nạp.

Nếu bắt đầu tự án mới cần cài đặt Extension **MKE_ONE_MICROBIT** trên [Microsoft MakeCode](https://makecode.microbit.org/) theo [hướng dẫn tại đây](https://github.com/makereduvn/MKE_ONE_MICROBIT). Sau khi cài đặt thành công, các khối lệnh của Extension **MKE_ONE_MICROBIT** sẽ xuất hiện trong danh sách block và sẵn sàng để sử dụng.

## Kích thước sản phẩm
![MKE-S14 DHT11](/extras/MKE-S14_1.jpg)

## Hình ảnh sản phẩm
![MKE-S14 DHT11](/extras/MKE-S14_2.png)
![MKE-S14 DHT11](/extras/MKE-S14_3.png)




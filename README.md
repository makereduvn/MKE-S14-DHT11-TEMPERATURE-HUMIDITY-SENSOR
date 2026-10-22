
# Cảm biến độ ẩm nhiệt độ MKE-S14 DHT11 Temperature Humidity Sensor

**MKE-S14 DHT11 Temperature Humidity Sensor** là cảm biến đo **nhiệt độ và độ ẩm không khí** sử dụng giao tiếp **Digital 1-Wire**, chỉ cần một chân tín hiệu để truyền dữ liệu, giúp việc kết nối với vi điều khiển trở nên đơn giản và thuận tiện. Cảm biến tích hợp phần tử đo nhiệt độ, độ ẩm cùng bộ xử lý tín hiệu bên trong, cho phép xuất dữ liệu đã được hiệu chuẩn dưới dạng số, giúp hệ thống đọc và xử lý nhanh chóng với **độ ổn định cao**.

Sản phẩm phù hợp cho nhiều ứng dụng như **đo nhiệt độ – độ ẩm môi trường, vườn thông minh, hệ thống giám sát không khí, thiết bị IoT và các dự án STEM**. Mạch được thiết kế tối ưu về **độ ổn định tín hiệu và khả năng chống nhiễu**, đảm bảo hoạt động tin cậy trong cả môi trường học tập và ứng dụng thực tế.

**Cảm biến độ ẩm nhiệt độ MKE-S14 DHT11 Temperature Humidity Sensor** hỗ trợ điện áp giao tiếp **3.3V và 5VDC**, cho phép kết nối trực tiếp và an toàn với các bo mạch điều khiển phổ biến như **Arduino, Raspberry Pi, Jetson Nano, Micro:bit** và nhiều nền tảng khác. Sản phẩm đi kèm **cáp kết nối 3P XH2.54 – Dupont**, đảm bảo kết nối chắc chắn, ổn định và thuận tiện trong quá trình lắp đặt và sử dụng.

> **⚠️ Lưu ý:** Cảm biến chỉ nên được sử dụng để đo **độ ẩm không khí trong môi trường thông thường (hơi nước)**. Không sử dụng cảm biến trong các môi trường **ủ kín, có nhiều vi khuẩn, nấm mốc, hóa chất hoặc tác nhân ăn mòn** như **ủ tỏi đen, ủ yếm khí, môi trường có hơi muối**. Các tác nhân này có thể bám hoặc tác động lên bề mặt cảm biến, làm **giảm độ chính xác của phép đo** hoặc **gây hư hỏng cảm biến theo thời gian**.

## Thông số kỹ thuật
- Điện áp cấp nguồn: 5VDC
- Chuẩn tín hiệu điều khiển: Digital 1-Wire
- Điện áp giao tiếp: TTL 3.3 / 5VDC
- Cảm biến sử dụng: [DHT11 Temperature Humidity Sensor ASAIR](/extras/DHT11%20datasheet.pdf)
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

| MKE-S14 | Ghi chú                   |
| :-------: | :------------------------- |
| `-`     | Chân cấp nguồn âm 0VDC    |
| `+`     | Chân cấp nguồn dương 5VDC |
| `S`   | Chân tín hiệu Digital 1-Wire |

## Hướng dẫn sử dụng

### Hướng dẫn kết nối
- Cấp nguồn 5VDC cho mạch qua hai chân `-` và `+`.
- Kết nối chân `S` (SIGNAL) của cảm biến với chân điều khiển được khai báo trong chương trình.

### Hướng dẫn sử dụng với Arduino / ESP32
- Trong Github của bộ thư viện, chọn **<> Code / Download ZIP** để tải về bộ thư viện.
- Mở chương trình Arduino, chọn **Sketch / Include Library / Add .ZIP Library** để cài đặt bộ thư viện.
- Mở chương trình mẫu tại **File / Examples / MKE_DHT TempHumi**
- Cấu hình board mạch tương ứng là **Arduino Uno / ESP32**, chọn đúng cổng **COM Port** của mạch và nhấn **Upload** để nạp chương trình.
- Cấp nguồn 5VDC cho mạch, kết nối chân `S` (SIGNAL) của cảm biến với chân điều khiển được khai báo trong chương trình.
- Xem kết quả mạch hoạt động theo chương trình đã nạp.

#### Chương trình mẫu cho Arduino Uno:
```ino
#include "MKE_DHT.h"
// Đặt tên cho chân kết nối cảm biến
#define DHTPIN 11     // Digital pin connected to the DHT sensor

MKE_DHT dht(DHTPIN, DHT11);

// Tạo biến lưu giá trị cảm biến
// value read from the sensor
float sensorValue1 = 0;
float sensorValue2 = 0;

void setup()
{
  // Khởi động kết nối Serial UART ở tốc độ 115200 để truyền dữ liệu lên máy tính.
  // Start the Serial UART connection at 115200 to transfer data to the computer.
  Serial.begin(115200);
  dht.begin();
}

void loop()
{
  // Đọc giá trị cảm biến
  // Get value
  sensorValue1 = dht.readTemperature();
  sensorValue2 = dht.readHumidity();

  // Hiển thị giá trị đo được của cảm biến lên máy tính.
  // Show the sensor value on Arduno Serial Monitor
  Serial.print("Temp: ");
  Serial.print(sensorValue1);
  Serial.print("  Humi: ");
  Serial.println(sensorValue2);
  
  // Chờ 2000ms
  // Wait 2000ms
  delay(2000);
}
```

#### Chương trình mẫu cho ESP32:
```ino
#include "MKE_DHT.h"
// Đặt tên cho chân kết nối cảm biến
#define DHTPIN 23     // IO23-D11 on Vietduino ESP32 (D11 on MakerEdu Shield)

MKE_DHT dht(DHTPIN, DHT11);

// Tạo biến lưu giá trị cảm biến
// value read from the sensor
float sensorValue1 = 0;
float sensorValue2 = 0;

void setup()
{
  // Khởi động kết nối Serial UART ở tốc độ 115200 để truyền dữ liệu lên máy tính.
  // Start the Serial UART connection at 115200 to transfer data to the computer.
  Serial.begin(115200);
  dht.begin();
}

void loop()
{
  // Đọc giá trị cảm biến
  // Get value
  sensorValue1 = dht.readTemperature();
  sensorValue2 = dht.readHumidity();

  // Hiển thị giá trị đo được của cảm biến lên máy tính.
  // Show the sensor value on Arduno Serial Monitor
  Serial.print("Temp: ");
  Serial.print(sensorValue1);
  Serial.print("  Humi: ");
  Serial.println(sensorValue2);
  
  // Chờ 2000ms
  // Wait 2000ms
  delay(2000);
}
```

### Hướng dẫn lập trình với Micro:bit (kéo thả khối)

- Khởi động [Microsoft MakeCode](https://makecode.microbit.org/) và **Import** chương trình theo đường link sau: `https://github.com/makereduvn/mke_s14_dht11_microbit/`
- Kết nối mạch Micro:bit và **Download** chương trình.
- Cấp nguồn 5VDC cho mạch, kết nối chân S (SIGNAL) của cảm biến với chân điều khiển được khai báo trong chương trình.
- Xem kết quả mạch hoạt động theo chương trình đã nạp.

Nếu bắt đầu tự án mới cần cài đặt Extension **MKE_ONE_MICROBIT** trên [Microsoft MakeCode](https://makecode.microbit.org/) theo [hướng dẫn tại đây](https://github.com/makereduvn/MKE_ONE_MICROBIT). Sau khi cài đặt thành công, các khối lệnh của Extension **MKE_ONE_MICROBIT** sẽ xuất hiện trong danh sách block và sẵn sàng để sử dụng.

## Kích thước sản phẩm
![MKE-S14 DHT11](/extras/MKE-S14_1.jpg)

## Hình ảnh sản phẩm
![MKE-S14 DHT11](/extras/MKE-S14_2.png)
![MKE-S14 DHT11](/extras/MKE-S14_3.png)

## Miễn trừ trách nhiệm
Sản phẩm này là bo mạch phát triển được thiết kế phục vụ cho mục đích nghiên cứu, thử nghiệm và học tập, không phải là một thiết bị hoàn chỉnh. Trong trường hợp người dùng kết hợp mạch này với các linh kiện, thiết bị hoặc phần mềm khác để tạo thành một hệ thống hoặc sản phẩm hoàn chỉnh, mọi chức năng và tính phù hợp của sản phẩm sau cùng đều thuộc trách nhiệm của người dùng.

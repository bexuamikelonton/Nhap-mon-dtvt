# ESP32-S3 GPIO Pin Map (`ESP32-S3-WROOM-1-N16R8`)

## 1. Camera OV7670 (`U2`)

| GPIO | Chân vật lý (`U1`) | Chân OV7670 | Net Label | Ghi chú |
| :--- | :---: | :--- | :--- | :--- |
| `IO4` | 4 | `SIO_C` (`A3`) | `SIOC` | Xung cấu hình SCCB |
| `IO5` | 5 | `SIO_D` (`A2`) | `SIOD` | Dữ liệu cấu hình SCCB |
| `IO6` | 6 | `VSYNC` (`D1`) | `VSYNC` | Đồng bộ khung hình dọc |
| `IO7` | 7 | `HREF` (`D2`) | `HREF` | Tham chiếu dòng ngang |
| `IO15` | 8 | `XCLK` (`E2`) | `XCLK` | Xung nhịp chủ cấp cho camera |
| `IO19` | 13 | `PCLK` (`E1`) | `PCLK` | Xung nhịp pixel |
| `IO11` | 19 | `D0` (`B4`) | `IO11` | Bit dữ liệu 0 (LSB) |
| `IO9` | 17 | `D1` (`A4`) | `IO9` | Bit dữ liệu 1 |
| `IO8` | 12 | `D2` (`B5`) | `IO8` | Bit dữ liệu 2 |
| `IO10` | 18 | `D3` (`A5`) | `IO10` | Bit dữ liệu 3 |
| `IO12` | 20 | `D4` (`D4`) | `IO12` | Bit dữ liệu 4 |
| `IO18` | 11 | `D5` (`E5`) | `IO18` | Bit dữ liệu 5 |
| `IO17` | 10 | `D6` (`F4`) | `IO17` | Bit dữ liệu 6 |
| `IO16` | 9 | `D7` (`E4`) | `IO16` | Bit dữ liệu 7 (MSB) |
| — | — | `AVDD`, `DVDD`, `RESET` | `3V3` | Nguồn 3.3V |
| — | — | `PWDN`, `DOGND`, `AGND` | `GND_01` | Mass |

## 2. Cảm biến siêu âm HC-SR04 (`U3`, `U4`, `U5`)

| GPIO | Chân vật lý (`U1`) | Linh kiện | Chân linh kiện | Net Label |
| :--- | :---: | :--- | :--- | :--- |
| `IO41` | 34 | `U3` (Ngăn 1) | `TRIG` | `IO41` |
| `IO40` | 33 | `U3` (Ngăn 1) | `ECHO` | `IO40` |
| `IO45` | 26 | `U4` (Ngăn 2) | `TRIG` | `IO45` |
| `IO48` | 25 | `U4` (Ngăn 2) | `ECHO` | `IO48` |
| `IO47` | 24 | `U5` (Ngăn 3) | `TRIG` | `IO47` |
| `IO21` | 23 | `U5` (Ngăn 3) | `ECHO` | `IO21` |

## 3. Servo, LED & Buzzer

| GPIO | Chân vật lý (`U1`) | Linh kiện | Chân linh kiện | Net Label |
| :--- | :---: | :--- | :--- | :--- |
| `IO20` | 14 | Header `SERVO_01` | `PWM` | `SERVO_01` |
| `IO3` | 15 | Header `SERVO_02` | `PWM` | `SERVO_02` |
| `IO13` | 21 | `U7` (qua `R1`) | `Anode` | `IO13` |
| `IO14` | 22 | `U8` (qua `R2`) | `Anode` | `IO14` |
| `IO1` | 39 | `BUZ1` | `+` | `BUZZER` |

## 4. Màn hình SPI (Header 8 chân)

| GPIO | Chân vật lý (`U1`) | Chân Header | Net Label | Lưu ý phần cứng |
| :--- | :---: | :--- | :--- | :--- |
| `IO35` | 28 | `MOSI` (Pin 1) | `IO35` | Trùng chân Octal PSRAM trên N16R8 |
| `IO36` | 29 | `MISO` (Pin 2) | `IO36` | Trùng chân Octal PSRAM trên N16R8 |
| `IO37` | 30 | `SCK` (Pin 3) | `IO37` | Trùng chân Octal PSRAM trên N16R8 |
| `IO38` | 31 | `CS` (Pin 4) | `IO38` | Chip Select |
| `IO39` | 32 | `DC` (Pin 6) | `IO39` | Data/Command |
| — | 3 | `RESET` (Pin 5) | `RESET` | Đang nối chung chân `EN` |

## 5. Chân GPIO chưa sử dụng

| GPIO | Chân vật lý (`U1`) | Ghi chú |
| :--- | :---: | :--- |
| `IO0` | 27 | Strapping pin (Boot mode) |
| `IO2` | 38 | GPIO trống |
| `IO42` | 35 | GPIO trống (có thể gắn cảm biến IR) |
| `IO43` (`TXD0`) | 37 | UART0 TX (nạp code / debug) |
| `IO44` (`RXD0`) | 36 | UART0 RX (nạp code / debug) |
| `IO46` | 16 | Strapping pin |

## 6. Khai báo `#define` (C/C++)

```cpp
// Camera OV7670 (U2)
#define CAM_PIN_PWDN    -1
#define CAM_PIN_RESET   -1
#define CAM_PIN_XCLK    15
#define CAM_PIN_SIOD     5
#define CAM_PIN_SIOC     4
#define CAM_PIN_D7      16
#define CAM_PIN_D6      17
#define CAM_PIN_D5      18
#define CAM_PIN_D4      12
#define CAM_PIN_D3      10
#define CAM_PIN_D2       8
#define CAM_PIN_D1       9
#define CAM_PIN_D0      11
#define CAM_PIN_VSYNC    6
#define CAM_PIN_HREF     7
#define CAM_PIN_PCLK    19

// Cảm biến siêu âm HC-SR04 (U3, U4, U5)
#define TRIG_1_PIN      41
#define ECHO_1_PIN      40
#define TRIG_2_PIN      45
#define ECHO_2_PIN      48
#define TRIG_3_PIN      47
#define ECHO_3_PIN      21

// Servo, LED & Buzzer
#define SERVO_1_PIN     20
#define SERVO_2_PIN      3
#define LED_1_PIN       13
#define LED_2_PIN       14
#define BUZZER_PIN       1

// Màn hình SPI
#define TFT_MOSI_PIN    35
#define TFT_MISO_PIN    36
#define TFT_SCK_PIN     37
#define TFT_CS_PIN      38
#define TFT_DC_PIN      39
```
```
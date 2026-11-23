# Giao diện giữa các module (chốt trong tuần 1)

## Quy ước đặt tên chung

Quy ước này áp dụng cho toàn bộ mã nguồn trong `firmware/`, `ai_model/` và `cloud/`.
Khi cần thay đổi quy ước, cập nhật tại file này trước rồi đồng bộ các module liên quan.

| Loại | Quy ước | Ví dụ |
|---|---|---|
| Thư mục/module | `snake_case` | `esp32_main`, `servo_control`, `telegram_client` |
| File C++/Arduino | `snake_case` | `state_machine.cpp`, `uart_protocol.h`, `camera_infer.ino` |
| Hàm | `camelCase` | `moveToBin()`, `sendLog()`, `sendStatus()` |
| Biến | `snake_case` | `fill_level`, `ai_confidence`, `uart_message` |
| Hằng số | `UPPER_SNAKE_CASE` | `UART_BAUD_RATE`, `AI_TIMEOUT_MS` |
| Kiểu dữ liệu/class | `PascalCase` | `WasteBinState`, `OfflineQueue` |
| Biến boolean | Bắt đầu bằng `is`, `has` hoặc `can` | `isDoorOpen`, `hasNetwork`, `canSendLog` |

### Quy tắc chung

- Tên cần mô tả đúng vai trò và tránh viết tắt không thống nhất.
- Hạn chế tên quá ngắn như `a`, `data`, `temp`; ngoại lệ được phép với biến đếm `i`, `j`.
- Một module, hàm hoặc biến chỉ dùng một thuật ngữ cho cùng một ý nghĩa.
- Nhãn kết quả AI phải dùng đúng: `bottle`, `can`, `paper`, `none`.
- Khi thêm hàm được gọi qua nhiều module, cập nhật mục tương ứng trong file này trước khi code.

## UART: board camera -> ESP32 chính
- Tốc độ: 115200 baud, 8N1
- Định dạng: `<nhãn>,<độ_tin_cậy>\n`   ví dụ: `bottle,0.87`
- Nhãn hợp lệ: bottle | can | paper | none
- Timeout chờ kết quả AI: ... ms

## Hàm servo (TV3)
- moveToBin(int id)
- openDoor() / closeDoor()

## Hàm IoT (TV4)
- sendLog(label, confidence)
- sendStatus(fill1, fill2, fill3)
- sendTelegramAlert(msg)

## Bảng chân GPIO
Xem hardware/gpio_map.md

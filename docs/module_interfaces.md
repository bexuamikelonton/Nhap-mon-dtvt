# Giao diện giữa các module (chốt trong tuần 1)

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

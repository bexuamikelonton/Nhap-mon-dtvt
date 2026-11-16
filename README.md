# Smart Waste Bin

Thùng rác thông minh: nhận diện rác bằng Edge AI (ESP32 camera), phân loại
bằng servo, giám sát qua Google Sheets và cảnh báo qua Telegram.

## Cấu trúc
- `firmware/`     mã nguồn các board (esp32_main, esp32cam_ai, servo_control, iot, display)
- `dataset/`      ảnh huấn luyện (bottle, can, paper, none)
- `ai_model/`     kết quả huấn luyện và đánh giá mô hình
- `cloud/`        Google Apps Script, mẫu Google Sheets
- `hardware/`     bản vẽ cơ khí, sơ đồ nguyên lý, PCB, BOM, bảng GPIO
- `tests/`        kế hoạch và kết quả kiểm thử
- `measurements/` số liệu đo đạc (độ trễ, sai số, độ ổn định)
- `docs/`         báo cáo, slide, video demo, giao diện giữa các module

## Phân công
TV1 tích hợp | TV2 AI | TV3 cơ khí, servo | TV4 IoT, đo đạc | TV5 điện tử, test, tài liệu

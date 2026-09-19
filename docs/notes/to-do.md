# To do List

## Ghi chú

Lộ trình triển khai chi tiết, đi từ

  1. **Cốt lõi** (Hardware interface & I2S Driver)
  2. **Kiến trúc** (Dual-core & Memory Management)
  3. **DSP** (Digital Signal Processing)
  4. **Giao tiếp dữ liệu** (Connectivity & Data Visualization)
  5. **Kiểm chứng và tối ưu** (Validation & Optimization)

## To-do Items

- [x] Thiết kế khung dự án (Project Structure)
- [x] Bổ sung các tài liệu căn bản của dự án
- [x] Tìm hiểu về thiết kế reset và clock nội bộ của ESP32
- [x] Viết driver setup clock cho ESP32 lên tối đa 240MHz
- [x] Tìm hiểu về I2S Protocol và cách hoạt động của I2S trên ESP32
- [x] Tìm hiểu các linh kiện phần cứng hỗ trợ thiết kế
- [x] Tìm hiểu về SPI Protocol và cách hoạt động của SPI trên ESP32
- [x] Tái cấu trúc và thay đổi cách tận dụng driver từ ESP-IDF thay thế cho bare-metal driver
- [x] Mua linh kiện phần cứng cần thiết cho việc phát triển và thử nghiệm
- [x] Hàn mạch PCM1808 để thử nghiệm và cấu hình I2S
- [x] Cấu hình I2S để thu tín hiệu âm thanh từ PCM1808 và MAX9812
- [x] Cắm mạch và kiểm tra tín hiệu hoạt động
- [x] Thiết kế PCB theo mẫu sử dụng PCM1808, MAX9812, ESP32, TL072IDT gốc
- [x] Bổ sung thiết kế phân tách đường tín hiệu cơ học với PJ-342S để giảm nhiễu và cải thiện chất lượng âm thanh
- [x] Làm mượt tín hiệu clock cho PCM1808 với mạch Pierce Oscillator để giảm jitter và cải thiện chất lượng âm thanh
- [x] Bổ sung đầu thu siêu âm TCT40-16R để thu tín hiệu siêu âm và tích hợp vào hệ thống làm stereo mode
- [x] Bổ sung mạch ổn áp DC-DC 1 MHz 3/6V-12V để cung cấp nguồn ổn định cho hệ thống
- [x] Thêm các linh kiện bổ sung để tách nguồn xuống 9V, 5V, 3.3V cho các thành phần khác nhau của hệ thống
- [x] Cân nhắc bổ sung LDO cho mạch để giảm nhiễu và cải thiện chất lượng âm thanh. Loại bỏ do độ phức tạp phải sửa đổi thiết kế PCB và tăng chi phí
- [x] Kiểm tra lại kích thước và bố trí linh kiện đã về hàng để đảm bảo thiết kế PCB phù hợp và tối ưu
- [x] Lựa chọn dataset và thuật toán xử lý dữ liệu âm thanh phù hợp để kiểm chứng khả năng thu thập dữ liệu âm thanh chất lượng cao của hệ thống
- [x] Thiết kế server nội bộ để ESP32 giao tiếp và truyền dữ liệu âm thanh về kit xử lý trung tâm (sử dụng WSL trên Windows để phát triển và kiểm thử như 1 server nội bộ)

// NOTE - 2242 - 19/09/26 onward

<!-- STATUS
Hiện tại server nội bộ đã có sẵn laptop cũ chạy Fedora 42 nên không cần phải cài đặt lại WSL trên Windows. Việc cấu hình TCP/IP và các thiết lập liên quan sẽ được tạm hoãn để tập trung vào việc triển khai MFCC và μEDP
-->

- [ ] Cân nhắc đưa μEDP vào làm nền tảng điều phối và xử lý dữ liệu âm thanh cho hệ thống.

<!-- STATUS
Đã thống nhất triển khai μEDP làm nền tảng điều phối và xử lý dữ liệu âm thanh cho hệ thống. Việc triển khai sẽ được thực hiện trên ESP32S3 và STM32H723 cho đề tài CE201 và CE224. Các MCU khác sẽ được loại bỏ khỏi repo CE201, ngoại trừ STM32F103 được giữ lại để thực hiện thí nghiệm baseline.
-->

- [ ] Bổ sung driver thiết kế cho thuật toán MFCC bao gồm (pre-emphasis, frame-split, windowing, fft, filter bank, dct) để phân tích và trích xuất đặc trưng âm thanh từ dữ liệu thu thập được
- [ ] Bổ sung driver tính toán rms, crest factor, spectral kurtosis để phân tích đặc trưng âm thanh và đánh giá chất lượng tín hiệu
- [ ] Kiểm tra kích thước của jack cắm PJ-342S để đảm bảo tương thích với thiết kế PCB
- [ ] Đặt gia công in mạch
- [ ] Tìm hiểu cơ chế giao tiếp với PSRAM để tận dụng làm ring buffer cho dữ liệu âm thanh

## Dữ liệu cần
### 1. Dữ liệu từ gói tin ARP (ARP Packets)
- `Địa chỉ MAC nguồn (Source MAC):` Kiểm tra xem có sự thay đổi bất thường của MAC ứng với một IP nào đó không.
- `Địa chỉ IP nguồn (Source IP):` Xác định xem IP có bị giả mạo không.
- `Địa chỉ MAC đích (Destination MAC):` Kiểm tra xem có hiện tượng MAC trùng lặp không hợp lệ không.
- `Địa chỉ IP đích (Destination IP):` Phát hiện các yêu cầu ARP không hợp lệ.
- `Loại gói tin ARP (Request/Reply):` Tấn công ARP thường liên quan đến việc gửi quá nhiều ARP Reply giả mạo.
### 2. Thông tin về tần suất và tốc độ gói tin ARP
- **`Số lượng ARP Request/Reply` trong một khoảng thời gian:** Tấn công ARP thường tạo ra một lượng lớn gói tin ARP trong thời gian ngắn.
- **`Tỷ lệ ARP Reply/Request` bất thường:** Thông thường, ARP Reply chỉ được gửi khi có Request, nhưng trong tấn công, kẻ tấn công có thể gửi Reply mà không có Request.
### 3. Dữ liệu về sự thay đổi ánh xạ IP-MAC
- **`Bảng ARP Cache (ARP Table)` của các thiết bị:** Theo dõi sự thay đổi đột ngột của cặp IP-MAC (ví dụ: một IP đột nhiên được ánh xạ sang một MAC khác).
- `Sự xuất hiện của nhiều MAC cho một IP:` Dấu hiệu của ARP Spoofing khi nhiều thiết bị khác nhau tuyên bố sở hữu cùng một IP.
### 4. Thông tin về lưu lượng mạng (Network Traffic)
- `Lưu lượng từ các máy có MAC giả mạo:` Kiểm tra xem có sự gia tăng đột biến lưu lượng từ một MAC cụ thể không.
- `Giao tiếp bất thường giữa các thiết bị:` Ví dụ, một máy đột nhiên trở thành gateway (MITM - Man-in-the-Middle).
### 5. Dữ liệu từ các nguồn khác
- Log từ hệ thống phát hiện xâm nhập (IDS/IPS): Các cảnh báo liên quan đến ARP.
- Thông tin từ DHCP Server: Kiểm tra xem có IP nào bị chiếm dụng bất hợp lệ không.
- Dữ liệu từ switch (nếu có): Một số switch hỗ trợ tính năng theo dõi ARP.
### 6. Nhãn (Label) dữ liệu để huấn luyện mô hình ML
- Dữ liệu bình thường (Normal ARP Traffic): Các gói ARP hợp lệ trong mạng.
- Dữ liệu tấn công (ARP Attack Traffic): Các mẫu ARP Spoofing đã được ghi nhận (có thể sử dụng công cụ như Ettercap, Scapy để tạo dữ liệu mô phỏng).
### 7. Các đặc trưng (Features) có thể sử dụng trong ML
- Tần suất gói ARP (ARP packet rate).
- Tỷ lệ ARP Reply không hợp lệ (Unsolicited ARP Replies).
- Sự thay đổi MAC-IP (MAC-IP binding changes).
- Sự trùng lặp MAC cho nhiều IP (MAC duplication).
- Thời gian giữa các gói ARP (Inter-arrival time of ARP packets).
### Một số thuật toán ML có thể áp dụng
#### Phân loại (Classification):
- Random Forest
- SVM (Support Vector Machine)
- Neural Networks
#### Phát hiện bất thường (Anomaly Detection):
- Isolation Forest
- One-Class SVM
- Autoencoders (Deep Learning)

| Thuật toán                                             | Ưu điểm                             | Gợi ý                            |
| ------------------------------------------------------ | ----------------------------------- | -------------------------------- |
| Decision Tree                                          | Dễ hiểu, dễ triển khai              | ✅ Cơ bản, tốt để kiểm thử        |
| Random Forest                                          | Độ chính xác cao, chống overfitting | ✅ Rất tốt                        |
| XGBoost                                                | Tối ưu hoá mạnh mẽ, hiệu suất cao   | 🔥 Tốt cho môi trường thực       |
| SVM / KNN                                              | Thử nghiệm nhưng không phải tối ưu  | Có thể dùng để so sánh           |
| Neural Network (nếu dùng nhiều đặc trưng, time-series) | Khả năng học cao                    | Dành cho dữ liệu lớn và phức tạp |

### ① Thông tin cơ bản về gói tin ARP từ wireshark
- Source MAC (địa chỉ MAC nguồn)
- Source IP (địa chỉ IP nguồn)
- Destination MAC (địa chỉ MAC đích)
- Destination IP (địa chỉ IP đích)
- Opcode (loại gói tin: Request (1) hoặc Reply (2))
- Packet size (kích thước gói tin)
- Timestamp (thời điểm gửi/nhận gói tin)

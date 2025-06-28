## DỮ LIỆU THU ĐƯỢC TỪ wireshark
- **1. timestamp:** thời điểm gửi/nhận gói tin
- **2. protocol:**
- **3. length-Packet size:** kích thước gói tin
- **4. src_mac:** `nằm trên khung ethernet` MAC của thiết bị thực sự gửi gói tin đi (vận chuyển thật trên mạng LAN)
- **5. dst_mac:** `nằm trên khung ethernet` MAC của thiết bị thực sự nhận gói tin đi (vận chuyển thật trên mạng LAN)
- **6. arp_opcode:** loại gói tin, *tấn công arp thường liên quan đến việc gửi quá nhiều reply giả mạo*
  - 1: ARP Request (Yêu cầu ARP).
  - 2: ARP Reply (Phản hồi ARP).
  - Các opcode khác (như RARP) ít phổ biến hơn.  
- **7. arp_src_ip:** địa chỉ ip nguồn trong gói `arp`
- **8. arp_src_mac:** địa chỉ mac nguồn trong gói `arp`
- **9. arp_dst_ip:** địa chỉ ip đích trong gói `arp`
- **10. arp_dst_mac:** địa chỉ mac nguồn trong gói `arp`
## TRÍCH ĐẶC TRƯNG (DẤU HIỆU TẤN CÔNG)
- **1. `(arp_rate_per_sec)` Tần xuất gói tin trong một khoảng thời gian:** Tấn công ARP thường tạo ra một lượng lớn gói tin ARP trong thời gian ngắn.
  - Phát hiện flood ARP (Request/Reply vượt ngưỡng)
  - Ngưỡng thông thường: <5 gói/giây, tấn công: >50-100 gói/giây
- **2. `(is_unsolicited)` Reply bất thường** Thông thường, ARP Reply chỉ được gửi khi có Request, nhưng trong tấn công, kẻ tấn công có thể gửi Reply mà không có Request.
  - Bình thường: Reply chỉ sau Request
  - Tấn công: Reply không được yêu cầu (unsolicited)
- **3. `(mac_change)` Thay đổi ARP Cache(ARP Table):** Theo dõi sự thay đổi đột ngột của cặp IP-MAC (ví dụ: một IP đột nhiên được ánh xạ sang một MAC khác).
- **4. `(mac_duplicate)` Sự xuất hiện của nhiều MAC cho một IP:** xung đột địa chỉ mac.
- **5. `(src_mac_count)` Tổng gói tin từ một địa chỉ MAC:** Kiểm tra xem có sự gia tăng đột biến lưu lượng từ một MAC cụ thể không.
- **6. `gateway_change`Giao tiếp bất thường giữa các thiết bị:** Ví dụ, một máy đột nhiên trở thành gateway (MITM - Man-in-the-Middle).
- **7. `(time_diff)`Khoản thời gian giữa các gói tin:**
  - Bình thường 1 phút 1 gói arp
  - Khi bị tấn công 1 phút > 20 gói
- **9. Tần suất thay đổi MAC**
- **10. `arp_count_per_mac_per_sec`Tổng gói tin mỗi giây từ một địa chỉ MAC**
  - lấy địa chỉ mac từ arp_src_mac
-  **Tỷ lệ ARP Reply/Request:**
## GÁN NHÃN CHO DATASET(label)
- 0: normal
- 1: attack arp
## Các đặc trưng (Features) có thể sử dụng trong ML
- Tần suất gói ARP (ARP packet rate).
- Tỷ lệ ARP Reply không hợp lệ (Unsolicited ARP Replies).
- Sự thay đổi MAC-IP (MAC-IP binding changes).
- Sự trùng lặp MAC cho nhiều IP (MAC duplication).
- Thời gian giữa các gói ARP (Inter-arrival time of ARP packets).
## Công cụ thu thập dữ liệu
- Wirehasrk: Bắt gói tin ARP
- Scapy(Python): Tạo và phân tích gói tin
## Một số thuật toán ML có thể áp dụng
- Phân loại (Classification):
  - Random Forest
  - SVM (Support Vector Machine)
  - Neural Networks
- Phát hiện bất thường (Anomaly Detection):
  - Isolation Forest
  - One-Class SVM
  - Autoencoders (Deep Learning)
##############################################################








### 🧠 1. Nhiều gói ARP Reply không có ARP Request tương ứng
- Trong giao thức ARP bình thường, một ARP Reply chỉ được gửi sau khi có ARP Request.

- Tấn công ARP thường gửi hàng loạt ARP Reply giả mạo mà không có yêu cầu (ARP Request).

- Dấu hiệu: Nhiều ARP Reply từ một địa chỉ IP đến nhiều địa chỉ MAC khác nhau mà không có ARP Request.

### ⚠️ 2. Một địa chỉ MAC gắn với nhiều địa chỉ IP khác nhau
- Trong mạng bình thường, 1 địa chỉ MAC = 1 địa chỉ IP.

- Khi bị tấn công, bạn có thể thấy nhiều IP cùng liên kết với 1 MAC, thường là MAC của kẻ tấn công.

###### Dấu hiệu:
###### Ví dụ:
```
192.168.1.1 → AA:BB:CC:DD:EE:FF  
192.168.1.100 → AA:BB:CC:DD:EE:FF  
192.168.1.105 → AA:BB:CC:DD:EE:FF
```
### 📈 3. Tần suất gửi ARP cao bất thường từ một thiết bị
- Thiết bị tấn công thường gửi liên tục các gói ARP giả mạo để chiếm bảng ARP của các nạn nhân.

- Dấu hiệu: Tần suất gói ARP từ một IP hoặc MAC cao vượt trội so với thiết bị bình thường.

### 🔁 4. Địa chỉ MAC của gateway bị thay đổi bất thường
- Kẻ tấn công thường mạo danh gateway để làm man-in-the-middle.

- Dấu hiệu: Bảng ARP của nạn nhân chứa địa chỉ MAC khác với địa chỉ thực của gateway.

- Có thể kiểm tra bằng:
```
arp -a
```
### 🧾 5. Sự thay đổi liên tục của ánh xạ IP ↔ MAC
- Trong môi trường mạng ổn định, ánh xạ giữa IP và MAC không thay đổi thường xuyên.

- Nếu ánh xạ này liên tục bị cập nhật, đó có thể là do ARP poisoning.

- Dấu hiệu: Cùng một IP bị gán nhiều MAC khác nhau trong một khoảng thời gian ngắn.

### 🔍 6. Sự hiện diện của gói ARP Gratuitous bất thường
- ARP Gratuitous là gói ARP thông báo địa chỉ IP của chính mình mà không có yêu cầu.

- Dùng để cập nhật bảng ARP. Tuy nhiên, nếu có nhiều ARP Gratuitous không đúng lúc, đó có thể là dấu hiệu giả mạo.

- Dấu hiệu: Gói ARP dạng Gratuitous từ địa chỉ không hợp lệ hoặc quá thường xuyên.

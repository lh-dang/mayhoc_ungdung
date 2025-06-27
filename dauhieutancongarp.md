## DỮ LIỆU THU ĐƯỢC TỪ wireshark
- **timestamp:** thời điểm gửi/nhận gói tin
- **protocal:**
- **length-Packet size:** kích thước gói tin
- **src_mac:** `nằm trên khung ethernet` MAC của thiết bị thực sự gửi gói tin đi (vận chuyển thật trên mạng LAN)
- **dst_mac:** `nằm trên khung ethernet` MAC của thiết bị thực sự nhận gói tin đi (vận chuyển thật trên mạng LAN)
- **arp_opcode:** loại gói tin, *tấn công arp thường liên quan đến việc gửi quá nhiều reply giả mạo*
  - 1: ARP Request (Yêu cầu ARP).
  - 2: ARP Reply (Phản hồi ARP).
  - Các opcode khác (như RARP) ít phổ biến hơn.  
- **arp_src_ip:** địa chỉ ip nguồn trong gói `arp`
- **arp_src_mac:** địa chỉ mac nguồn trong gói `arp`
- **arp_dst_ip:** địa chỉ ip đích trong gói `arp`
- **arp_dst_mac:** địa chỉ mac nguồn trong gói `arp`


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

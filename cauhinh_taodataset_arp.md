## Sơ đồ mạng ban đầu

![image](https://github.com/user-attachments/assets/d57440dc-cd4e-41ba-a20a-6f56896fdde9)


|Thiết Bị|Địa chỉ ip|Địa chỉ MAC|
|--------|----------|-----------|
|gateway_R1|172.16.3.1|c4:01:58:e8:00:00|
|kali_linux|172.16.3.2|00:0c:29:50:0b:fb|
|windows_7_x64|172.16.3.3|00:0c:29:f7:fa:46|
|ubuntu_x64|172.16.3.4|00:0c:29:2d:39:b9|
***********************************************************
## Sơ đồ mạng sau ngày 29/6
### xem card mạng
```
ip link
```
### đặt địa chỉ ip thủ công
```
ip link set <interface> down
ip addr add <ip>/<mask> dev <interface>
ip link set <interface> up
```
### đặt địa chỉ mac
```
ip link set <interfave> down
ip link set <interface> address <mac_address>
```
### kiểm tra địa chỉ
```
ip addr show dev eth0
```
### xem arp 
```
arp -a
```
### Lưu cấu hình tự boot mỗi khi khởi động
#### soạn thảo 🧾
```
vi /etc/network/interfaces
```
#### 🧾 nội dung
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 192.168.1.100
    netmask 255.255.255.0
    gateway 192.168.1.1
```
#### 🔃 khởi động dịch vụ mạng theo cấu hình
```
rc-service networking restart
ip addr show dev eth0
rc-update add networking default
```
![image](https://github.com/user-attachments/assets/dd959b60-3e90-4066-9b88-cefd08d4cbe1)

|Thiết Bị|Địa chỉ ip|Địa chỉ MAC|
|--------|----------|-----------|
|gateway_R1|172.16.3.1|c4:01:58:e8:00:00|
|kali_linux|172.16.3.2|00:0c:29:50:0b:fb|
|windows_7_x64|172.16.3.3|00:0c:29:f7:fa:46|
|ubuntu_x64|172.16.3.4|00:0c:29:2d:39:b9|
|alpinelinux1|172.16.3.7|0c:66:fe:df:00:00|
|alpinelinux2|172.16.3.6|0c:c2:55:b0:00:00|
****************************************************************************************
![image](https://github.com/user-attachments/assets/e96ca47f-5b50-4863-b210-df408fd8641b)
|Thiết Bị|Địa chỉ ip|Địa chỉ MAC|
|--------|----------|-----------|
|kali|192.168.10.5|08:00:27:6e:13:6e|
|ubuntu 2|192.168.10.2|00:0c:29:95:99:68|
|ubuntu 01|192.168.10.4|08:00:27:f6:8e:2e|
|ubuntu 1|192.168.10.3|00:0c:29:c7:d3:01|
|gateway|192.168.10.1|c2:01:27:10:00:00|
## MÔ HÌNH NGÀY 30/6
![image](https://github.com/user-attachments/assets/a2cf82b2-66eb-4d1c-9b41-7036e6b30d84)

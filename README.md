# PHẦN NỘI DUNG

## 1. Mô tả bài toán

## 2. Mô tả dữ liệu, ý nghĩa của dữ liệu
### 2.1. Mô tả dữ liệu
### 2.2. Ý nghĩa dữ liệu
#### 2.2.1. Giới thiệu các đặc trưng và nhãn của dữ liệu
#### 2.2.2. Sự phân bố các giá trị của nhãn

## 3. Phân tích dữ liệu và lựa chọn mô hình
### 3.1. Phân tích dữ liệu
#### 3.1.1. Đánh giá dữ liệu
Tập dữ liệu có định dạng nhị phân, với mỗi mẫu có nhãn phân loại rõ ràng.
Dữ liệu khá đầy đủ, mặc dù có xuất hiện một số giá trị không xác định (missing values). Những trường hợp này chiếm tỷ lệ nhỏ, do đó có thể được coi là ngoại lệ và xử lý với các phương pháp như **điền giá trị trung bình hoặc giá trị phổ biến nhất của đặc trưng tương ứng thay vì loại bỏ**, nhằm giữ lại các bộ dữ liệu có giá trị tham khảo cao.
Đây là bài toán thuộc dạng học có giám sát (supervised learning), với nhãn dữ liệu có giá trị rời rạc và phân loại rõ ràng. Tập nhãn được chia thành hai lớp:
Lớp có giá trị 0: Đại diện cho ... .
Lớp có giá trị 1: Đại diện cho ... .
Lớp có giá trị 2: Đại diện cho ... .
Tập dữ liệu có sự ```mất cân bằng``` nhãn tương đối lớn, trong đó lớp có giá trị ... (...) chiếm đa số. Điều này có thể gây khó khăn cho các mô hình học máy trong việc nhận diện chính xác ... .Dữ liệu kiểm tra Overfitting

#### 3.1.2. Tiền xử lý dữ liệu
### 3.2. Lựa chọn mô hình
#### 3.2.1.	K-Nearest Neighbors (KNN):
![image](https://github.com/user-attachments/assets/7a58f91e-4bc7-42df-a9a7-4d2236bfe96d)

Mô tả giải thuật KNN

KNN (K-Nearest Neighbors) là một thuật toán học máy phi tham số, học có giám sát, lười (lazy learning), sử dụng cho cả hai mục đích là hồi quy và phân lớp. Thuật toán được Evelyn Fix và Joseph Hodges công bố đầu tiên vào năm 1951 và được Thomas Cover mở rộng sau này vào năm 1967.

Mô hình KNN hoạt động dựa trên nguyên tắc: dữ liệu mới sẽ được phân loại dựa trên các dữ liệu đã có cùng lớp. Cụ thể, thuật toán KNN sẽ tìm ra k điểm dữ liệu đã có gần nhất với dữ liệu mới theo một hàm khoảng cách nào đó (công thức Euclid, Manhattan, Minkowski,...). Sau đó, thuật toán sẽ phân loại dữ liệu mới dựa trên lớp của đa số các điểm k gần nhất.

Quá trình tìm k láng giềng của mẫu mới thường sử dụng khoảng cách Euclidean được định nghĩa như sau:

![image](https://github.com/user-attachments/assets/192e7d9b-a54a-45c8-adaf-630fa0ba781a)

,trong đó:  x^(a )và x^b là 2 mẫu độc lập.

Ưu điểm của mô hình KNN
- Đơn giản và dễ giải thích: Mô hình KNN có cấu trúc đơn giản, dễ hiểu và dễ triển khai.
- Không đưa ra bất kỳ giả định nào: Mô hình KNN không đưa ra bất kỳ giả định nào về dữ liệu, vì thế nó có thể được sử dụng trong các bài toán phi tuyến tính.
- Hoạt động tốt trong trường hợp phân loại với nhiều lớp: Mô hình KNN có thể phân loại dữ liệu với nhiều lớp một cách hiệu quả.
- Sử dụng được trong cả phân loại và hồi quy: Mô hình KNN có thể được sử dụng cho cả hai mục đích là phân loại và hồi quy.
  
Nhược điểm của mô hình KNN
- Yêu cầu nhiều bộ nhớ: Mô hình KNN cần lưu trữ toàn bộ tập dữ liệu, vì thế nó có thể yêu cầu nhiều bộ nhớ, đặc biệt là đối với các tập dữ liệu lớn.
- Tốn kém về mặt tính toán: Mô hình KNN có thể tốn kém về mặt tính toán, đặc biệt là đối với các tập dữ liệu lớn.
- Nhạy cảm với nhiễu: Mô hình KNN có thể nhạy cảm với nhiễu trong tập dữ liệu.


#### 3.2.2.	Cây Quyết định (Decision Tree):
![image](https://github.com/user-attachments/assets/826f10df-5705-4126-83eb-f8140844d437)

Decision Tree (cây quyết định) là một thuật toán học máy phân loại, có thể được sử dụng để phân loại dữ liệu phân loại và hồi quy. Mô hình hoạt động dựa trên nguyên tắc chia nhỏ dữ liệu thành các nhóm dựa trên các thuộc tính của dữ liệu.

Mô hình Decision Tree được xây dựng theo dạng cây phân cấp, trong đó mỗi nút đại diện cho một thuộc tcom)
4. [OPML](https://www.openml.org/search?type=data&status=any&sort=runs&id=4534)
5. [kitsune-mitm-test](https://www.kaggle.com/code/smeyra/kitsune-mitm-test)
6. [kitsune-mitm-attack-detection](https://www.kaggle.com/code/smeyra/kitsune-mitm-attack-detection)
7. [MITM (IoT)](https://link.springer.com/article/10.1007/s43926-025-00104-w#Abs1)
8. [Detecting_End-Point_EP_Man-In-The-Middle_MITM_Attack_based_on_ARP_Analysis_A_Machine_Learning_Approach(Báo kkhoa học)](https://www.researchgate.net/publication/347947532_Detecting_End-Point_EP_Man-In-The-Middle_MITM_Attack_based_on_ARP_Analysis_A_Machine_Learning_Approach)
9. [Phát hiện tấn công mitm ở phía máy khách (báo khoa họchọc)](https://github.com/Maheshmuddunuru/MITM-Detection-Mechanism-at-client-side-using-Machine-Learning-Algorithms/blob/main/Final_research_report.pdf)

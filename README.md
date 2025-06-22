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

Mô hình Decision Tree được xây dựng theo dạng cây phân cấp, trong đó mỗi nút đại diện cho một thuộc tính của dữ liệu, mỗi cạnh đại diện cho một giá trị của thuộc tính đó và mỗi nút lá đại diện cho một kết quả phân loại.

Ưu điểm của mô hình Decision Tree
-	Đơn giản và dễ hiểu: Mô hình Decision Tree có cấu trúc đơn giản, dễ hiểu và dễ triển khai.
-	Không đưa ra bất kỳ giả định nào: Mô hình Decision Tree không đưa ra bất kỳ giả định nào về dữ liệu, vì thế nó có thể được sử dụng trong các bài toán phân loại phi tuyến.
-	Hoạt động tốt trong trường hợp dữ liệu có ít mẫu: Mô hình Decision Tree có thể hoạt động hiệu quả trong trường hợp dữ liệu có ít mẫu.
-	Dễ giải thích: Mô hình Decision Tree có thể dễ dàng giải thích, vì nó cung cấp một biểu đồ trực quan thể hiện mối quan hệ giữa các thuộc tính và kết quả phân loại.

Nhược điểm của mô hình Decision Tree
-	Dễ bị overfitting: Mô hình Decision Tree có thể bị overfitting nếu không được kiểm soát.
-	Yêu cầu nhiều bộ nhớ: Mô hình Decision Tree có thể yêu cầu nhiều bộ nhớ, đặc biệt là đối với các tập dữ liệu lớn.
-	Tốn kém về mặt tính toán: Mô hình Decision Tree có thể tốn kém về mặt tính toán, đặc biệt là đối với các tập dữ liệu lớn.

#### 3.2.3.	Rừng Ngẫu nhiên (Random Forest):
![image](https://github.com/user-attachments/assets/9afefea4-4af0-4f62-a475-ccbcacaccea5)

Đây là một mô hình ensemble dựa trên việc kết hợp nhiều cây quyết định, giúp tăng cường độ chính xác và khả năng khái quát hóa của mô hình. 

Rừng ngẫu nhiên sử dụng một tập hợp cây quyết định độc lập, tạo thành từ các mẫu dữ liệu và tập con của các thuộc tính ngẫu nhiên.

Sau đó, dự đoán của các cây được tổng hợp bằng cách bỏ phiếu hoặc tính trung bình (tuỳ thuộc vào bài toán phân loại hay hồi quy), giúp tạo ra một mô hình mạnh mẽ và ít nhạy cảm với quá khớp.
Ưu điểm của mô hình Random Forest
-	Độ chính xác cao: Random Forest thường có độ chính xác cao, đặc biệt là trong các bài toán phân loại với dữ liệu phức tạp.
-	Kháng overfitting: Random Forest có khả năng kháng overfitting tốt hơn so với mô hình Decision Tree.
-	Dễ triển khai: Random Forest có cấu trúc đơn giản, dễ triển khai và có thể được sử dụng trong nhiều lĩnh vực khác nhau.
Nhược điểm của mô hình Random Forest
-	Yêu cầu nhiều bộ nhớ: Random Forest có thể yêu cầu nhiều bộ nhớ để lưu trữ các cây quyết định.
-	Tốn kém về mặt tính toán: Random Forest có thể tốn kém về mặt tính toán, đặc biệt là đối với các tập dữ liệu lớn.
-	Khó giải thích: Random Forest có thể khó giải thích hơn so với mô hình Decision Tree.

#### 3.2.4.	Bagging (Bootstrap Aggregating):
![image](https://github.com/user-attachments/assets/71f3c81e-649e-4451-bd13-fbb3ae239f06)

Bagging (Bootstrap aggregating) là một thuật toán học máy thuộc nhóm ensemble learning, được sử dụng để phân loại và hồi quy. Mô hình hoạt động dựa trên nguyên tắc xây dựng nhiều mô hình phân loại hoặc hồi quy yếu, sau đó kết hợp kết quả của các mô hình này để cải thiện hiệu quả.

Trong quá trình xây dựng các mô hình phân loại hoặc hồi quy yếu, Bagging sẽ lấy ngẫu nhiên các mẫu dữ liệu từ tập dữ liệu huấn luyện. Điều này giúp giảm thiểu mức độ overfitting của các mô hình yếu và của mô hình tổng thể.

Ưu điểm của mô hình Bagging
-	Độ chính xác cao: Bagging thường có độ chính xác cao, đặc biệt là trong các bài toán phân loại với dữ liệu phức tạp.
-	Kháng overfitting: Bagging có khả năng kháng overfitting tốt hơn so với các thuật toán học máy khác.
-	Dễ triển khai: Bagging có cấu trúc đơn giản, dễ triển khai và có thể được sử dụng trong nhiều lĩnh vực khác nhau.
Nhược điểm của mô hình Bagging
-	Yêu cầu nhiều bộ nhớ: Bagging có thể yêu cầu nhiều bộ nhớ để lưu trữ các mô hình phân loại hoặc hồi quy yếu.
-	Tốn kém về mặt tính toán: Bagging có thể tốn kém về mặt tính toán, đặc biệt là đối với các tập dữ liệu lớn.



[mohinh_decu](https://github.com/user-attachments/assets/78cd9d5d-321b-4bb0-90a7-4dc24b865de3)


## 4. Cấu hình máy tính
- Sử dụng google colab
## 5. Huấn luyện mô hình
### 5.1. KNN
Thuật toán K-Nearest Neighbors (KNN) là một phương pháp phân loại dựa trên việc đo khoảng cách giữa các điểm dữ liệu. Để dự đoán nhãn cho một điểm dữ liệu mới, KNN tiến hành như sau:

Đầu tiên, KNN tính khoảng cách từ điểm dữ liệu mới này đến tất cả các điểm dữ liệu đã có trong tập huấn luyện. Khoảng cách này thường được đo bằng công thức Euclid hoặc các phương pháp đo lường khác, tùy thuộc vào yêu cầu bài toán.

![image](https://github.com/user-attachments/assets/1da0be6c-68b5-46a3-9aa6-e54a6ddf27c2)

Sau khi tính toán xong các khoảng cách, KNN chọn ra k điểm gần nhất với điểm dữ liệu mới. k là một tham số mà người dùng có thể điều chỉnh, thường là một số lẻ để tránh tình huống hòa phiếu (dùng grid search để tìm k).

![image]()

Kết quả dùng Grid Search cho thấy k= ... có độ chính xác tốt nhất.

Tiếp theo, KNN sẽ kiểm tra nhãn của k điểm lân cận vừa chọn. Các nhãn này sẽ tiến hành “bầu chọn” cho điểm dữ liệu mới. Nhãn nào chiếm đa số trong k điểm lân cận sẽ là nhãn dự đoán cho điểm dữ liệu mới.

### 5.2. Cây quyết định
Cây quyết định (Decision Tree) là một mô hình phân loại và hồi quy hoạt động dựa trên việc phân chia dữ liệu thành các nhánh, giúp đưa ra quyết định hoặc dự đoán dễ dàng hơn. Cây quyết định hoạt động như sau:

Mô hình sẽ xem xét tất cả các đặc trưng (features) của dữ liệu và chọn ra đặc trưng phân chia dữ liệu tốt nhất. Việc lựa chọn đặc trưng này dựa trên các chỉ số đo lường như chỉ số Gini hoặc Entropy. Những chỉ số này giúp xác định mức độ "thuần" của mỗi nhánh, giúp giảm độ không chắc chắn trong phân loại.

![image](https://github.com/user-attachments/assets/ff8641f3-1779-4b3b-aa28-cfe91a090a01)


Sau khi chọn được đặc trưng tốt nhất, cây quyết định sẽ chia dữ liệu thành các nhánh con dựa trên giá trị của đặc trưng này. Mỗi nhánh con tương ứng với một nhóm dữ liệu có giá trị đặc trưng tương ứng, nhằm mục tiêu làm cho dữ liệu trong mỗi nhánh đồng nhất hơn về nhãn.

Quá trình phân chia này tiếp tục lặp lại cho từng nhánh con. Với mỗi nhánh, mô hình lại chọn đặc trưng tốt nhất và tiếp tục chia cho đến khi đạt một trong các điều kiện dừng.

Để tối ưu hiệu suất của cây quyết định, Grid Search được sử dụng nhằm tìm ra các giá trị tốt nhất cho các tham số quan trọng của mô hình, như độ sâu tối đa của cây hoặc số lượng mẫu tối thiểu trong mỗi nhánh. Các tham số không nằm trong quá trình tìm kiếm tối ưu sẽ được giữ nguyên ở giá trị mặc định.

### 5.3. Rừng ngẫu nhiên (Random Forest)
Mô hình hoạt động theo cơ chế tạo ra nhiều cây quyết định. Cách xây dựng mỗi cây quyết định như sau:

Dùng kỹ thuật Bootstrapping để lấy tập n dữ liệu từ tập dữ liệu ban đầu. Từ tập n dữ liệu này, chỉ chọn ngẫu nhiên ở k thuộc tính (k<n), tức lúc này sẽ có bộ dữ liệu mới gồm n dữ liệu và mỗi dữ liệu có k thuộc tính. 

Dùng thuật toán decision tree để xây dựng cây quyết định với bộ dữ liệu vừa tạo. 

Ở bước dự đoán, với mỗi dữ liệu mới sẽ test với từng cây quyết định ở trên, kết quả cuối cùng được tổng hợp từ kết quả của các cây quyết định (vote).

Để đạt được hiệu suất tốt nhất, có thể dùng Grid Search để tìm các giá trị tham số phù hợp cho Random Forest. Tuy nhiên, do Random Forest là mô hình phức tạp và gồm nhiều cây quyết định khác nhau, Grid Search không phải lúc nào cũng tối ưu hóa tốt. Trong một số trường hợp, các tham số mặc định đã có thể mang lại kết quả tốt và ít tốn tài nguyên hơn


### 5.4. Bagging
Bagging sử dụng kỹ thuật Bootstrapping để tạo ra các tập dữ liệu khác nhau từ tập dữ liệu ban đầu. Mỗi tập dữ liệu mới được tạo bằng cách lấy mẫu ngẫu nhiên có lặp lại từ tập dữ liệu gốc, và mỗi mẫu sẽ có kích thước bằng với kích thước của tập dữ liệu ban đầu. Mỗi cây quyết định trong Bagging sử dụng tất cả các đặc trưng có sẵn để huấn luyện mô hình.

Đối với dự đoán, Bagging sẽ cho mỗi dữ liệu mới đi qua tất cả các mô hình con (các cây quyết định). Sau đó, kết quả cuối cùng được xác định bằng cách bỏ phiếu đa số (voting) cho các mô hình phân loại hoặc tính trung bình nếu là mô hình hồi quy.

## 6. Đánh giá mô hình
Trong quá trình phát triển mô hình phân loại, việc đánh giá hiệu suất là một bước quan trọng để đảm bảo rằng mô hình không chỉ học từ dữ liệu đào tạo mà còn có khả năng dự đoán chính xác trên dữ liệu mới. 

Có nhiều chỉ số quan trọng được sử dụng để đánh giá mô hình, trong đó F1 Score, Recall, Accuracy, và Precision đóng vai trò quan trọng, mang lại cái nhìn đa chiều về hiệu suất của mô hình.
-	Accuracy, mặc dù là một chỉ số phổ biến, nhưng cũng cần phải được xem xét một cách cẩn thận. Nó đo lường tỷ lệ giữa số lượng dự đoán đúng và tổng số mẫu, nhưng không nhất thiết là lựa chọn tốt nhất đối với dữ liệu mất cân bằng, vì nó có thể bị ảnh hưởng bởi sự thiên lệ của mô hình đối với lớp đa số.
-	Precision, hoặc độ chính xác của dự đoán tích cực, tập trung vào việc đo lường khả năng của mô hình trong việc không tạo ra quá nhiều dự đoán sai tích cực. Nếu mục tiêu là giảm False Positives, Precision trở nên quan trọng.
-	Recall, hay còn gọi là độ nhớ, tập trung vào việc đo lường khả năng của mô hình trong việc bao quát tất cả các trường hợp tích cực. Nếu mục tiêu là đảm bảo không bỏ sót những trường hợp quan trọng, Recall trở nên quan trọng, vì nó đo lường tỷ lệ của các dự đoán tích cực đúng so với tổng số thực sự tích cực.
-	F1 Score, một chỉ số tổng hợp của Precision và Recall, là một phép đo hiệu suất toàn diện. F1 Score thích hợp cho các tình huống mô hình đối mặt với dữ liệu mất cân bằng, nơi sự kết hợp giữa việc giảm False Positives và False Negatives là quan trọng. Nó là một con số duy nhất có thể đo lường cân bằng giữa độ chính xác của mô hình trong việc dự đoán tích cực và khả năng tìm ra tất cả các trường hợp tích cực.

### 6.1. Kết quả của các mô hình
### 6.2. Đánh giá chi tiết từng mô hình

## 7. PHẦN KẾT LUẬN
### 7.1. Kết quả đạt được
### 7.2. Hướng phát triển
# TÀI LIỆU THAM KHẢO
- [1]. Đỗ Thanh Nghị, Phạm Nguyên Khang, Giáo trình nguyên lý máy học, Đại học Cần Thơ, Cần Thơ, 2012.
- [2]. Slide bài giảng học phần Máy Học Ứng Dụng CT294 – Thầy Mã Trường Thành (Trường CNTT & TT).
## DATASETS
1. https://github.com/nisha077/ARP-SDN-Dataset
2. https://data.mendeley.com/datasets/yxzh9fbvbj/2
3. kaggie
   [image](https://github.com/user-attachments/assets/a7fc59a0-1b52-4ff2-91fc-2fb19a9652f8)
4. [OPML](https://www.openml.org/search?type=data&status=any&sort=runs&id=4534)
5. [kitsune-mitm-test](https://www.kaggle.com/code/smeyra/kitsune-mitm-test)
6. [kitsune-mitm-attack-detection](https://www.kaggle.com/code/smeyra/kitsune-mitm-attack-detection)
7. [MITM (IoT)](https://link.springer.com/article/10.1007/s43926-025-00104-w#Abs1)

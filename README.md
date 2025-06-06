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

Giải thuật k láng giềng (kNN) được Fix và Hodges đề xuất từ những năm 1952. Đây là phương pháp rất đơn giản nhưng cũng cho hiệu quả cao trong khai mỏ dữ liệu (Hastie et al., 2009; Wu and Kumar, 2009). Giải thuật kNN không có quá trình học. Khi dự đoán giá trị biến phụ thuộc của phần tử dữ liệu x mới đến, giải thuật đi tìm k láng giềng (k=1, 2, ...) của x từ tập dữ liệu học là các phần tử {(x1,y1), ..., (xk,yk)}, sau đó thực hiện hồi quy với giá trị trung bình của các {y1, ..., yk}. 
Quá trình tìm k láng giềng của mẫu mới thường sử dụng khoảng cách Euclidean được định nghĩa như sau:

![image](https://github.com/user-attachments/assets/192e7d9b-a54a-45c8-adaf-630fa0ba781a)

,trong đó:  x^(a )và x^b là 2 mẫu độc lập.
#### 3.2.2.	Cây Quyết định (Decision Tree):
![image](https://github.com/user-attachments/assets/826f10df-5705-4126-83eb-f8140844d437)

Giải thuật học từ dữ liệu là quá trình xây dựng cây bắt đầu từ nút gốc đến nút lá. Đây là giải thuật đệ quy phân hoạch tập dữ liệu theo các biến độc lập thành các phân vùng chữ nhật rời nhau mà ở đó các phần tử dữ liệu xi, xj, ..., xk của cùng phân vùng (nút lá) có các yi, yj, ..., yk là thuần khiết:
Giống nhau trong vấn đề phân lớp,
Tương tự nhau trong vấn đề hồi quy. 
Mô hình cây quyết định sau khi xây dựng thường không mạnh với nhiễu, có tính tổng quát thấp, chỉ cần dữ liệu kiểm tra có thay đổi một ít so với dữ liệu học thì cây quyết định dự báo sai.
#### 3.2.3.	Rừng Ngẫu nhiên (Random Forest):
![image](https://github.com/user-attachments/assets/9afefea4-4af0-4f62-a475-ccbcacaccea5)

Đây là một mô hình ensemble dựa trên việc kết hợp nhiều cây quyết định, giúp tăng cường độ chính xác và khả năng khái quát hóa của mô hình. 

Rừng ngẫu nhiên sử dụng một tập hợp cây quyết định độc lập, tạo thành từ các mẫu dữ liệu và tập con của các thuộc tính ngẫu nhiên.

Sau đó, dự đoán của các cây được tổng hợp bằng cách bỏ phiếu hoặc tính trung bình (tuỳ thuộc vào bài toán phân loại hay hồi quy), giúp tạo ra một mô hình mạnh mẽ và ít nhạy cảm với quá khớp.

#### 3.2.4.	Bagging (Bootstrap Aggregating):
![image](https://github.com/user-attachments/assets/71f3c81e-649e-4451-bd13-fbb3ae239f06)


Bagging là một kỹ thuật trong học máy, thường dùng để cải thiện độ chính xác và giảm thiểu hiện tượng quá khớp (overfitting) của mô hình.

Kỹ thuật này tạo ra nhiều mẫu dữ liệu (bằng cách lấy mẫu ngẫu nhiên với thay thế) từ tập huấn luyện ban đầu và huấn luyện các mô hình riêng biệt trên mỗi mẫu này. Sau đó, dự đoán cuối cùng được lấy trung bình hoặc theo đa số từ các mô hình thành phần. 


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

### 5.3. Rừng ngẫu nhiên
Mô hình hoạt động theo cơ chế tạo ra nhiều cây quyết định. Cách xây dựng mỗi cây quyết định như sau:

Dùng kỹ thuật Bootstrapping để lấy tập n dữ liệu từ tập dữ liệu ban đầu. Từ tập n dữ liệu này, chỉ chọn ngẫu nhiên ở k thuộc tính (k<n), tức lúc này sẽ có bộ dữ liệu mới gồm n dữ liệu và mỗi dữ liệu có k thuộc tính. 

Dùng thuật toán decision tree để xây dựng cây quyết định với bộ dữ liệu vừa tạo. 

Ở bước dự đoán, với mỗi dữ liệu mới sẽ test với từng cây quyết định ở trên, kết quả cuối cùng được tổng hợp từ kết quả của các cây quyết định (vote).

Để đạt được hiệu suất tốt nhất, có thể dùng Grid Search để tìm các giá trị tham số phù hợp cho Random Forest. Tuy nhiên, do Random Forest là mô hình phức tạp và gồm nhiều cây quyết định khác nhau, Grid Search không phải lúc nào cũng tối ưu hóa tốt. Trong một số trường hợp, các tham số mặc định đã có thể mang lại kết quả tốt và ít tốn tài nguyên hơn


### 5.4. Bagging
Bagging sử dụng kỹ thuật Bootstrapping để tạo ra các tập dữ liệu khác nhau từ tập dữ liệu ban đầu. Mỗi tập dữ liệu mới được tạo bằng cách lấy mẫu ngẫu nhiên có lặp lại từ tập dữ liệu gốc, và mỗi mẫu sẽ có kích thước bằng với kích thước của tập dữ liệu ban đầu. Mỗi cây quyết định trong Bagging sử dụng tất cả các đặc trưng có sẵn để huấn luyện mô hình.

Đối với dự đoán, Bagging sẽ cho mỗi dữ liệu mới đi qua tất cả các mô hình con (các cây quyết định). Sau đó, kết quả cuối cùng được xác định bằng cách bỏ phiếu đa số (voting) cho các mô hình phân loại hoặc tính trung bình nếu là mô hình hồi quy.

## 6. Đánh giá mô hình
### 6.1. Kết quả của các mô hình
### 6.2. Đánh giá chi tiết từng mô hình

## 7. PHẦN KẾT LUẬN
### 7.1. Kết quả đạt được
### 7.2. Hướng phát triển
# TÀI LIỆU THAM KHẢO
## DATASETS
1. https://github.com/nisha077/ARP-SDN-Dataset
2. https://data.mendeley.com/datasets/yxzh9fbvbj/2
3. kaggie
   [image](https://github.com/user-attachments/assets/a7fc59a0-1b52-4ff2-91fc-2fb19a9652f8)
4. [OPML](https://www.openml.org/search?type=data&status=any&sort=runs&id=4534)


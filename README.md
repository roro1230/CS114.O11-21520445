![image](https://github.com/roro1230/CS114.O11-21520445/blob/fdb46864a5ae1f78fce3c082995a15e9e2db0415/UIT-Image.png)


## **TRƯỜNG ĐẠI HỌC CÔNG NGHỆ THÔNG TIN**

## **ĐỒ ÁN CUỐI KỲ MÔN MÁY HỌC - CS114.O11**

## **ĐỒ ÁN: MOTOBIKE NUMBER LICENSE PLATE RECOGNITION**

### Lớp: CS114.O11

### Giảng viên: TS. Lê Đình Duy, ThS. Phạm Nguyễn Trường An

### Thành viên nhóm:

Lê Minh Quang - 21522510

Nguyễn Hồng Thái - 21520445

Nguyễn Duy Hưng - 21520894

#### 1. Mô tả bài toán  
Đề tài tự động nhận diện và nhận dạng các ký tự trên biển số xe máy từ các hình ảnh chụp hoặc video.

##### 1.2. Input và output của bài toán  
- Input: Dataset bao gồm ảnh chứa biển số xe ở bãi giữ xe UIT. Mỗi ảnh là chứa 1 biển số xe được chụp chính diện ở trung tâm bức hình.  
- Output: Vị trí của biển số xe được ghi nhận (được xác định bằng bounding box bởi 2 tọa độ (x1,y1) và (x2,y2) tương ứng góc trái trên và góc phải dưới) và chuỗi kí tự trên biển số xe đó.

##### 1.3. Các thuật toán máy học mà đồ án sử dụng  
Trong bài báo cáo, nhóm sẽ sử dụng mô hình Inception-ResNet-v2 cho đề tài. Sau khi qua các bước xử lý dữ liệu và trích chọn đặc trưng, data được xử lý sẽ đưa vào mô hình classification và sau cùng đánh giá mô hình bằng IOU và giá trị của các metrics: accuracy, precision, recall và f1-score.

##### 1.4. Các tiêu chí về một mô hình được đánh giá tốt  
Tiêu chí mà nhóm sử dụng để đánh giá một mô hình có thể xem là tốt đó là:  
- f1-score cao: f1- score là giá trị trung bình điều hòa của precision và recall. Hiểu một cách đơn giản, f1-score cân bằng hai giá trị precision và recall. Đôi khi trong một số trường hợp, tập dữ liệu quá nghiêng về trường hợp positive, giá trị precision sẽ cao nhưng recall thấp, và ngược lại. Hiện tượng này thường được đề cập với tên gọi precision-recall trade-off. Do đó, để tránh việc này, f1-score phải cao thì mới tương ứng với precision cao và recall cao.  
- IOU: Mô hình tốt là khi IOU có giá trị ?

#### 2. Tập dữ liệu  
- Dữ liệu được thu thập thủ công ở bãi giữ xe UIT.  
- Bộ dataset là ảnh các biển số xe, chúng em tiến hành chụp ảnh bằng điện thoại thu được một dataset có 348 ảnh, các ảnh có tính chất là đều có thể nhìn rõ và đọc được các chữ và số ghi trên biển số. Mỗi ảnh có kích thước là 4000x2250px (width x height).  
- Các ảnh sau khi được thu thập sẽ được đổi tên theo định dạng S*.jpg (với * chạy từ 1 đến 348) (VD: 29-S1 503 88.jpg). Sau đó tụi em tiến hành label các ảnh này bằng công cụ LabelImg để xác định bounding box và thể hiện qua file xml.  
- Thông tin trong một file xml bao gồm có tên folder nằm trong thẻ <folder>, tên của ảnh nằm trong thẻ <filename>, đường dẫn đến ảnh nằm trong thẻ <path>. Những thông tin này cho biết nguồn gốc của ảnh được label. Thông tin quan trọng nhất nằm trong thẻ <object> gồm có thẻ <name> lưu trữ tên của object với bounding box được label, và thẻ <bndbox> lưu trữ giá trị bounding box của object trong đó các giá trị (<xmin>, <ymin>), (<xmax>, <ymax>) lần lượt là giá trị tọa độ gốc trên bên trái và gốc dưới bên phải của bounding box.
  
#### 3. Mô tả về đặc trưng + feature engineering
 
#### 4. Mô tả thuật toán máy học  
- Inception-ResNet-v2

#### 5. Đánh giá kết quả, kết luận: Kết quả f1-score cùng với IOU:

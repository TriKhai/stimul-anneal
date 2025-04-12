# Simulated Annealing (SA)

**Simulated Annealing** là một thuật toán tìm kiếm được sử dụng trong tối ưu hóa để tìm ra giá trị tối ưu hoặc gần tối ưu cho một bài toán.

## Simulated Annealing (SA) là gì?

Simulated Annealing là một thuật toán mô phỏng quá trình làm nguội kim loại để tìm ra điểm tối ưu toàn cục (global optimum) trong một không gian giải pháp rộng. Thuật toán này được lấy cảm hứng từ quá trình làm nguội kim loại (annealing) trong vật lý, trong đó vật liệu được làm nóng đến một nhiệt độ cao và sau đó được làm nguội dần dần để giảm độ căng thẳng và đạt cấu trúc ổn định.

## Cách hoạt động của Simulated Annealing:

1. **Khởi tạo**: Bắt đầu với một giải pháp ngẫu nhiên.
2. **Thử các thay đổi nhỏ**: Tạo ra các giải pháp hàng xóm (neighboring solutions) bằng cách thay đổi một số yếu tố trong giải pháp hiện tại.
3. **Chấp nhận giải pháp mới**:
   - Nếu giải pháp mới tốt hơn giải pháp hiện tại, thì chấp nhận giải pháp mới.
   - Nếu giải pháp mới tệ hơn, có thể chấp nhận giải pháp mới với một xác suất nhất định, xác suất này giảm dần theo thời gian (giống như quá trình làm nguội).
4. **Giảm "nhiệt độ"**: Cứ sau mỗi vòng lặp, "nhiệt độ" của hệ thống giảm dần, làm cho xác suất chấp nhận giải pháp kém đi. Điều này giúp thuật toán dần dần "lắng xuống" và tìm ra một giải pháp ổn định (tối ưu).
5. **Kết thúc**: Khi nhiệt độ quá thấp hoặc đạt đến số vòng lặp tối đa, thuật toán dừng lại và trả về giải pháp tìm được.

# Áp dụng Simulated Annealing vào Traveling Salesman Problem (TSP)

**Traveling Salesman Problem (TSP)** yêu cầu tìm lộ trình ngắn nhất sao cho người bán hàng (salesman) thăm tất cả các thành phố một lần và trở lại điểm xuất phát. Đây là một bài toán NP-hard, và **Simulated Annealing** có thể được áp dụng để giải quyết bài toán này.

## Các bước áp dụng Simulated Annealing vào TSP

### 1. **Khởi tạo giải pháp ngẫu nhiên**
   - Bắt đầu với một lộ trình ngẫu nhiên, tức là một chuỗi các thành phố được tham quan lần lượt.
   - Tính toán tổng quãng đường của lộ trình này.

### 2. **Tạo giải pháp hàng xóm (Neighboring Solution)**
   - Thực hiện thay đổi nhỏ trên lộ trình hiện tại. Một cách phổ biến là **hoán đổi** vị trí của hai thành phố trong lộ trình (swap two cities).
   - Điều này sẽ tạo ra một giải pháp gần giống với lộ trình hiện tại, giúp thuật toán tìm kiếm các lộ trình tốt hơn.

### 3. **Chấp nhận giải pháp mới**
   - Nếu lộ trình mới có tổng quãng đường ngắn hơn, chấp nhận giải pháp mới.
   - Nếu lộ trình mới có tổng quãng đường dài hơn, chấp nhận giải pháp đó với một xác suất `P` được tính theo công thức:

     \[
     P = \exp\left(\frac{-\Delta E}{T}\right)
     \]

     - `ΔE` là sự thay đổi trong độ dài lộ trình (quãng đường), tức là sự khác biệt giữa lộ trình cũ và lộ trình mới.
     - `T` là nhiệt độ, giá trị này giảm dần qua các vòng lặp.

### 4. **Giảm nhiệt độ (Cooling Schedule)**
   - Nhiệt độ sẽ giảm dần sau mỗi vòng lặp. Một cách đơn giản để giảm nhiệt độ là nhân nó với một hệ số nhỏ hơn 1 (ví dụ: `T = T * alpha`, với `alpha` là một hằng số từ 0.95 đến 0.99).

### 5. **Lặp lại quá trình**
   - Lặp lại quá trình này cho đến khi nhiệt độ quá thấp hoặc đạt đến số vòng lặp tối đa.
   - Khi quá trình kết thúc, thuật toán sẽ trả về lộ trình ngắn nhất tìm được.

## **Ưu điểm của Simulated Annealing trong TSP**
   - **Khả năng thoát khỏi cực trị địa phương**: Nhờ cơ chế chấp nhận giải pháp tệ hơn với xác suất, thuật toán có thể thoát khỏi các cực trị địa phương và tìm kiếm giải pháp toàn cục tốt hơn.
   - **Tính linh hoạt**: Không cần phải biết trước cấu trúc của bài toán, có thể áp dụng cho nhiều bài toán tối ưu hóa khác nhau.

## **Lưu ý khi áp dụng**
   - **Chọn lịch làm nguội (Cooling Schedule) hợp lý**: Việc giảm nhiệt độ quá nhanh có thể khiến thuật toán bị kẹt ở cực trị địa phương. Ngược lại, giảm nhiệt độ quá chậm có thể làm chậm quá trình tìm kiếm.
   - **Điều chỉnh các tham số**: Nhiệt độ ban đầu, hệ số giảm nhiệt độ (`alpha`), và số vòng lặp có thể ảnh hưởng lớn đến kết quả.


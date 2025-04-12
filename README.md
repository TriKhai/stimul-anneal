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

## Ứng dụng của Simulated Annealing:

Simulated Annealing thường được sử dụng trong các bài toán tối ưu hóa phức tạp như:
- Tối ưu hóa hàm mục tiêu (objective function)
- Tối ưu hóa đường đi trong các bài toán như **TSP (Traveling Salesman Problem)**.
- Tìm kiếm các cấu trúc tốt nhất trong các bài toán kết cấu, như tối ưu hóa thiết kế.

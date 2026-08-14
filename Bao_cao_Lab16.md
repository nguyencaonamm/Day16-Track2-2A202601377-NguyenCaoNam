# Báo cáo kết quả Lab 16 - LightGBM trên CPU Node (t3.micro)

**1. Môi trường triển khai:**
- Nền tảng: AWS
- Công cụ triển khai: Terraform
- Cấu hình Compute Node: `t3.micro` (Do giới hạn tài khoản Free Tier)

**2. Kết quả đo đạc (Benchmark):**
- Thời gian tải dữ liệu (hơn 284.000 dòng): 2.38 giây
- Thời gian huấn luyện (100 cây quyết định): 4.67 giây
- Độ chính xác tổng thể (Accuracy): 99.83%
- Điểm AUC-ROC: 0.8203
- Tốc độ dự đoán (Inference throughput - 1000 dòng): 0.0060 giây
- Độ trễ dự đoán 1 dòng: 1.56 ms

**3. Nhận xét:**
Việc huấn luyện bộ dữ liệu Credit Card Fraud trên cấu hình máy chủ CPU nhỏ bé diễn ra vô cùng mượt mà. Mặc dù bộ dữ liệu bị mất cân bằng nghiêm trọng (imbalanced), mô hình LightGBM vẫn đạt độ chính xác cực cao (Accuracy ~99.8%) và tốc độ dự đoán ấn tượng (xử lý 1000 dòng chỉ trong 6 mili-giây). Điều này chứng minh rằng với các bài toán dữ liệu dạng bảng (tabular data), một máy chủ CPU cơ bản hoàn toàn có thể đáp ứng xuất sắc yêu cầu huấn luyện và suy luận mà không cần phải sử dụng đến GPU đắt đỏ.

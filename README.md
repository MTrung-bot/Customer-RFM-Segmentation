# 🛍️ Customer Segmentation with RFM Analysis

## 📌 Mục tiêu dự án
- Phân tích hành vi khách hàng dựa trên dữ liệu giao dịch mua hàng.
- Tính toán các chỉ số RFM: **Recency, Frequency, Monetary** để đánh giá giá trị của từng khách hàng.
- Phân nhóm khách hàng thành các nhóm: **VIP**, **nguy cơ rời bỏ**, **chi tiêu cao**, **khác**...
- Trực quan hóa trên Power BI → phục vụ **marketing, chăm sóc khách hàng & tối ưu hiệu suất bán hàng**.

## 📁 Nguồn dữ liệu
- Dataset: [E-Commerce Behavior Data (Kaggle)](https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store)
- Dung lượng: 2.7 GB
- Bao gồm các trường:
  - `event_time`, `event_type`, `user_id`, `product_id`, `price`, `category`, `brand`,...

## 🛠️ Công cụ & kỹ thuật
- Python (Pandas, NumPy, datetime)
- Power BI
- RFM Analysis
- Data Modeling (Power BI)
- Git & GitHub

---

## 🔄 Quy trình thực hiện

### 1. Tiền xử lý dữ liệu (Python)
- Gộp dữ liệu từ các tháng (`2019-Oct.csv`, `2019-Nov.csv`)
- Chuyển đổi định dạng thời gian, lọc các dòng có `event_type = "purchase"`
- Loại bỏ dòng thiếu thông tin: `user_id`, `price`

### 2. Tính toán RFM
- Recency: số ngày từ giao dịch gần nhất đến ngày snapshot
- Frequency: số lần giao dịch
- Monetary: tổng chi tiêu

### 3. Gán điểm RFM và phân nhóm khách hàng
- Gán điểm từ 1–5 cho từng chỉ số bằng `qcut`
- Tạo cột `RFM_Score`
- Dựa trên logic gán nhóm: VIP, Chi tiêu cao, Rời bỏ, Khác,...

### 4. Trực quan hóa với Power BI
- Tạo bảng thời gian & mô hình liên kết
- Tạo biểu đồ:
  - Bar chart: số lượng khách theo `RFM_Score`, theo `Customer_Type`
  - Matrix table: chi tiết từng khách hàng (RFM, nhóm)
  - KPI card: tổng KH, số KH VIP, doanh thu trung bình
  - Slicer: lọc theo nhóm KH, điểm R/F/M

---

## 📊 Giao diện Dashboard (Power BI)
> (Chèn ảnh Power BI dashboard tại đây nếu có)

---
![Screenshot 2025-06-23 185108](https://github.com/user-attachments/assets/810dfbbd-f43b-4404-97f4-3c3175bcc7e5)

## 📁 Cấu trúc thư mục

```bash
rfm-customer-analysis/
│
├── data/
│   ├── 2019-Oct.csv
│   └── 2019-Nov.csv
│
├── notebooks/
│   └── rfm_analysis_notebook.ipynb
│
├── dashboards/
│   └── rfm_model.pbix
│
├── reports/
│   ├── rfm_report.pdf
│   └── rfm_presentation.pptx
│
├── README.md
└── requirements.txt


# data-warehouse-etl-pipeline
Khung quy trình ETL toàn diện cho tích hợp dữ liệu CUKCUK: Raw → Staging → Data Warehouse.
# 🏗️ Multi-Source Data Warehouse ETL Framework

> **Framework ETL tổng quát cho nhiều nguồn dữ liệu: CUKCUK, CNV, và các hệ thống khác**

## 📋 Tổng quan

Repository này chứa framework ETL tổng quát để xây dựng data warehouse từ **nhiều nguồn dữ liệu khác nhau**, bao gồm:

- 🍴 **CUKCUK API**: Dữ liệu nhà hàng (invoices, employees, products)
- 📊 **CNV System**: Dữ liệu kinh doanh và vận hành  
- 🏦 **Banking APIs**: Dữ liệu giao dịch tài chính
- 📱 **Mobile Apps**: User behavior và analytics
- 🗄️ **Legacy Systems**: Dữ liệu từ các hệ thống cũ
- 🔌 **Custom APIs**: Các nguồn dữ liệu nội bộ khác

### 🎯 Mục tiêu
- **Chuẩn hóa** quy trình ETL cho mọi nguồn dữ liệu trong công ty
- **Tự động hóa** việc đồng bộ từ multiple sources
- **Thống nhất** cấu trúc dữ liệu từ các hệ thống khác nhau
- **Scalable** framework có thể mở rộng cho nguồn dữ liệu mới
- **Tăng tốc** việc onboard hệ thống mới vào data warehouse



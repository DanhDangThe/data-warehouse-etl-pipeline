# data-warehouse-etl-pipeline
Khung quy trình ETL toàn diện cho tích hợp dữ liệu CUKCUK: Raw → Staging → Data Warehouse.
🏗️ Multi-Source Data Warehouse ETL Framework

Framework ETL tổng quát cho nhiều nguồn dữ liệu: CUKCUK, CNV, và các hệ thống khác

📋 Tổng quan
Repository này chứa framework ETL tổng quát để xây dựng data warehouse từ nhiều nguồn dữ liệu khác nhau, bao gồm:

🍴 CUKCUK API: Dữ liệu nhà hàng (invoices, employees, products)
📊 CNV System: Dữ liệu kinh doanh và vận hành
🏦 Banking APIs: Dữ liệu giao dịch tài chính
📱 Mobile Apps: User behavior và analytics
🗄️ Legacy Systems: Dữ liệu từ các hệ thống cũ
🔌 Custom APIs: Các nguồn dữ liệu nội bộ khác

🎯 Mục tiêu

Chuẩn hóa quy trình ETL cho mọi nguồn dữ liệu trong công ty
Tự động hóa việc đồng bộ từ multiple sources
Thống nhất cấu trúc dữ liệu từ các hệ thống khác nhau
Scalable framework có thể mở rộng cho nguồn dữ liệu mới
Tăng tốc việc onboard hệ thống mới vào data warehouse

🏛️ Architecture
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│  CUKCUK API     │───▶│                 │    │                 │    │                 │
├─────────────────┤    │   Raw Tables    │───▶│ Staging Tables  │───▶│ Data Warehouse  │
│    CNV API      │───▶│   (MySQL)       │    │   (MySQL)       │    │  (ClickHouse)   │
├─────────────────┤    │                 │    │                 │    │                 │
│  Banking API    │───▶│  • cukcuk_raw   │    │ • cukcuk_staging│    │ • dim_products  │
├─────────────────┤    │  • cnv_raw      │    │ • cnv_staging   │    │ • dim_customers │
│   Mobile App    │───▶│  • banking_raw  │    │ • banking_staging│   │ • fact_sales    │
├─────────────────┤    │  • mobile_raw   │    │ • mobile_staging│    │ • fact_finance  │
│  Legacy Systems │───▶│  • legacy_raw   │    │ • legacy_staging│    │ • fact_behavior │
└─────────────────┘    └─────────────────┘    └─────────────────┘    └─────────────────┘
        │                       │                       │                       │
        │               ┌───────▼───────┐       ┌───────▼───────┐       ┌───────▼───────┐
        │               │  Multi-Source │       │   Unified     │       │   Business    │
        └──────────────▶│  Raw Storage  │──────▶│  Data Model   │──────▶│  Intelligence │
                        │               │       │               │       │  (Superset)   │
                        └───────────────┘       └───────────────┘       └───────────────┘
🔄 Multi-Source Data Flow

Source Connectors: n8n workflows cho từng data source
Raw Ingestion: Lưu dữ liệu thô theo source-specific schema
Standardization: Transform sang unified staging format
Integration: Combine data từ multiple sources
Analytics: Cross-source insights và reporting

🚀 Quick Start
Prerequisites

n8n instance
MySQL 8.0+
ClickHouse 23.0+
Apache Superset
CUKCUK API credentials

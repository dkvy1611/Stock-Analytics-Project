# 📈 Stock Analytics Project

## 🔍 Overview

This project focuses on **stock price forecasting** using historical data from the Vietnamese stock market.

An **end-to-end Machine Learning pipeline** was built to automate the full workflow:

- Daily data extraction
- Time series data cleaning & preprocessing
- Model training and comparison
- Model evaluation and selection

**Data period:** 01/01/2020 – 14/01/2026  
This range allows evaluation across different market trends and conditions.

---

## 📊 Dataset

- **Source:** vnstock API
- **Frequency:** Daily
- **Features:**
  - Open
  - High
  - Low
  - Close
  - Volume

---

## 🏗️ System Architecture

### Data Flow

vnstock API → Airflow → Database → Data Cleaning → Modeling → Evaluation


### Components

- **Docker Compose** – Initialize Airflow & database locally
- **Apache Airflow (DAG)** – Automate daily data extraction
- **Database** – Store raw and processed data
- **Data Processing** – Clean and normalize time series data
- **Modeling** – Train and evaluate forecasting models

---

## 🤖 Models Implemented

- ARIMA
- LSTM
- Ensemble (ARIMA + LSTM)

---

## 📈 Evaluation

- **Metrics:** MSE, RMSE
- **Best Model:** LSTM achieved the lowest MSE and RMSE among all models.

---

## 🛠️ Tech Stack

- Python
- Docker
- Apache Airflow
- vnstock
- Pandas
- Scikit-learn
- TensorFlow / Keras

---

# 🚀 Project Setup

## ⚙️ Requirements

- Docker & Docker Compose
- Python ≥ 3.9
- Git

---

## 📂 Project Structure


### Folder Description

| Folder | File | Description |
|--------|------|------------|
| ETL | `vnstock_update_stock_price_dag.py` | Extract stock price data daily from vnstock API and load into database |
| ETL | `stock_price_cleaning.ipynb` | Clean and preprocess time series data |
| infra | `.env` | Environment variables (database, Airflow config, ETL settings) |
| infra | `docker-compose.yml` | Initialize Airflow and database locally |
| Model | `ARIMA-LSTM.ipynb` | Train and compare ARIMA, LSTM, and Ensemble models |

---

### ▶️ Quy trình chạy dự án

| Bước | Thực hiện | Mô tả |
|------|-----------|-------|
| 1 | `docker-compose up -d` | Khởi tạo Airflow và database local |
| 2 | Mở Airflow UI | Truy cập `http://localhost:8080` |
| 3 | Trigger DAG | Chạy DAG `once_time_stock_dag` để trích xuất dữ liệu từ vnstock API |
| 4 | Chạy notebook cleaning | Mở `stock_price_cleaning.ipynb` để làm sạch và xử lý dữ liệu |
| 5 | Train & evaluate model | Chạy `ARIMA-LSTM.ipynb` để huấn luyện và đánh giá mô hình |

---

### 🔄 Luồng xử lý dữ liệu

| Thứ tự | Thành phần | Vai trò |
|--------|------------|---------|
| 1 | vnstock API | Cung cấp dữ liệu giá cổ phiếu |
| 2 | Airflow DAG | Điều phối và tự động hóa quá trình ETL |
| 3 | Database | Lưu trữ dữ liệu thô và dữ liệu đã xử lý |
| 4 | Data Cleaning | Chuẩn hóa dữ liệu chuỗi thời gian |
| 5 | Modeling | Huấn luyện và đánh giá mô hình dự báo |


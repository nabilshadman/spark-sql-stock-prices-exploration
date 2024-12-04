# Stock Market Analysis with Spark SQL

An analysis of stock market data for major tech companies (Amazon, Google, Tesla) leveraging Apache Spark SQL and Python. This project demonstrates data manipulation, statistical analysis, and time series exploration using distributed computing capabilities.

## Overview

This project utilizes PySpark and Spark SQL to analyze historical stock market data, demonstrating:
- Distributed data processing with Spark RDDs and DataFrames
- SQL queries and aggregations
- Time-series analysis of stock performance
- Data persistence using Parquet format
- Interactive data exploration in Jupyter notebooks

## Architecture

The project is structured around several key components:
```
.
├── sparksql_stock_prices_exploration_notebook.ipynb    # Main analysis notebook
├── data/
│   ├── AMZN.csv                                        # Amazon historical stock data
│   ├── GOOG.csv                                        # Google historical stock data
│   └── TSLA.csv                                        # Tesla historical stock data
└── README.md
```

## Technical Implementation

### Core Technologies
- Apache Spark 3.x
- PySpark
- Spark SQL
- Jupyter Notebook
- Python 3.x

### Key Features
1. **Data Loading & Transformation**
   - CSV ingestion into Spark DataFrames
   - Schema inference and optimization
   - Data type handling and validation

2. **Analysis Capabilities**
   - Time-series stock price analysis
   - Statistical computations (moving averages, volatility)
   - Cross-company performance comparisons
   - Advanced SQL aggregations

3. **Data Persistence**
   - Parquet file format support
   - Efficient data storage and retrieval
   - Query optimization

## Getting Started

### Prerequisites
- Apache Spark (3.x recommended)
- Python 3.x
- Jupyter Notebook
- Required Python packages:
  ```
  pyspark
  pandas
  numpy
  jupyter
  ```

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/spark-sql-stock-prices-exploration.git
cd spark-sql-stock-prices-exploration
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

3. Launch Jupyter Notebook:
```bash
jupyter notebook
```

4. Open `sparksql_stock_prices_exploration_notebook.ipynb` to start exploring the analysis.

## Usage

The notebook contains several key sections:
1. Data Loading and Preparation
2. Basic Stock Analysis
3. Spark SQL Queries
4. Cross-Company Comparisons
5. Statistical Analysis
6. Data Export and Persistence

Example query for average monthly stock prices:
```python
sqlContext.sql("""
    SELECT year(Date) as year, 
           month(Date) as month, 
           avg(Close) as avg_close 
    FROM stock_prices 
    GROUP BY year, month 
    ORDER BY year, month
""").show()
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Acknowledgments

- Historical stock data provided by Yahoo Finance
- Apache Spark documentation and community
- PySpark documentation

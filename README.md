#Roots Inventory Intelligence Hub
Project Overview

The Roots Inventory Intelligence Hub is a predictive analytics solution designed to address inventory management challenges in retail.

The project focuses on inventory distortion, including stockouts, overstocking, and inefficient replenishment. The solution uses data cleaning, exploratory data analysis, feature engineering, machine learning, and inventory analytics to support better demand forecasting and inventory decisions.

The analysis uses a publicly available supply chain dataset from Kaggle as a proxy for retail inventory operations. The dataset does not represent proprietary Roots Corporation data.

Business Problem

Retail businesses can experience significant inventory challenges when demand, inventory levels, supplier lead times, and replenishment decisions are not effectively connected.

The main business problems addressed in this project are:

* Stockout risk
* Overstocking
* Inventory holding costs
* Inefficient replenishment
* Demand uncertainty
* Promotional demand variation

Analytics Questions

The project addresses five key questions:

1. Can historical sales, inventory, and supplier data be used to forecast demand at the SKU level?
2. Which products are at risk of reaching a stockout condition?
3. What reorder points and safety stock levels can support inventory decisions?
4. How does promotional activity affect demand?
5. Which variables have the greatest influence on demand forecasting?

Dataset

The original dataset contains:

* 91,250 rows
* 15 columns
* 5 SKUs
* 5 warehouses
* 10 suppliers
* 4 geographic regions
* 2024 calendar year

A working dataset of 8,000 records was used for the analysis.

The dataset was intentionally modified with data-quality issues to simulate real-world conditions before applying the cleaning pipeline.

Data Cleaning

The data preparation process included:

* Duplicate detection and removal
* Invalid date handling
* Numeric type conversion
* Missing-value treatment
* Negative-value treatment
* Data validation

The final dataset contained 8,000 clean and analysis-ready records.

Feature Engineering

The feature engineering process expanded the dataset from 15 to 19 features.

New features included:

* Year
* Month
* Day
* Day of Week
* Is Weekend
* Monthly Average Units Sold by SKU
* Sales-to-Inventory Ratio
* Inventory-to-Reorder Gap

These features were designed to capture temporal patterns, inventory utilization, and replenishment conditions.

Exploratory Data Analysis

Key observations included:

* High dispersion in inventory levels, indicating potential overstock risk.
* High demand uncertainty, creating a need for appropriate safety stock.
* Moderate variation in supplier lead times.
* Relatively stable reorder points across SKU-warehouse combinations.
* High variation in order quantities, indicating irregular replenishment patterns.
* Approximately 9.8% of records were associated with promotional activity.

Machine Learning Models

Several models were evaluated:

* Random Forest Regressor
* XGBoost Regressor
* LSTM Neural Network
* Logistic Regression
* Random Forest Classifier

The models were evaluated using metrics such as:

* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)

Model Results

Baseline Demand Forecasting

Model	MAE	RMSE
Random Forest	0.78	7.58
XGBoost	0.99	8.40

Random Forest was selected as the primary forecasting model based on its overall stability and interpretability in the tested scenarios.

Scenario Testing

Scenario	Model	MAE	RMSE
High Inventory	Random Forest	0.61	5.93
High Inventory	XGBoost	0.40	5.45
Promotional	Random Forest	0.53	5.65
Promotional	XGBoost	0.40	6.11

The results show that model performance varied by scenario and evaluation metric. Random Forest demonstrated stable RMSE performance during promotional conditions, while XGBoost achieved lower MAE in the tested scenarios.

Technology Stack

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* Matplotlib
* Seaborn
* MySQL
* SQLAlchemy
* Jupyter Notebook

Solution Architecture

The proposed solution follows four main layers:

1. Data Ingestion and Storage
2. Intelligence and Modeling
3. Presentation and Visualization
4. Reporting and Decision Support

The architecture is designed to connect operational data with predictive analytics and inventory decision-making.

Business Value

The solution demonstrates how predictive analytics can support:

* Demand forecasting
* Stockout risk identification
* Inventory optimization
* Reorder point analysis
* Safety stock planning
* Promotional demand analysis
* Data-driven inventory decisions

Future Improvements

Potential enhancements include:

* Adding external demand drivers such as weather and economic indicators
* Real-time data streaming using Apache Kafka
* Automated model selection
* Prescriptive analytics
* Real-time inventory monitoring
* Integration with enterprise ERP, POS, and SCM systems

Project Files

This repository contains:

* Python/Jupyter Notebook
* Clean supply chain dataset
* Machine-learning-ready dataset
* Model prediction outputs
* Data visualizations
* Project documentation

Conclusion

The Roots Inventory Intelligence Hub demonstrates an end-to-end predictive analytics workflow, from raw data preparation and exploratory analysis to machine learning and inventory decision support.

The project combines Python, SQL, data analytics, machine learning, and business problem-solving to develop a practical approach to retail inventory optimization.

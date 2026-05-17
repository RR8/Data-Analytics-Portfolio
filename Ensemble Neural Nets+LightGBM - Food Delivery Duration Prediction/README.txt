** Project Overview
In this project, I applied advanced data science and machine learning techniques using Python and its data science packages to build a strong prediction model. The project focused on data preprocessing, feature engineering, deep learning, gradient boosting, and ensemble modeling to improve predictive performance and model interpretability.


* Skills and Methods Applied

  1. Data Cleaning and Transformation
Handled missing values, outliers, and inconsistent data


  2. Time Series Decomposition
Decomposed time series data into trend, seasonality, and residual components
Analyzed temporal patterns to improve forecasting accuracy


  3. Feature Engineering
Created meaningful predictive features from raw data


  4. Neural Networks
Applied neural network architectures for predictive tasks

    4.1 Embedding High-Cardinality Features
Utilized embedding layers to efficiently represent categorical variables with large cardinality


  5. LightGBM Modeling
  Built gradient boosting models using LightGBM for high-performance prediction tasks
    
    5.1 LightGBM Optimization
      5.1.1 Feature Importance Analysis
      Evaluated and interpreted feature contributions
      Identified the most influential variables affecting predictions

      5.1.2 Hyperparameter Tuning
      Performed systematic hyperparameter optimization
      Used validation strategies to improve generalization performance


  6. Ensemble Modeling
Combined predictions from neural networks and LightGBM models to achieve more stable and accurate results


  7. Residual Analysis
Analyzed prediction errors and residual distributions
Evaluated model assumptions and identified areas for improvement


** Dataset Overview
The dataset contains a subset of deliveries received at DoorDash in early 2015 in a subset of the cities. Each row in this file corresponds to one unique delivery. There is added noise to the dataset to obfuscate certain business details. Each column corresponds to a feature as explained below. Note all money (dollar) values given in the data are in cents and all time duration values given are in seconds

The target value to predict here is the total seconds value between created_at and actual_delivery_time.


Columns in dataset:

* Time features

market_id: A city/region in which DoorDash operates, e.g., Los Angeles, given in the data as an id
created_at: Timestamp in UTC when the order was submitted by the consumer to DoorDash. (Note this timestamp is in UTC, but in case you need it, the actual timezone of the region was US/Pacific)
actual_delivery_time: Timestamp in UTC when the order was delivered to the consumer


* Store features

store_id: an id representing the restaurant the order was submitted for
store_primary_category: cuisine category of the restaurant, e.g., italian, asian
order_protocol: a store can receive orders from DoorDash through many modes. This field represents an id denoting the protocol
Order features

total_items: total number of items in the order
subtotal: total value of the order submitted (in cents)
num_distinct_items: number of distinct items included in the order
min_item_price: price of the item with the least cost in the order (in cents)
max_item_price: price of the item with the highest cost in the order (in cents)


* Market features
* DoorDash being a marketplace, there is information on the state of marketplace when the order is placed, that can be used to estimate delivery time. The following features are values at the time of created_at (order submission time):

total_onshift_dashers: Number of available dashers who are within 10 miles of the store at the time of order creation
total_busy_dashers: Subset of above total_onshift_dashers who are currently working on an order
total_outstanding_orders: Number of orders within 10 miles of this order that are currently being processed.


* Estimate features
* There are predictions from other models for various stages of delivery process that can be used

estimated_order_place_duration: Estimated time for the restaurant to receive the order from DoorDash (in seconds)
estimated_store_to_consumer_driving_duration: Estimated travel time between store and consumer (in seconds)

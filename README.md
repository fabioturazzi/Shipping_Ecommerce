# Ecommerce Shopping Analysis

## Project Overview
This project aims to study the shipping status from an e-commerce company, aiming to identify and understand late deliveries to improve customer experience. The dataset is obtained from [Kaggle](https://www.kaggle.com/prachi13/customer-analytics), and the analysis notebook is uploaded to [Google Colab](https://colab.research.google.com/drive/1hDEyXAiuXt_i9HjGRUrbZea3SSEiO4mk?authuser=1#scrollTo=rC5cFzL69ZxK)

## Main Method:
- Data Wrangling with pandas
- EDA with seaborn
- Feature Selection and Scaling
- Sample Balancing with RandomOverSampler
- Classification with Machine Learning algorithms, Ensemble Methods, and Artificial Neural Network

## Dataset
The dataset contains 12 columns, with a total of 10999 rows. The target variable is ```Reached.on.Time_Y.N```.

Variable Name | Description | Data Type
--- | --- | ---
ID                  | Unique ID for each shipment |  int64 
Warehouse_block     | Name of warehouse block (A,B,C,D, F) | object
Mode_of_Shipment    | Mode of shipment (Flight, Road, Ship) |  object
Customer_care_calls | Number of calls from customer | int64 
Customer_rating     | Customer's shipment rating (1-5) |  int64 
Cost_of_the_Product | Product's prices |  int64 
Prior_purchases     | Number of previous purchases |  int64 
Product_importance  | Degree of importance (low, medium, high) |  object
Gender              | Customer's gender |  object
Discount_offered    | Discount offered on that specific product |  int64 
Weight_in_gms       | Product's weight in grams |   int64 
Reached.on.Time_Y.N | Whether the shipment arrived as scheduled (0,1) |   int64

## Project Directory
```
| - Shipping_Ecommerce                                        
|   -- data                                                 Contains the raw dataset 
|     --- customer_data.csv
|   -- E-commerce Shipping Analysis - Project Report.pdf    Contains details about the analysis with findings
|   -- E_commerce_shipping_analysis.ipynb                   Contains the source codes
|   -- LICENSE                                              MIT License
|   -- README.md                                            Project Overview
```

## Challenges
As we carried out our feature selecion step, it was apperent that only 2 variables: ```Discount_offered``` and ```Weight_in_gms``` seem to have determining impact on shipment's status. Due to the lack of additional domain knowledge, it is challenging to explain the reasons behind this issue.

However, we can infer that, although the classification task with two independent variables is simpler, it still presents a probabilistic problem that benefits from using Machine Learning. While the simple thresholds of these two variables can be used to flag any potentially delayed order, the fact that we are providing an accurate model that can analyze each case by their specific value and render probabilistic outputs makes this process more efficient and precise. Moreover, our report explores the instrinsic relationship between these variables and other features, presenting the argument that they also carry implicit information regarding Product_importance. 

## Future Considerations:
A final consideration to be made here is that additional inputs to the model would be beneficial, particularly by aggregating data related to the shipment contracts and specifications with the supplier for each order. We believe that this would aid the models in interpreting the impacts of the actual shipping to delivery times. We hypothesize that orders with low discount and “problematic” weight ranges translate to particular shipping contract specifications that reflect a lower priority by the shipment providers. Therefore, including this sort of data would further help improve the results. 

Nevertheless, we believe that our current findings already suffice to address the presented problem. The models used correctly address the matter of identifying potential delays, specially when considering the patterns in our confusion matrix and classification report. Since the model tends to rarely miss the indication of actual delays, most problematic shippings will be successfully flagged to the management.

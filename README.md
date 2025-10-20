Dataset - https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce/data

<img width="2486" height="1496" alt="DBSchema" src="https://github.com/user-attachments/assets/6f6b87b4-4351-497c-a7d4-5c33bc4d1cba" />


# **Predicting Customer Loyalty: Repeat Purchase Model**

**Objective**

The main objective of this project is to build a predictive model to estimate the probability of a customer making a repeat purchase (Repeating_customer) based on order, product, payment, and customer-related features.
This model enables data-driven decision-making in customer retention, marketing optimization, and sales forecasting.


**Feature Set**

The model was trained using the following 15 features that capture product characteristics, customer behavior, delivery experience, and payment preferences:

**Product Attributes:** product_weight_g, product_length_cm, product_height_cm, product_width_cm

**Product Presentation:** product_photos_qty, product_description_lenght, product_category_name_english

**Delivery & Logistics:** freight_value, delivery_time_days, delay_vs_estimate

**Customer Feedback:** review_score

**Order Timing:** order_month, order_year

**Payment Behavior:** payment_type, payment_installments                           |



**Target Variable**
**Target:** Repeating_customer



**Type:** 

Binary classification (1 = Repeat Customer, 0 = Non-Repeat Customer)



**Goal:**
**Predict the likelihood of a customer belonging to the repeat segment.**




**Models Evaluated**

Four models were trained and compared using the same feature set and balanced data (using oversampling):
| Model         | Accuracy | ROC AUC | Precision (1) | Recall (1) | F1-Score (1) |
| ------------- | -------- | ------- | ------------- | ---------- | ------------ |
| CatBoost      | 0.9709   | 0.9896  | 1.00          | 0.94       | 0.97         |
| XGBoost       | 0.9834   | 0.9909  | 1.00          | 0.97       | 0.98         |
| Random Forest | 0.9852   | 0.9963  | 1.00          | 0.97       | 0.99         |
| LightGBM      | 0.9848   | 0.9905  | 1.00          | 0.97       | 0.98         |




**Best Model:**

Random Forest — highest accuracy and ROC-AUC, excellent balance of precision and recall.



**Feature Importance (Top 5)**


**review_score**— Strongest predictor; satisfied customers tend to return.

**order_year** — Reflects evolving loyalty trends.

**payment_type**— Credit card users more likely to repurchase.

**payment_installments** — Flexible payments increase repeat probability.

**order_month** — Seasonal variations affect repeat behavior.



**Predicted Repeat Purchase Probabilities for New Customers**


| Product Category          | Repeat Probability |
| ------------------------- | -----------------: |
| **furniture_decor**       |          **0.403** |
| **health_beauty**         |          **0.386** |
| **arts_and_craftmanship** |          **0.125** |



**New Customer Predictions**


| Product Category      | Repeat Probability |
| --------------------- | -----------------: |
| furniture_decor       |              0.403 |
| health_beauty         |              0.386 |
| arts_and_craftmanship |              0.125 |


**Insight:** Furniture & decor and health & beauty have the highest repeat purchase likelihood.


**Business Applications**

- Focus retention campaigns on high-repeat categories.

- Personalize marketing based on payment type and engagement.

- Improve delivery performance to reduce delays.

- Enhance product images and descriptions to increase trust and loyalty.

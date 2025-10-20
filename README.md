Dataset - https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce/data

<img width="2486" height="1496" alt="DBSchema" src="https://github.com/user-attachments/assets/6f6b87b4-4351-497c-a7d4-5c33bc4d1cba" />


**Repeat Customer Prediction Model Summary**

**Objective**

The main objective of this project is to build a predictive model to estimate the probability of a customer making a repeat purchase (Repeating_customer) based on order, product, payment, and customer-related features.
This model enables data-driven decision-making in customer retention, marketing optimization, and sales forecasting.


**Feature Set**

The model was trained using the following 15 features that capture product characteristics, customer behavior, delivery experience, and payment preferences:
| Category                       | Feature                                                                             | Description / Role                                                                                      |
| ------------------------------ | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
|  **Product Characteristics**   | `product_weight_g`, `product_length_cm`, `product_height_cm`, `product_width_cm`    | Physical dimensions of the product, influencing handling, cost, and repeat interest.                    |
|  **Product Presentation**      | `product_photos_qty`, `product_description_lenght`, `product_category_name_english` | Product visibility and information quality; more photos and detailed descriptions build customer trust. |
|  **Delivery & Logistics**      | `freight_value`, `delivery_time_days`, `delay_vs_estimate`                          | Indicators of shipping cost, speed, and reliability; delays often reduce repeat likelihood.             |
|  **Customer Feedback**        | `review_score`                                                                      | Reflects customer satisfaction; higher ratings correlate strongly with repeat purchases.                |
|  **Order Timing**           | `order_month`, `order_year`                                                         | Captures seasonality and purchasing patterns over time.                                                 |
|  **Payment Behavior**        | `payment_type`, `payment_installments`                                              | Payment flexibility and method preferences that indicate loyalty behavior.                              |



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



**Feature Importance (Top 10 Features)**
| Rank | Feature                           | Importance | Interpretation                                                       |
| ---- | --------------------------------- | ---------: | -------------------------------------------------------------------- |
| 1    | **review_score**                  |     0.1506 | Higher satisfaction ratings strongly increase repeat likelihood.     |
| 2    | **order_year**                    |     0.1393 | Indicates evolving customer loyalty trends across years.             |
| 3    | **payment_type**                  |     0.1118 | Credit card and installment payments correlate with repeat behavior. |
| 4    | **payment_installments**          |     0.0940 | Customers paying in installments are more engaged.                   |
| 5    | **order_month**                   |     0.0890 | Seasonal variations affect repeat patterns.                          |
| 6    | **product_photos_qty**            |     0.0520 | More product photos improve trust and return rates.                  |
| 7    | **product_description_lenght**    |     0.0492 | Longer product descriptions improve customer confidence.             |
| 8    | **delay_vs_estimate**             |     0.0444 | Fewer delivery delays lead to higher retention.                      |
| 9    | **product_category_name_english** |     0.0443 | Certain product categories naturally drive loyalty.                  |
| 10   | **product_weight_g**              |     0.0421 | Product size and weight may influence repeat potential.              |




**Predicted Repeat Purchase Probabilities for New Customers**
| Product Category          | Repeat Probability |
| ------------------------- | -----------------: |
| **furniture_decor**       |          **0.403** |
| **health_beauty**         |          **0.386** |
| **arts_and_craftmanship** |          **0.125** |



**Interpretation**

Furniture & Decor and Health & Beauty show the highest repeat probabilities, suggesting strong customer satisfaction and trust.


Arts & Craftsmanship has lower retention potential, indicating niche or infrequent purchases.




**Key Insights**

- Customer satisfaction (review_score) and payment flexibility are the strongest predictors of repeat buying.


- Operational excellence (on-time delivery, accurate estimates) significantly impacts retention.


- Product presentation (photos, descriptions) enhances perceived reliability and encourages repeat purchases.


- Seasonality and recency also influence repurchase behavior.




**Business Implications**

**Customer Retention:** Target high-repeat categories and satisfied customers with loyalty programs.


**Marketing Strategy:** Personalize offers for customers using credit cards or installment payments.


**Operations:** Reduce delivery delays to improve retention.


**Product Strategy:** Invest in better product content (images, detailed descriptions) for long-term customer engagement.


***
SLA Prediction using Random Forest
***

## **Project Overview**

This project predicts the Service Level Agreement (SLA) for order deliveries using machine learning techniques. The goal is to predict the number of days between when an order is shipped and when it is delivered, based on features like order date, pickup and drop pin codes, order quantity, and delivery SLA.

The model uses a Random Forest Regressor to train on historical data and make predictions. The project includes data preprocessing, feature engineering, model training, and evaluation using metrics such as Mean Squared Error (MSE) and Root Mean Squared Error (RMSE).


## **Files**

train.csv: The training dataset containing order details, including dates and locations.
test.csv: The test dataset used to make predictions based on the trained model.
pincodes.csv: A dataset containing pincode details for pickup and drop locations.
submission.csv: The output file with predicted SLA values for the test data.

## **Steps to Run the Project**

1. Install Dependencies
Make sure the required libraries are installed:

bash
Copy code
pip install pandas numpy scikit-learn

2. Data Preparation
The dataset contains the following key columns:

order_placed_date, order_shipped_date, order_delivered_date
pickup_pin_code, drop_pin_code
quantity, order_delivery_sla
The data is preprocessed by converting date columns to datetime, creating new features like the month, day, and weekday, and merging the pincode dataset for additional location features.

3. Feature Engineering
Created the predicted_exact_sla as the target variable, representing the number of days between when an order is shipped and delivered.
Derived features such as:
Month, day, and weekday from order_shipped_date
Same state indicator (same_state) to check if pickup and drop locations are in the same state.

5. Model Training
Split the data into an 80-20 training-testing ratio using train_test_split.
Trained the model using Random Forest Regressor from scikit-learn.

7. Evaluation
Evaluated the model using Mean Squared Error (MSE) and Root Mean Squared Error (RMSE) to assess the accuracy of the predictions.

9. Prediction and Submission
After training, the model makes predictions on the test dataset (test.csv).
The predictions are saved to submission.csv, which contains the predicted SLA values for each test order.
Model Performance
Mean Squared Error (MSE): [Insert value from the output]
Root Mean Squared Error (RMSE): [Insert value from the output]
Conclusion
The model performs [good/average/poor] based on the MSE and RMSE values, and it provides reasonable predictions for SLA. Further improvements can be made by tuning the model or adding more features.

Future Enhancements
Explore hyperparameter tuning for Random Forest or try other models like Linear Regression.
Improve feature engineering by considering other time-based or location-based features.
Use cross-validation to better evaluate model performance.

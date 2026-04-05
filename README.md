Overview
•	Hotel Chain A was losing significant revenue due to booking cancellations and no-shows. This project builds a machine learning model to predict booking outcomes and help the hotel take early action.

Problem
Predict one of 3 booking outcomes from historical data:
•	Check-Out — guest completes their stay
•	Canceled — booking canceled before arrival
•	No-Show — guest never arrives without notice

Data
Provided directly by Hotel Chain A:
•	Training: 26,993 bookings after cleaning
•	Validation: 2,733 bookings
•	Test: 4,291 bookings
•	24 features including lead time, deposit type, room rate, guest history

Approach
1. Feature engineering — calculated Lead Time, Length of Stay, revenue risk
2. Cleaned inconsistent labels and removed invalid rows
3. Label Encoding before SMOTE to avoid breaking synthetic samples
4. SMOTETomek to handle class imbalance — training data only
5. Compared 5 models using Macro F1 as primary metric
6. Selected best model and predicted on test set

Results
•	Best model: Decision Tree (Macro F1 = 0.339)

Macro F1 used instead of accuracy — dataset is imbalanced across 3 classes.

•	Logistic Regression: F1 = 0.305, Accuracy = 0.519
•	Decision Tree: F1 = 0.339, Accuracy = 0.456 (best)
•	Random Forest: F1 = 0.310, Accuracy = 0.537
•	XGBoost: F1 = 0.304, Accuracy = 0.539
•	ANN: F1 = 0.337, Accuracy = 0.503

Key Findings
•	1,556 out of 4,291 test bookings flagged as high risk (36.04%)
•	£1,985,459 revenue lost annually from cancellations and no-shows
•	Top features: Lead Time, Deposit Type, Ethnicity

Stack
•	Python, scikit-learn, XGBoost, imbalanced-learn, pandas, numpy, matplotlib, seaborn, Google Colab

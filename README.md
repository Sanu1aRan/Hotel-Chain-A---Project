 Hotel Chain A — Booking Cancellation Prediction

Project Background
Hotel Chain A has been experiencing significant revenue losses due to booking cancellations and no-shows. This project uses machine learning to predict booking outcomes and help the hotel take proactive action.

Problem
Predict one of 3 booking outcomes:
Check-Out — guest completes their stay
Canceled— booking canceled in advance
No-Show — guest never arrives without notice

Dataset
Provided by Hotel Chain A:
Training set: 26,993 bookings (after cleaning)
Validation set: 2,733 bookings
Test set: 4,291 bookings
Features: 24 variables including lead time, deposit type, room rate, guest history

What We Did
1. Cleaned and preprocessed the data
2. Engineered new features (Lead Time, Length of Stay, Revenue Risk)
3. Handled class imbalance using SMOTETomek
4. Trained and compared 5 models
5. Selected best model based on Macro F1 score
6. Predicted outcomes on test set
7. Calculated revenue impact and business recommendations

Models Compared

| Model | Macro F1 | Accuracy |
| Logistic Regression | 0.305 | 0.519 |
| Decision Tree | 0.339 | 0.456 |
| Random Forest | 0.310 | 0.537 |
| XGBoost | 0.304 | 0.539 |
| ANN | 0.337 | 0.503 |

Best model: Decision Tree (Macro F1 = 0.339)
Macro F1 was used instead of accuracy because the dataset is imbalanced across 3 classes.

 Key Results

1,556 out of 4,291 test bookings flagged as high risk (36.04%)
£1,985,459 revenue lost annually from cancellations and no-shows
Top predictors: Lead Time, Deposit Type, Ethnicity

Libraries Used

pandas, numpy
scikit-learn
xgboost
imbalanced-learn
matplotlib, seaborn
Google Colab





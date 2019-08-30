# analytics_vidya_ml_india_hiring_hackathon
Analytics Vidya ML India Hiring Hackathon 2019

Statement - Predict delinquency for month-m13

About Data:- No null values in any of the columns

EDA:-
1. Numerical Features<br />
  a. unpaid_principal_bal - Right skewness is 0.895, so normalisation is required.<br />
  b. loan_term - Left skewness is -0.69, medium normalisation is required. Most of the data having 360 loan_term.<br />
  c. loan_to_value - medium left skewed.<br />
  d. number_of_borrowers - very less left skewed. having only two values 1 or 2.<br />
  e. debt_to_income_ratio - Already normalised. no skewness. <br />
  f. interest_rate - not skewed. Hence already normalised.<br />
  g. borrower_credit_score - highly left skewed. Need normalisation.<br />
  h. insurance_percent - highly right skeded. Need normalisation. most of the loan_id's having 0 as insurance percent.<br />
  i. co-borrower_credit_score - small left skewness and most of the co-borrowers credit score having 0 values or around 750.<br />
  j. insurance_type - highly right skewed and having only 0 values.<br />
 
 2. Numerical Features vs m13(0 - Non-delinquency, 1 - delinquency)<br />
  a. interest_rate - Interest rate of delinquent loan is more than non-delinquent loan. There are more_outliares for non-delinquent loans.<br />
  b. unpaid_principal_bal - Unpaid principal balance of delinquent loan is less than non-delinquent loan. There are more_outliares for non-delinquent loans.<br />
  c. loan_term - loan_term for 0 is between 180 to 360 and for 1, it's only 360. As well as having some outliers for 1.<br />
  d. loan_to_value - loan to value is more for 1 and less for 0. Both classes having some outliers.<br />
  e. number_of_borrowers - graph doesn't infer any specific information. Both classes having value either 1 or 2.<br />
  f. debt_to_income_ratio - debit to income ratio is more for class 1. <br />
  g. borrower_credit_score - credit score is high for class 0 which is correct, it should be.<br />
  h. insurance_percent - Average insurance percent is 0 for both the classes and having outliers in both the classes.<br />
  i. co-borrower_credit_score - Average is higher for class 0 which seems correct.<br />
  j. insurance_type - Averge is 0 for both the classes and both classes having some outliers.<br />
  
 For m1 to m12 - 0 is the most frequent values for m1 to m12. It seems like m7 to m12 is deciding factor for delinquency in m13.
 
 After looking at correlation matrix, it seems like co-borrower credit score and number of borrowers is highly correlated. So we can drop any one of the columns.
 
 3. Cateogrical features<br />
  a. source - most of the loans belongs to sorce 'X'.<br />
  b. financial_instution - most of the loans belongs to 'Other' and 'Browning-Hart'. So we can combine all other values into one so that we will have only three cateogries.<br />
  c. origination_date - Only three distinct values is there.<br />
  d. first_payment_date - There are very few values for 02/12, so we can replace it by 03/12.<br />
  e. loan_purpose - having 3 distinct values.<br />
  
 I have generated cross-tables for each cateogrical features with respect to m13. Can infer more info. from that.
 
 By looking at m13 data, we can say that it is a class imbalance problem. I have used SMOTE for class balancing.
 
 Langauage Used - Python3
 Python Libraries - Pandas, Numpy, Seaborn, Matplotlib, sklearn, imblearn(for imbalance class)
 Algorithm - Used GridCV with Logistic Regression with 5-fold validation.
 Accuracy of algorithm is 85%. Got balanced precision and recall values for both the classes and f1-score also seems good for both classes.
 
 Remaining work - More feature engineering.
 
 

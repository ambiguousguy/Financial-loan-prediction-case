# Financial-loan-prediction-case
**(sorry for that, since the jupyternote book havent save the checkpoint,  result didnt show in it, if wanna to know more, the ppt file 'project show' is available )**

## Project introduction
1.this project basing on the competition of Ali Tianchi, with total 32 variables, 800000 observation in train set, 200000 observation in test set<br>
2. it requires to building the model to predict whether a loaner will default the loan.

## Evaluation Metric
The competition uses AUC as the evaluation metric. AUC (Area Under Curve) is defined as the area enclosed by the coordinate axis under the ROC curve.
The closer the AUC is to 1.0, the higher the authenticity of the detection method.


## data introduction
![image](https://github.com/ambiguousguy/Financial-loan-prediction-case/blob/main/pic/0.png)<br>
![image](https://github.com/ambiguousguy/Financial-loan-prediction-case/blob/main/pic/1.png)<br>
![image](https://github.com/ambiguousguy/Financial-loan-prediction-case/blob/main/pic/2.png)<br>


## data cleaning part
### Null Value
There are a total of 22 columns of data with null values
After all empty rows are deleted, there will be 686,195 data left. 
### Duplicate Value
Id item has no duplicate value.
### Data type
Features are generally composed of categorical features and numerical features, and numerical features are further divided into continuous and discrete types.

### data processing
1.Any variables displayed as a single column in the distribution chart , in my opinion, that is no researching value and can be deleted directly.(pic following)

<br>
2.  for outlier handling, i handle it with the method of truncation : if there is a point higher or lower than upper quartile / lower quartile，
then we set this point as the Q3+(scale*IQR) or Q1+(scale*IQR)

## feature engineering

1.**Data binning**<br>

2.**new feature construction**<br>
Interest rate/Total Loan amount<br>
Annual income/Total Loan amount<br>
Installment amount/Total Loan amount<br>
Annual Income / Installment Amount<br>
Annual Income/ Years of employment (years)<br>
Annual income * years of employment<br>
openAcc/totalAcc<br>
openAcc/earliesCreditLine<br>
<br>
3.**label encoding**

## Model performance

### 1. logistic regression
AUC = 0.7011

### 2. random forest 
AUC= 0.7082<br>
![image](https://github.com/ambiguousguy/Financial-loan-prediction-case/blob/main/pic/RF.png)<br>

### 3. XGB model
AUC = 0.7469<br>
![image](https://github.com/ambiguousguy/Financial-loan-prediction-case/blob/main/pic/xgb.png)<br>


### 4.LGBT model(the best performance model)
AUC = 0.7482<br>
![image](https://github.com/ambiguousguy/Financial-loan-prediction-case/blob/main/pic/lgbt.png)<br>


## importance feature

### in random forest
![image](https://github.com/ambiguousguy/Financial-loan-prediction-case/blob/main/pic/RF_I.png)<br>

### in xgb
![image](https://github.com/ambiguousguy/Financial-loan-prediction-case/blob/main/pic/xgb_i.png)<br>

### in lgbt
![image](https://github.com/ambiguousguy/Financial-loan-prediction-case/blob/main/pic/LGBT_I.png)<br>


### common feature
for feature construction variable:<br>
	‘annualIncome / installment’, ‘openAcc / totalAcc’, ‘installment/loanAmnt’ , ‘annualIncome/ loanAmnt’ , ‘openacc / earliesCreditline’<br>


for behavior count variable: <br>
	‘n6’ , ‘ n8 ’, ‘ n7 ’,’ n9 ’<br>


for employment variable:<br>
	‘employmentLength’<br>


# conclusion
1.the LGBT model perform the best in this project, with AUC 0.7482 and XGBoosting model is close to it with AUC 0.7469 <br>


2.The feature construction variables in feature engineering , like ‘annualIncome / installment’, show great important in the model performance, which is a great success.<br>

3.We found some of the features are really helpful to make a default prediction, say, ‘n6’ , ‘n7’ , ‘n8’ , ‘n9’ , ‘employmentlenth’ and some of the feature we create.<br>


4.Due to the insufficient computational power, we can not process the model stacking part which combine the model we mention and may highly improve the performance<br>




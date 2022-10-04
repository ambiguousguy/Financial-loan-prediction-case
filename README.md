# Financial-loan-prediction-case
**(sorry for that, since the jupyternote book havent save the checkpoint,  result didnt show in it, if wanna to know , the ppt file 'project show' is available )**

## Project introduction
1.this project basing on the competition of Ali Tianchi, with total 32 variables, 800000 observation in train set, 200000 observation in test set<br>
2. it requires to building the model to predict whether a loaner will default the loan.

## Evaluation Metric
The competition uses AUC as the evaluation metric. AUC (Area Under Curve) is defined as the area enclosed by the coordinate axis under the ROC curve.
The closer the AUC is to 1.0, the higher the authenticity of the detection method.


## data introduction
0-3(图片补充)


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
（图片补充）
<br>
2.  for outlier handling, i handle it with the method of truncation : if there is a point higher or lower than upper quartile / lower quartile，
then we set this point as the Q3+(scale*IQR) or Q1+(scale*IQR)

## feature engineering

1.**Data binning**<br>

2.**new feature construction**<br>
Interest rate/Total Loan amount
Annual income/Total Loan amount
Installment amount/Total Loan amount
Annual Income / Installment Amount
Annual Income/ Years of employment (years)
Annual income * years of employment
openAcc/totalAcc
openAcc/earliesCreditLine
<br>
3.**label encoding**

## Model performance

### 1. logistic regression
AUC = 0.7011

### 2. random forest 
AUC= 0.7082 (补图片)

### 3. XGB model
AUC = 0.7269(补图片)

### 4.LGBT model(the best performance model)
AUC = 0.7282(补图片)


## importance feature
(补图片)

for feature construction variable:<br>
	‘annualIncome / installment’, ‘openAcc / totalAcc’, ‘installment/loanAmnt’ , ‘annualIncome/ loanAmnt’ , 	‘openacc / earliesCreditline’<br>


for behavior count variable: <br>
	‘n6’ , ‘ n8 ’, ‘ n7 ’,’ n9 ’<br>


for employment variable:<br>
	‘employmentLength’<br>






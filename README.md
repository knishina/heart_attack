# heart_attack

### Summary.
This project takes data consisting of attributes that are hypothesized to contribute to heart disease.  The purpose of this project is to take the data and generate a predictive model for heart disease.  The data was obtained through [Kaggle](https://www.kaggle.com/ronitf/heart-disease-uci).  The following modules were used analyze/visualize and build a predictive model: `pandas` for data munging, `matplotlib, seaborn` for data visualization, and `sklearn, eli5` for model building and its associated analyses.

The data have fourteen attributes.  They include:
 - `age` &nbsp; &nbsp; &nbsp; &nbsp; in years
 - `sex` &nbsp; &nbsp; &nbsp; &nbsp; (1 = male; 0 = female)
 - `cp` &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; chest pain type
 - `trestbps` resting blood pressure (in mm Hg on admission to the hospital)
 - `chol` &nbsp; &nbsp; &nbsp; &nbsp;serum cholestoral in mg/dl
 - `fbs` &nbsp; &nbsp; &nbsp; &nbsp; (fasting blood sugar > 120 mg/dl) (1 = true; 0 = false)
 - `restecg` &nbsp; resting electrocardiographic results
 - `thalach` &nbsp; maximum heart rate achieved
 - `exang` &nbsp; &nbsp; &nbsp; exercise induced angina (1 = yes; 0 = no)
 - `oldpeak` &nbsp; ST depression induced by exercise relative to rest
 - `slope` &nbsp; &nbsp; &nbsp; the slope of the peak exercise ST segment
 - `ca` &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;number of major vessels (0-3) colored by flourosopy
 - `thal` &nbsp; &nbsp; &nbsp; &nbsp; 3 = normal; 6 = fixed defect; 7 = reversable defect
 - `target` &nbsp; &nbsp; 1 or 0 (I think this means 1= heart attack; 0=no heart attack)
 
 <br />
 
 ### Data Analysis and Visualization.
 
 ![heatmap](https://github.com/knishina/heart_attack/blob/master/Images/01.png)
 <b>Data Heatmap</b>
All categories were set against each other.  A resulting heatmap was produced that indicates positive/negative correlations.  Considering the various columns in reference to `target`, there a few notable positive and negative relationships.
- positive relationships include: cp, thalach, and slope. 
- negative relationships include: age, sex, exang, oldpeak, ca, and thal.

<br />

<img src="https://github.com/knishina/heart_attack/blob/master/Images/02.png" width=50% alt="age">
<b>Age as an indicator for heart disease</b>
This plot considers age and its role as an indicator for heart attack. The legend indicates heart attack (1) v. no heart attack (0). In this case, the above bar graph indicates that there is little to correlation of age as an indicator for heart attack. This is further evidenced by the heat map having a negative correlation value of -0.23.

<br />

<img src="https://github.com/knishina/heart_attack/blob/master/Images/03.png" width=50% alt="gender">
<b> Gender as an indicator for heart disease</b>
This plot considers sex and its role as an indicator for heart attack. First, it appears that the data is skewed to males, meaning, that there are more males in this study compared to females. In fact, the ratio of males to females is 2:1. Second, the female population has a higher rate of heart attacks; the male population has a lower rate of heart attacks. Due to this discrepancy, the heatmap reads this as not having a positive correlation. In other words, heatmap is indicating that sex is not likely an indicator of having a heart attack (-0.28).

<br />

<img src="https://github.com/knishina/heart_attack/blob/master/Images/04.png" width=50% alt="chest_pain">
<b>Chest pain as an indicator for heart disease</b>
This plot considers chest pain type (cp) as an indicator for heart attack. For data where cp is 1 or higher, the incidence of heart attack is high. For data were cp is 0, the value of 0 indicates that there is no chest pain and correlates strongly with the absence of heart attack. According to the heatmap, the value for cp is 0.43, a positive correlation. That means that cp is likely an indicator of having a heart attack.

<br />

### Model Building.
Three models were trained and tested.  The three include: linear regression, logistic regression, and support vector machine (SVM).  Of the three, the linear regression model had a poor predictive outcome.

<b>Logistic Regression</b>
- Accuracy score: Train = 0.864; Test = 0.885.  
- Classification report: <br/>
<img src="https://github.com/knishina/heart_attack/blob/master/Images/05.png" width=50% alt="classification_report1">

<b>SVM</b>
- Accuracy score: Train = 0.855; Test = 0.869.
- Classification report: <br/>
<img src="https://github.com/knishina/heart_attack/blob/master/Images/06.png" width=50% alt="classification_report2">

The better model of the two is the Logistic Regression.  Below is the weight per feature and the ROC for the logistic model.

<img src="https://github.com/knishina/heart_attack/blob/master/Images/07.png" width=20% alt="weights">
<img src="https://github.com/knishina/heart_attack/blob/master/Images/08.png" width=50% alt="ROC">
<br />

### License.
This project is licensed under the MIT License - see the [LICENSE](https://github.com/knishina/heart_attack/blob/master/LICENSE) file for details.

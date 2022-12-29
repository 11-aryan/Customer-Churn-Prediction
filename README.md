# Customer-Churn-Prediction
A web-application made with flask that predicts whether a customer will churn or not
<br> </br>
Link to the Web Application: https://churn-prediction.onrender.com

### Built with
<a href="https://www.python.org/">
    <img src="https://skillicons.dev/icons?i=python" />
</a>
<a href="https://www.tensorflow.org/">
    <img src="https://skillicons.dev/icons?i=tensorflow" />
</a>
<a href="https://pandas.pydata.org/">
    <img src="https://user-images.githubusercontent.com/55359898/209969238-b1349651-9324-474b-9d96-17ada096c75e.png" height=50/>
</a>
<a href="https://numpy.org/">
    <img src="https://user-images.githubusercontent.com/55359898/209969436-17256362-93a3-46da-9e1e-f503460e1670.png" height=50/>
</a>
<a href="https://git-scm.com/">
    <img src="https://skillicons.dev/icons?i=git" />
</a>
<a href="https://www.w3schools.com/html/">
    <img src="https://skillicons.dev/icons?i=html" />
</a>
<a href="https://www.w3schools.com/css/">
    <img src="https://skillicons.dev/icons?i=css" />
</a>
<a href="https://getbootstrap.com/">
    <img src="https://skillicons.dev/icons?i=bootstrap" />
</a>

<br>
<br>
<img src="https://user-images.githubusercontent.com/55359898/209970037-a7027cb2-c979-4abb-bbc5-fa70a19a0bb1.png" width="800">


### Exploratory Data Analysis
The data preprocessing and EDA can be found in the ***EDA.ipynb*** jupyter notebook.
The data was preprocessed to remove duplicates, the dropping the Null values as the percentage of Null values was small.
EDA techniques used include *univariate and bivariate analysis* to draw inferences about how the churn is *correlated* to different data features.
##### Inferences drawn from EDA:
- Customers who use *Electronic Check* are the higest churners
- Customers with *long term* contracts are *more likely* to churn than the customers with short term contracts
- Customers with *no tech support* churn more
- *Senior citizens* are *less likely* to churn compared to non senior citizens
<br> </br>

### Model Building
This can be found in the ***Churn_Model.ipynb*** jupyter notebook
The numeric values such as *TotalCharges* and *MonthlyCharges* were used without any changes and the categorical values such as *gender*, *paymentMethod*, etc. were one hot encoded 
<br> </br>
Initially the model was trained one the original preprocessed data with **Decision Tree** and the following results werwe obtained:
* Accuracy: ***0.79***
* Precision: ***0.74***
* Recall: ***0.71***
* F1 Score: ***0.72***

The performance of the model was not good, and was as expected because the dataset is **skewed**, with *less samples* for No Churn. *Upsampling* with **SMOTE-ENN** and retraining the model, significantly improved the performance of the model, with the following results:
* Accuracy: ***0.94*** 
* Precision: ***0.94***
* Recall: ***0.94***
* F1 Score: ***0.94***

Apart from decision tree, different models were trained such as **Random Forest Classifier** and **XGBoost**. On comparing the results no significant difference was found in the performance of these models.


### Web Application
The web applicatoin takes the input from the user for differnt features such as MonthlyCharges, Payment Method, Contract type, etc. and displays a message whether the customer with the given input features is likely to churn or not, along with the confidence of the prediction.
<br> </br>
The front-end of the web application is made with **HTML**, **CSS, bootstrap** and in the back-end **Flask** is used. This web application is deployed on Render, and the link to it can be found at the top.

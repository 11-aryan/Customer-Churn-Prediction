# Customer-Churn-Prediction
A web-application made with flask that predicts whether a customer will churn or not
<br> </br>
Link to the Web Application: https://churn-prediction-webapp.herokuapp.com/

### Built with
<code><img height="30" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/python/python.png"></code>
<code><img height="30" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/html/html.png"></code>
<code><img height="30" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/css/css.png"></code>
<code><img height="30" src="https://github.com/tomchen/stack-icons/raw/master/logos/bootstrap.svg"></code>
<code><img height="30" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/git/git.png"></code>
<code><img height="30" src="https://symbols.getvecta.com/stencil_80/56_flask.3a79b5a056.jpg"></code>
<code><img height="30" src="https://cdn.iconscout.com/icon/free/png-256/heroku-225989.png"></code>
<code><img height="30" src="https://raw.githubusercontent.com/numpy/numpy/7e7f4adab814b223f7f917369a72757cd28b10cb/branding/icons/numpylogo.svg"></code>
<code><img height="30" src="https://raw.githubusercontent.com/pandas-dev/pandas/761bceb77d44aa63b71dda43ca46e8fd4b9d7422/web/pandas/static/img/pandas.svg"></code>
<code><img height="30" src="https://matplotlib.org/_static/logo2.svg"></code>
<code><img height="30" src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Scikit_learn_logo_small.svg/1280px-Scikit_learn_logo_small.svg.png"></code>
<br>
<br>
<img src="Images/ChurnPrediction.png" width="700">
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
The front-end of the web application is made with **HTML**, **CSS, bootstrap** and in the back-end **Flask** is used. This web application is deployed on Heroku, and the link to it can be found at the top.

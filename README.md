# Salary-estimation
#### This project estimate data analyst salaries to help them negotiate their income when they get a job(MAE=0.015K , MIN_SALARY:29K , MAX_SALARY: 101K)
* Scraped over 400 job descriptions from glassdoor using python and selenium
* Engineered features from the text of each job description to quantify the value companies put on python, excel, R, SQL,tableau,PowerBI, haddop & spark.
* Optimized Linear, and Random Forest Regressors using GridsearchCV to reach the best model.

# Web Scraping
I scrapped over 400 jobs from glassdoor.com to extract job title,salary estimate,job description,company name,location,company size,type of ownership etc
### WHY SELEMIUMM: Glassdoor renders its content with Javascript. Which means that a simple get request to the webpage below would return only the visible content. We are interested in more than that.
* Scraper Article: https://towardsdatascience.com/selenium-tutorial-scraping-glassdoor-com-in-10-minutes-3d0915c6d905

# Data Cleaning
After scraping the data, I needed to clean it up so that it was usable for our model. I made the following changes:
* extract the minimum,maximum,average salary from the colum salary estimate
* extract the state from location column
* Transformed founded date into age of company
* Made columns for if different skills were listed in the job description:Python,R,Excel,tableau....
* add a column for simplified job title and Seniority

# Exploratory data analysis:
This step is so important to extract the trends and insights from the data
* most companies are 1000+ employees & 1001-5000 employees
* private companies are the most commun 
* data analyst mostly are demanded in the health care,It services,consulting,computer hardware &software companies
* data analyst mostly work in the IT sector and business services
* data analyst is most demanded in CA and NY
![](https://github.com/kaouta/Salary-estimation/blob/master/type%20of%20ownership.png)

![](https://github.com/kaouta/Salary-estimation/blob/master/excel.png)

# Model Building and performance
First, I transformed the categorical variables into dummy variables. I also split the data into train and tests sets(train set 80%,test set 20%)
I tried 2 different models and evaluated them using Mean Absolute Error. I chose MAE because it is relatively easy to interpret and outliers aren’t particularly bad in for this type of model.

* Multiple linear regression MAE : 5.6690763194922056e-15
* Random forest MAE: 0.015459375000001213



# 0. Introduction and problem definition
As of now, there exist more than 3.1M mobile apps solely on Google Play Market (Statista, 2020). Together with the ones available in iOS App Store, these applications generate almost $32B of revenue, making it a desirable market for many founders (D. Curry, 2021). Having read about these positive trends, I got myself wondering - how many of these 3.1m mobile apps become successful? Gartner study reveals that only 0.01% of the apps reach commercial success.
With the above in mind, I decided to take a data-driven approach to explore the following questions:

What features define a successful mobile application? Can I use ML to predict the app's ratings?
Can I use ML to predicting the app's success before launch?
I approach these questions with a user-centered mind - that is, the application's success is defined by the average rating that the application has or/and the number of installs.

# 1. Executive summary of the proposed solution 
To answer these questions, I will use the dataset that was published on Kaggle by L. Gupta (2018).. This dataset was scraped from Google Play Market and resulted in two datasets: (1) features of the apps, such as ratings, installs, category; (2) actual user reviews in text. For this project, I will only use the first dataset, however, the second one could serve as a great complement to quantitive analysis and might be performed sometime in the future.

I divide this overarching problem into two separate modeling processes. One being regression modeling ("What is the rating of the app, given these features?"), and the other being classification ("Would this application be successful given these pre-launch features?").

For both of the processes, I use the same ML methods because: (a) using the same models will allow me to compare the methods in two different kinds of the problem (regression VS classification), which yields the highest learning opportunity for me; (b) these methods make sense in the given context (explained below).

1. Random Forest Model (RFM) - will provide a great insight into what are the specific features defining the success of the application and their degree of influence. RFM does not make any assumptions about underlying data, which is helpful in my context of highly variable and rich data ;
2. Support Vector Machines (SVM) - specifically SV Regression and SV Classification correspondingly. Because sparsity of the data is high (the genres categories are often 0s), SVMs would make the most out of it. Further, SVMs are usually preffered over neural nets in case of the smaller dataset, which is also our case.

Furthermore, I will compare the stand-alone models with those fitted on PCA reduced datasets. PCA will help me see if any components alone can do a job for all other components. Also, for each model, I perform a 4-fold CV grid search to determine the best hyperparameters. All the data is also scaled before fitting giving huge variaility.

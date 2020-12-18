# Taking on the House: NFL Over/Under Predictor

Since the decision to legalize sports gambling in a number of states in the U.S. the sports gambling industry has continued to grow exponentially. With a lot of states still making plans to legalize, this is the perfect time to make a mark on the growing industry. This project is tasked with the goal to successfully predict the over or under total in an NFL game. Betting the over/under total is one of the most popular sports bets to make and my predictor can help both the handicapper and the bettor make more informed decisions. 

  
- **Data:** 

My first task was to source the data. For the original dataset I used Kaggel.com to pull two separate datasets. The first was a dataset that had all the betting data for every NFL game played dating back to the 1960s. Then I also managed to retrieve an NFL Stadium dataframe, which had all the relevant NFL Stadiums dating back to the 1960s. 
Next, I decided it was important to use data containing some of the team states for each home and away team, www.pro-football-reference.com turned out to be an amazing source for all the NFL statistics I needed.

- **EDA:** 

Once I had collected all the relevant data, I started with EDA. To start I broke all my features into 4 groups; Setting, Weather, Team Statistics, and Betting Data.
The Setting group contained all features that portray the time or place an NFL game was taking place. Day of the Week a game was played on was one of the first features I looked in to. Below is a visualization describing the Over/Under comparison for each day of the week. 
![alt text](visualizations/weekday_bar.png)
It is important to note that the class imbalance would lead to the favor the Under,





- **Feature Engineering:**  

I then began with Feature Engineering. First, I feature engineered a Bath per Bedroom value. I plotted Bath_per_Bed vs Price and did not come to any visual conclusion. After a new featured was engineered I would use the correlation matrix, a VIF calculator, and an OLS to see how the new variable effects the data.

![alt text](Data_Visualizations/bath_per_bed.png)

I also decided to make some of my variable’s binary. Liked mentions earlier, I changed the sqft_basement feature to show if the house has a basement or not. I did a similar conversion to the ‘floors’ feature. Our model was not responding well to that feature, so I decided to make it into a “One Story House” or “Multi Story House”.  Similarly, I made the condition feature “Bad Condition” and “Good Condition”. 

Another successful way to feature engineer was through binning. For the features “Grade”, “Zip Code Price Level”, and “Years Old” instead of having a lot of unique discrete variables for each feature. 

I also used the Date Sold column to engineer a column that shows the season the house was sold. Which did not come out very valuable. 


- **Statistical Tests:** 
The first statistical test I used was a Two Sample T-Test, to text the mean prices of the Year a house sold. We only had two unique values for year sold (2014, 2015) so a Two Sample T-Test was perfect. 

   Our Null Hypothesis is that the mean prices of houses sold in 2014 and 2014 are the same 

   Our Alternative Hypothesis was that they are different
  

   With a t-statistic of 0.307 and a p-value of .759 we can accept the Null hypothesis. Proving the year does not make a   significant different in the mean house prices. 
     ![alt text](Data_Visualizations/Screen%20Shot%202020-10-23%20at%209.51.12%20AM.png)
     
     
Next I went on to an Anova test. Here I tried to determine if the season the house was sold matter in the price. 

   My Null Hypothesis is that the season does not affect the price 

   My Alternative Hypothesis is that season does have an effect on price

   With a f-statistic of 6.882 and a P-value of 0.000125 we reject the null hypothesis proving that the season sold does make a difference. 
![alt text](Data_Visualizations/anova1.png)

Last I did another Anova test to see if the Binned Zip code based on housing prices has an effect on the Sqft of the House.

My Null Hypothesis is that the zip code has no effect on the size of the house.

My Alternative Hypothesis is that the zip code does have an effect on the size of the house.

With a f-statistic of 523.56 and a p-value of 0.0 we can reject the null hypothesis. Leading us to believe that there is a statistical different inhouse size by zip code 

![alt text](Data_Visualizations/anova2.png)     
     
 
 **Feature Selection:** 
 I used a lot of different methods for Feature Selection. To start I was able to code a VIF factor with help me decide with variable were having negative effect on the model. I also used the Person Correlation Matrix to help see if my features were multicollinear. Then I would use a simple OLS Multiple Linear model to help see which features are helping and hurting our predictions; based on p-values, r-squared value, t-value, etc. After I was fine with those tests, I would move into Sklearn linear modeling to further test my data. I used the Polynomial Features function to transform my dataset. I also used Recursive Feature Elimination to further examine my data. And KBest to get my most useful features 



- **Model Interpretation:** 
After going through each different process, I would check to see the R-Squared, Training Root Mean Square Error, Test Root Mean Squared Error. I would also check my Residual Plot help visually see where my model errors lie. 

![alt text](Data_Visualizations/residual.png) 

In the end I decided to use a Polynomial 2-degree dataset and ran a Select Kbest function to get a list of my 20 most useful features when predicting price. While the R-squared value was .74, determining that 74% of my model variance can be explained. And my Training RMSE was $173,615 and Test RMSE $185,258. I still was unable to perform confidently on the Holdout Data which is concerning. I will need to go back a troubleshoot to see where my error lie. 
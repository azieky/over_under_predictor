# Taking on the House: NFL Over/Under Predictor

Since the decision to legalize sports gambling in a number of states in the U.S. the sports gambling industry has continued to grow exponentially. With a lot of states still making plans to legalize, this is the perfect time to make a mark on the growing industry. This project is tasked with the goal to successfully predict the over or under total in an NFL game. Betting the over/under total is one of the most popular sports bets to make and my predictor can help both the handicapper and the bettor make more informed decisions. 

  
- ***Data:*** 

My first task was to source the data. For the original dataset I used Kaggel.com to pull two separate datasets. The first was a dataset that had all the betting data for every NFL game played dating back to the 1960s. Then I also managed to retrieve an NFL Stadium dataframe, which had all the relevant NFL Stadiums dating back to the 1960s. 
Next, I decided it was important to use data containing some of the team states for each home and away team, www.pro-football-reference.com turned out to be an amazing source for all the NFL statistics I needed.

- **EDA:** 

Once I had collected all the relevant data, I started with EDA. To start I broke all my features into 4 groups; Setting, Weather, Team Statistics, and Betting Data.
The Setting group contained all features that portray the time or place an NFL game was taking place. Day of the Week a game was played on was one of the first features I looked in to. Below is a visualization describing the Over/Under comparison for each day of the week. 
![alt text](visualizations/weekday_bar.png)
It is important to note that the class imbalance would lead to the favor the Under,






# Taking on the House: NFL Over/Under Predictor

Since the decision to legalize sports gambling in a number of states in the U.S. the sports gambling industry has continued to grow exponentially. With a lot of states still making plans to legalize, this is the perfect time to make a mark on the growing industry. This project is tasked with the goal to successfully predict the over or under total in an NFL game. Betting the over/under total is one of the most popular sports bets to make and my predictor can help both the handicapper and the bettor make more informed decisions. 

  
- **Data:** 

My first task was to source the data. For the original dataset I used Kaggel.com to pull two separate datasets. The first was a dataset that had all the betting data for every NFL game played dating back to the 1960s. Then I also managed to retrieve an NFL Stadium dataframe, which had all the relevant NFL Stadiums dating back to the 1960s. 
Next, I decided it was important to use data containing some of the team states for each home and away team, www.pro-football-reference.com turned out to be an amazing source for all the NFL statistics I needed.

- **EDA:** 

Once I had collected all the relevant data, I started with EDA. To start I broke all my features into 4 groups; Setting, Weather, Team Statistics, and Betting Data.

The Setting group contained all features that portray the time or place an NFL game was taking place. Day of the Week a game was played on was one of the first features I looked in to. Below is a visualization describing the Over/Under comparison for each day of the week. 

![alt text](visualizations/weekday_bar.png)

It is important to note that the class imbalance would lead to favor the Under, so it would be notable that Saturday games Overs seem to eclipse Under in percentage. It is also important to note Friday only has a sample size of 10, so while interesting, data is insufficient to gain insights. 

Another feature explored from the 'Setting" group was Stadium Capacity. Below is a voilin plot showing the distribution of Stadium Capacity throughout the dataset.

![alt text](visualizations/capacity_violin.png)

This shows that while most Stadiums lay in the size range of 60,000 to 80,000 maximum capacity, there are some outliers. I chose to explore that realization by binning the stadium capacity into three seperate groups; Low, Medium, and High

![alt text](visualizations/stadium_bar.png)

We can see here that the percentage of Overs exclipses Unders in Low Capacity Stadiums, and in High Capacity Stadiums the Under percentage take a sizeable percentage, giving insight into the possibility playing in High Capacity Stadiums could lead to more Unders.






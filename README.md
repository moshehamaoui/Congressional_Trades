# Congressional_Trades
Congressional Legislations Vs Stock Performance  
BrainStation Data Science Capstone Project

The goal of this project was to determine if there is a relationship between congressional legislations and trade success in the stock market. I aimed to look into how well each politician performed in the stock market and how they each voted in legislations within their respective congressional chambers. The idea is that congress has insider knowledge of the economy, so it is of value to determine who, if anyone, uses their knowledge and influence to trade exceptionally well in the stock market. 

If such a discovery of exceptional traders can be made, it could have 2 potential points of value. One is suspicion of insider trading. Although it is impressively difficult to prove, a congressman who continues to beat the market would be a person of interest for the SEC.

Alternatively, knowing which congressmen trade exceptionally well could prove lucrative to those who follow in their economic footsteps. Perhaps, it is a good idea to perform the same trades as those congressmen who continue to beat the market, thereby increasing one's own personal wealth.

That being said, here is how I went about searching for such information:

### Notebook 1 - Data Wrangling

In the first notebook, I acquired the necessary data, which came from 3 sources:

- Voting Data from govtrack.us

Here is where I found all of the congressional legislations for every single congressman.
The data dates back to the 1st congress, back in 1789. I did not go that far back. I was influenced by the availability of the trading data for how far back to go.

- Trading Data from Capitoltrades.com

This is where I found the transaction information for all the trades that each politician made. This data only goes back 3 years, to November of 2019. As a result, I only went as far back as the beginning of 2019, the start of the previous congress (the 116th) to the current one (the 117th).

- Stock Data from finance.yahoo.com

Lastly, here was the source of the stock information. Given the stock symbols that I discovered that were traded by the politicians, I looked up the stock price of each symbol, dating from a week before the symbol's earliest trade to now, the end of November, 2022.

I scraped these 3 sites for all the related information i coud find.  
Namely, politician biographical information such as age, party, chamber, committee membership...   
Each politician's voting records for all the legislations over the past 4 years.  
And all the transaction information related to every trade.

I ended up with 6 DataFrames:

- The Senate Legislations: voting records of all the senators
- The House Legislations: voting records of all the house representatives
- The Politicians: Those who traded in the stock market within the last 3 years
- Committees: Which politicians are members of which committeees
- Trades: The transaction information of each trade
- Stock Data: The price history of each of the congressionally traded stock symbols

#### Caution:

***Keep in mind that because more trades keep happenning daily, a later scraping than mine will yield more politicians and trades than what I've wrangled.***

Once scraped, I moved on to step 2:

### Notebook 2 - Data Cleaning

In notebook 2, I determined which features of each dataset were potentially useful and which could be let go.  
I transformed the voting data from Yes/No to 1/-1  
I created the target variables by searching the stock data for price information related to the stock price near the transaction date.  
I removed any datapoints for which the transaction data could not be useful.

This led to 

### Notebook 3 - Feature Engineering

Using the target variables created in notebook 2, I created scores for each politician by which to measure their performance. I split up the data by chamber and cleaned data a bit more to make the datasets more consistent with each other so they could easily relate to one another.

### Notebook 4 - EDA, Modeling, and Analysis

Here is where I explored the data, made observations on politicians who seem to outperform their peers, and made some models to see if I could predict politicians' successfulness, based on their voting records and committee memberships.

### I hope you enjoy and appreciate the journey!

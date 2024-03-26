# Retirement_Forecasting
The goal of this data project is to create a retirement simulator to see the effects of portfolio investments that are fully invested in the stock market, aggressively invested, moderately invested or conservatively invested.

This idea came from a retirement simulator that I built in excel.

The included Jupyter notebook shows the coding utilized to create a database of future return rates for the stock market, including a series of managed portfolios (aggressive, moderate and conservative).

## Stock Market Data
The stock market returns came from the Sterns school of business, and included a range of historical market values, including T-Bills, Real Estate and Gold.  My analysis focused on market returns

[Stock Market Data Source](https://pages.stern.nyu.edu/~adamodar/New_Home_Page/datafile/histretSP.html)

## Plotting the return rate distributions

After researching historical portfolio performance, I worked with both the mean sample sizes and the return rate columns from the historical table to create return distributions that best matched expected portfolio performance.

While the S&P 500 returns have the greatest spread, this set of returns also has the highest return rate.
As you shift from aggressive down to moderate, the distribution tightens, but the average return rate also decreases. The conservative investment will be the most predictable, but have the lowest average return.

![Rate Distributions](./Images/FutureReturnsDistribution.jpg)

### Research Source:
https://www.sciencedirect.com/science/article/pii/S2405473915000331
I used this article, in addition to working with a local wealth management firm to compare this hypothetical future performance to industry expectations.
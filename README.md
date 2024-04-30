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

**Return Rate Statistics**
After fine tuning my forecasted investment returns, I rand a statistical analysis to validate my results across historical trends.  Note that more aggressive returns will have a wider confidence level, created by the increased votility. Aggressive investors will see a greater return over a long investment window, but this higher return does come with an added risk.

<img src="Images/InvestmentReturnStatistics.png" width="670" height= "211">

### Sources:
[Stock Market Performance](https://www.sciencedirect.com/science/article/pii/S2405473915000331) <br>
I analyzed historical stock trends and consulted with a local wealth management firm to compare this hypothetical future performance to industry expectations.

## A random walk through probability

The random walk theory claims that stock prices are not influenced by history, but rather a random walk that follows an upward slope. Additionally, the Black-Scholes/Merton equation explores the probability distribution of the markets in great depth, focusing on the correlation between brownian motion and the probability distrubtion found in finances.

I investigated the directions of change (derivatives) from 1928 to 2023, and found that the expected distribution resulted in 41 years with an increase in rate of return, and 52 years of decrease. Looking at the visual of my analysis, the stock market was positive for 70 of the 96 years surveyed, and negative for 26 of those years.

The goal of this retirement simulator is to simulate the same patterns found in the historical stock market to forecast the probable distribution of future returns. <br><br>

<img src="Images/StockPatterns.jpg" width="900" height="610">

### Sources:
[Random Walk](https://www.sciencedirect.com/science/article/pii/S2405473915000331) <br>
[Black-Scholes/Merton Equation](https://www.youtube.com/watch?v=A5w-dEgIU1M)

*I can calculate the motion of heavenly bodies, but not the madness of people.” — Sir Isaac Newton.*

## Visualizing variability
After validating my retirement value distributions, I created a retirement simulator function meant to display the inherent variability of investing. The user is asked to enter an initial investement, their investor type (aggressive, moderate, conservative or nervous), and the number of years to forecast. Each entry into the retirement simulator displays 5 sample retirement forecast,an average rate of return, in addition to high and low ends of the results. This simulator effectively works as a roll of the dice, each entry will return varying results.

![Retirement Simulation](./Images/SampleForecast.jpg)

## Learning from the Past
The retirement simulator function was utilized to generate 10,000 hypothetical investment scenarios. Initial investment values were randomly generated, ranging from $100,000 to $2,000,000, with a range of investment years from 10-50. The hypothetical dataset was saved as a CSV and then utilized for machine learning.

*Modeling:* Linear regression, ridge regression, and KNN were the machine learning models tested. A grid search was set up to optimize the parameters for each model.
*Cross-validation:* After assessing the model performance, the KNN model proved to be the best predictor of retirement values. The KNN model was implemented for creating predictions.

### Predicting the Future
In this retirement forecasting method, machine learning is used to analyze this large volume of hypothetical returns to predict a future retirement value based on the user inputs. Rather than a series of samples, the user sees a final, most probable forecast.

*The current prediction model is embedded in the Jupyter Notebook, but will be utilized in a Streamlit app for easier use in the future.*

<img src="Images/Retirement_Prediction.jpg" width="640" height= "176">

Below is a visual showing the data used in the machine learning model.  Note that the more aggressive the investor, the wider the range of variability (shaded bands).  Additionally, despite the nervous investor pulling from the same return table as the aggressive investor, they see the worst portfolio performance. The nervous investor is taught by the model to pull out of the market for 3 years every time the market has negative returns, resulting in poor returns.

![Retirement Forecast](./Images/Years_value_by_investor.jpg)

# The Big Short Part I

The real estate bubble that led to the financial crisis in 2008 resulted in one of the worst economic disasters since the Great Depression of 1929. During this period, housing prices fell precipitously, causing massive ripples throughout the U.S. economy and ultimately causing the stock market to crash. Some keen investors profited off of the recession by *shorting* the market or placing bets that the market would fall. Most, however, lost substantial value from their investment portfolios, including much-needed retirement accounts and savings accounts.

If you had an algorithm to monitor and *short* the market in 2008, could you have possibly *made* money? Create a dual moving average crossover strategy that would have shorted VNQ (Real Estate ETF) stock during the years between 2007 and 2009.

## Part 1 Instructions: The Big Short Part I

* Create a Dual Moving Average Crossover Trading Signal that indicates shorting opportunities.

  * Create a filtered DataFrame containing just the `Date` and `Close` columns of the VNQ stock data.

  * Set the `Date` column as the index to the DataFrame.

  * Set a `short_window` and `long_window` to `50` and `100`, respectively.

  * Create a 50-day moving average and a 100-day moving average from the VNQ closing prices using the `rolling` and `mean` functions.

  * Initialize a new DataFrame column `Signal` and set the values to 0.

  * Use the numpy `where` function to set the signal column to `1.0` when the SMA50 is less than SMA100 and `0.0` otherwise.

  * Use the `diff` function on the `Signal` column and assign the values to a `Entry/Exit` column to indicate trade entry and exit points in time.

* Plot the entry and exit points of your Short Dual Moving Average Crossover signal.

  * Create scatter plots for the entry and exit points. Use the color green to indicate the entry points. Use a second scatter plot with red markers to indicate the exit points.

  * Create line plots for the VNQ closing prices, the 50-day moving average, and the 100-day moving average.

  * Create a composite plot that overlays all of the above into a single plot.

---

## Hints

* Remember that taking a short position (profiting off of selling) is the inverse of taking a long position (profiting off of buying), therefore make sure the decision logic regarding your trading signal reflects this!

* To read more on what a short position is, click [here!](https://www.investopedia.com/terms/s/short.asp)

* Refer to the Holoviews or Hvplot documentation to see how to [compose plots](https://holoviz.org/tutorial/Composing_Plots.html).

---

# The Big Short Part II

Now that you have developed a Short Position Dual Moving Average Crossover Trading Strategy and determined that the algorithm could have *made* money during the 2008 financial recession, it is now time to determine *how much* money could have been made.

## Part 2 Instructions: The Big Short Part II

* Set an `initial_capital` variable to 100000, representing the simulated starting portfolio value.

* Set a negative `share_size` value of -500.

* Create a new column `Position` by multiplying the `share_size` by the values in the `Signal` column.

* Create a new column `Entry/Exit Position` by using the `diff` function on the `Position` column.

* Create a new column `Portfolio Holdings` by multiplying the `Close` prices of VNQ by the cumulative sum of the values of the `Entry/Exit Position` column.

* Create a new column `Portfolio Cash` by subtracting the `initial_capital` by cumulative sum of the product of the `Close` prices of VNQ and the values of the `Entry/Exit Position` column.

* Create a new column `Portfolio Total` by adding the values of the `Portfolio Cash` and `Portfolio Holdings` columns.

* Create a new column `Portfolio Daily Returns` by using the `pct_change` function on the `Portfolio Total` column.

* Create a new column `Portfolio Cumulative Returns` by using the `cum_prod` function on the `Portfolio Daily Returns` column.

* Use the `figure` and `axes` objects of the `matplotlib` library to plot the Short Position Dual Moving Average Crossover trading strategy against its backtesting results.

## Hint

Remember that shorting a stock means to sell shares of a stock and then buy or cover the shares at a later point in time. Therefore, share sizes relative to backtesting calculations should be negative.

---

# The Big Short Part III

Now that you have developed a Short Position Dual Moving Average Crossover Trading Strategy, determined that the algorithm could have *made* money during the 2008 financial recession as well as how much, it is now time to evaluate the performance of the overall portfolio and corresponding trades.

## Part 3 Instructions: The Big Short Part III

Evaluate the backtesting results by calculating the annual return, cumulative returns, annual volatility, Sharpe ratio, and Sortino ratio for your portfolio. These evaluation metrics will provide insight into how well the trading algorithm performed in terms of maximizing returns and minimizing risk and volatility. In addition, evaluate the performance of each trade by grabbing the relevant entry and exit values, and calculate the profit/loss for each trade.

1. Initialize a Portfolio Evaluation DataFrame with an index set to `['Annual Return', 'Cumulative Returns', 'Annual Volatility', 'Sharpe Ratio', 'Sortino Ratio']` and columns as `['Backtest']`.

2. Calculate and assign the following portfolio metrics to the portfolio evaluation DataFrame:

    1. Cumulative Return

    2. Annual Return

    3. Annual Volatility

    4. Sharpe Ratio

    5. Sortino Ratio

3. Initialize a Trade Evaluation DataFrame with columns set to `['Stock', 'Entry Date', 'Exit Date', 'Shares', 'Entry Share Price', 'Exit Share Price', 'Entry Portfolio Holding', 'Exit Portfolio Holding', 'Profit/Loss']`.

4. Iterate over the backtested signals DataFrame and pull the relevant entry and exit data values to calculate the per-trade profit/loss and append each record to the Trade Evaluation DataFrame.

## Hints

* Because this is a short strategy, in order to calculate the profit/loss for each trade, the difference should be the inverse of a long strategy. In other words the profit/loss should be calculated using the entry holding value minus the exit holding value.

* Consult the [evaluations calculation guide](../../../Supplemental/EvaluationsCalculationGuide.md) for the above calculations/formulas.

---
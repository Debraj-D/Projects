
# Discounted Cash Flow Analysis using Free Cash Flow

The project conducts a DCF Analysis of the Reliance Industries Stock on NSE. We compare the market value of the stock to its intrinsic value and come to a conclusion whether the stock is over-valued or under-valued.

The DCF Analysis here is based on the methods given in the book **_Fundamental Analysis for Dummies_**. The summary of the book can be found [here](https://github.com/Debraj-D/Book-Summaries). The DCF Analysis can be found from Pg 32-35.

The `yfinance` library was used to get all the financial data. 

Financial information used :

- Company's free cash Flow
- No. of shares outstanding
- Estimated intermediate term-growth (taken from next year [growth estimates](https://finance.yahoo.com/quote/RELIANCE.NS/analysis/))
- Expected perpetual growth rate (Indian economy growth rate)
- Discount rate (Using CAPM Model)

Equations used :

`CAPM discount rate = risk free rate + (expected market return – risk free rate) × stock’s beta`

- _risk free rate_ : return for taking very little risk with your money. 10 Year Indian Government Bond Yield.
- _expected market return_ : 15 year average NIFTY 50 return.
- _stock's beta_ : how risky a stock is relative to the market. Greater than 1 means more volatile.

`Forecast Cash Flow = Free Cash Flow * (1 + intermediate term growth)^(time)`
- _time_ = forecast year - latest financial data year

`Residual Value = Cash flow in farthest forecast year × (1 + long-term growth rate)/ (Discount rate – long-term growth rate)`
- _long-term growth rate_ : Indian economy growth rate

Discount all forecasted cash flows :  
`Present value = Future value / (1 + discount rate) ^ time`

`Intrinsic Value = Sum (All Discounted Values)`

`Intrinsic Value per share = Intrinsic value/ No of outstanding shares`

#### Comparison

If Intrinsic Value per share :  

 **\>** current stock price - **Undervalued**  
 **\<** current stock price - **Overvalued**

Articles for help :  
[The Secrets of Discounted Cash Flow (DCF) Analysis](https://medium.com/@wl8380/the-secrets-of-discounted-cash-flow-dcf-analysis-a4674d754222)  
[Automate your Discounted Cash Flow model in Python](https://medium.com/@gianlucabaglini/automate-your-discounted-cash-flow-model-in-python-cdf98eb0924d)




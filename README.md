
# Algorthmic Trading Strategy for BTC/USDT

## Market Dynamics

An analysis of the cryptocurrency market dynamics led to the understanding that Bitcoin market prices exhibit strong trend-based momentum, which is ideal for algorithmic trading strategies. This momentum particularly in cryptocurrencies can be attributed to factors such as:

- **Constrained attention of investors**
  
  As cryptocurrency markets operate 24/7, the continuous trading environment may cause retail investors to miss important developments. Their trading activities typically lag with respect to market news headlines and price changes, allowing momentum-based strategies to exploit this delay.

- **Network Effects**
  
  The value and utility of the crypto tokens increases as more users join and develop the blockchain ecosystem. The compounded user growth for these blockchains inherently promotes momentum.

## Proposition

A long-short strategy which aims to capture strong uptrends and make profits in a bullish market.

The strategy makes use of:
- **Technical indicators** which identify the strength of trends and **Momentum** in the market by considering price movements and traded volume.

Risk management measures are also incorporated in the strategy including stop-losses and time-based stops to:
- **Mitigate position risk** and
- **Reduce overexposure to market volatility** with respect to time.

## Data Analysis - Missing Values

Initial analysis of the data revealed that there are certain missing entries in the hourly data provided, shown as follows:

![missing_data](https://github.com/sarthakkapoor44/Inter_iit_12.0/blob/main/assets/missing_data)

## Technical Indicators
![missing_data](https://github.com/sarthakkapoor44/Inter_iit_12.0/blob/main/assets/indicator1.png)
![missing_data](https://github.com/sarthakkapoor44/Inter_iit_12.0/blob/main/assets/indicator2.png)

## Entry and Exit Signals
### Long Position Entry
The following conditions must be satisfied in conjunction to open a long position:
All of these signals in combination give a strong indication of an upwards moving market
- **Smoothed** RSI>70
- **Volume**: Fast SMA > Slow SMA
- **Price** : Fastest EMA > Fast EMA > Slow EMA
- **Aroon Indicator**: Aroon Up < Aroon Down
### Long Position Exit
Once the trend loses strength and momentum goes down, the strategy picks up on this and squares off the long position
The following conditions must be satisfied in conjunction to close a long position:
- **RSI** < 30
- **Volatility Index** > **Vol. Index Moving Average**
As the RSI is now at a very low level, the trend has lost strength and momentum. Additionally since volatility is relatively higher it can indicate a oncoming dip in the price i.e price movement in the opposite direction.

### Short Position Entry
While the market is bullish there are brief periods of pullbacks and price corrections. These movements are also captured by the strategy by entering short positions
The following conditions must be satisfied in conjunction to open a short position:
- **Smoothed RSI**<30
- **Price**: Fastest EMA < Fast EMA < Slow EMA
- **VWAP**: Crosses below Fastest EMA of Price
- **Aroon Indicator**: Aroon Down < Aroon Up
These signals indicate that the price is likely to experience pullback as the trend is weak and traded volume is also relatively lower.

### Short Position Exit
The short positions are intended to be held for short periods of time and rely on relatively faster signals
The following conditions must be satisfied in conjunction to close a short position:
- **VWAP > Fastest EMA of Price**
- **Time-based Stop**: If position has been held for longer than 8 hours

## Risk Management Measures
### Price Level Stop-Losses
To limit the directional risk of the positions, price level stop-losses have been implemented using the upper channel of 24-hour Highest High (HH) and lower channel of 24-hour Lowest Low (LL)
- **Long Position - SL of Lowest Low**
- **Short Position - SL of Highest High**
### Time-based Stops
To limit overexposure to the market volatility, time-based stops have been implemented
- **Long Position** - Maximum holding time is **24 days**
- **Short Position** - If position is held for more than 8 hours and VWAP > Fastest EMA, then the position is squared off

## Backtesting
 Created class BacktestResults to take in the signal logs and compute metric)
- Object-orientedimplementation promotes code modularity
- Separate methods for
  - Viewing different results
  - Data visualizations

## Trade History and Metrics
![missing_data](https://github.com/sarthakkapoor44/Inter_iit_12.0/blob/main/assets/trade_info.png)

  
  | Metric                         | Value           | 
  |--------------------------------|-----------------|
  | Maximum Trade Duration         | 24 days         |                          
  | Average Trade Duration         | 6 days 19 hours |                          
  | Number of Trades               | 59              |                          
  | Winning Trades                 | 43              |                          
  | Losing Trades                  | 16              |                          
  | Win Rate                       | 72.881%         |                          
  | Number of Long Trades          | 23              |                          
  | Number of Short Trades         | 36              |       

## Equity Curves
Evolution of the portfolio balance or net profit/loss made by the strategy
Impact of the strategy on the portfolio when the entire balance at each entry time is invested in the trade (starting balance is $1,000)
![missing_data](https://github.com/sarthakkapoor44/Inter_iit_12.0/blob/main/assets/compounded.png)

## Trade Positions
Indicates the entry and exit positions for both long and short trades on an interactive plot which is available in the Python notebook.
### Long Trade Positions
![missing_data](https://github.com/sarthakkapoor44/Inter_iit_12.0/blob/main/assets/long_trades)
### Short Trade Postions
![missing_data](https://github.com/sarthakkapoor44/Inter_iit_12.0/blob/main/assets/short_trades)
## Drawdowns
![missing_data](https://github.com/sarthakkapoor44/Inter_iit_12.0/blob/main/assets/dd.png)
  | Metric                         | Value           | 
  |--------------------------------|-----------------|
  | Maximum Drawdown               | -6.46%          |                          
  | Benchmark Drawdown             | -81.4%          |    


![missing_data](https://github.com/sarthakkapoor44/Inter_iit_12.0/blob/main/assets/logo.png)


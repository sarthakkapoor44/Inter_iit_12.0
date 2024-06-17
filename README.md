
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
- ** Smoothed RSI>7O
- ** Volume: Fast SMA > Slow SMA
- ** Price: Fastest EMA > Fast EMA > Slow EMA
- ** Aroon Indicator: Aroon Up < Aroon Down

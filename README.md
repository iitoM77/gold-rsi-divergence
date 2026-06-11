# gold-rsi-divergence
seeks to study strategy performance on gold h1 time frame over a period of time
## Strategy Rules

**RSI Settings:** 14  
- Oversold: ≤ 30  
- Overbought: ≥ 70  

### Buy Signal
1. Price forms a swing low with RSI oversold (≤ 31).  
2. Price pulls back to a lower high.  
3. Price breaks the swing low while RSI is ≥ 6 points above its reading at the first swing low.  
4. At least 3 candles must separate the lower-high and the break candle.  

**Entry confirmations:**
- Hammer candle (body ≥ 20%, wick ≥ 80%, body above 60% of candle length).  
- Bullish engulfing pattern (candle 2 bullish, body engulfs candle 1).  
- Bullish Harami setup (candle 1 bullish, body engulfs candle 2 bearish).  
- Triple rejection (3 candles fail to close below the break).  

**Targets:** Previous swing high (lower high).  
**Stop:** At swing low.  
**Risk/Reward:** ≥ 1:1.5 required.  

---

### Sell Signal
1. Price forms a swing high with RSI overbought (≥ 69).  
2. Price pulls back to a lower low (relative to the swing high).  
3. Price breaks the swing high while RSI is ≥ 6 points below its reading at the first swing high.  
4. At least 3 candles must separate the lower-low and the break candle.  

**Entry confirmations:**
- Inverted hammer candle (body ≥ 20%, wick ≥ 80%, body positioned below 40% of candle length).  
- Bearish engulfing pattern (candle 2 bearish, body engulfs candle 1).  
- Bearish Harami setup (candle 1 bearish, body engulfs candle 2 bullish).  
- Triple rejection (3 candles fail to close above the break).  

**Targets:** Previous swing low (higher low).  
**Stop:** At swing high.  
**Risk/Reward:** ≥ 1:1.5 required.  


### project structure
gold-rsi-divergence-strategy/

**data/**  
- raw/                # Exported price data from Pepperstone MT5 (CSV, H1 chart)
- processed/          # Cleaned datasets ready for analysis

**notebooks/**  
- 01_data_extraction.ipynb   # How you pulled data from MT5
- 02_strategy_rules.ipynb    # Walkthrough of RSI divergence rules
- 03_backtest.ipynb          # Backtesting logic + performance metrics
- 04_results_visualization.ipynb # Plots of trades, equity curve, drawdowns

**scripts/**  
- data_loader.py       # Load raw/processed data
- strategy.py          # Encodes buy/sell signal rules
- backtester.py        # Runs trades over historical data
- plot_tools.py        # Candlestick charts, RSI overlays, trade markers

**visuals/**  
- equity_curve.png  
- sample_trade.png  
- rsi_divergence_example.png  
    
- requirements.txt         # pandas, numpy, matplotlib, TA-Lib, etc.
- README.md                # Project overview & usage

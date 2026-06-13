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
- raw/                # Exported price data from XM Global MT5 (CSV, H1 chart)
- processed/          # Cleaned datasets ready for analysis

**notebooks/**  
- 01_backtest.ipynb    # Document how the backtest was run (with code + explanation)
- 02_analysis.ipynb    # Interactive exploration of results

**scripts/**  
- backtest.py          # Your Python backtest simulation code
- report_parser.py     # Parse backtest CSV into structured DataFrame
- metrics.py           # Functions for win rate, Sharpe, drawdown, profit factor
- session_analysis.py  # Break down trades by day/session
- plot_tools.py        # Equity curve, trade distribution, session charts

**visuals/**  
- equity_curve.png  
- session_performace.png  
- day_performance.png  
    
- app.py                   # Streamlit dashboard (main entry point)
- requirements.txt         # pandas, numpy, matplotlib, TA-Lib, etc.
- README.md                # Project overview & usage

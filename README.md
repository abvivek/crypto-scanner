# Crypto order block scanner

Live dashboard using public Binance data. It runs entirely in your browser, needs no keys and never places trades. Educational only, not financial advice.

Open: https://abvivek.github.io/crypto-scanner/

Tabs:
- **Futures by default:** everything runs on Binance USDT-M perpetuals, so longs and shorts are both normal trades. Spot mode is optional (Risk → Market mode).
- **Scanner / Signals:** live order-block setups across the top 50 USDT perpetuals.
- **📊 Coin report:** a live report for any coin.
  - Money flow: taker buy/sell, the trade tape, and OI, funding and long/short when the coin has futures.
  - Liquidity: depth bands, walls, spread and estimated stop clusters.
  - Structure and trend per timeframe, RSI, VWAP, the 50-day SMA and pivots.
  - A verdict with bias score and reasons, the nearest support and resistance, and a setup with a risk check when price is near a zone.
  - Charts, plus performance and correlation vs BTC.
- **🧪 Demo (paper trades):** demo-enter any signal or coin and watch it live. The stop and target close it automatically; it also has P/L in $ and R, a mini chart, a journal, stats, an equity curve and CSV export. Saved in your browser and caught up on 1m candles when you reopen. Futures demos also track leverage, margin, liquidation (closes as "Liquidated") and funding. DEMO only, no real money.
- **⏱ Time Machine:** replays a setup on past candles, with Monte Carlo.
- **Risk:** position sizing for a small futures account: leverage (5x default), isolated/cross, margin, an estimated liquidation price, funding, fees (0.05% taker + 0.02% slippage) and a budget check. Liquidation prices are estimates because Binance's exact maintenance-margin tiers need an API key; real liquidation can be closer, and leverage can lose the whole margin on a gap.
- **Liquidations / Backtest / How it works.**

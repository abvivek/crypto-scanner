# Crypto Futures Scanner

A live order-block and market-structure dashboard for **Binance USDT-M perpetual futures**. It runs entirely in your browser on public Binance data: no API keys, no account, no backend, and it **never places trades**.

**Live:** https://abvivek.github.io/crypto-scanner/

> Educational tool only, not financial advice. Futures with leverage can lose your whole margin quickly.

## Features

| Tab | What it does |
|---|---|
| **Scanner** | Live order-block setups across the top 50 USDT perpetuals, long and short. |
| **Signals** | Fresh entries with entry, stop, target and R:R, plus exit warnings such as pin-bar reversals. |
| **📊 Coin report** | A full live report for any coin. It covers money flow (taker buy/sell, the trade tape, open interest, funding and the long/short ratio), liquidity (depth bands, walls, spread and estimated stop clusters), structure per timeframe, RSI, VWAP, the 50-day SMA and pivots. It ends with a bias score and verdict, nearest support and resistance, a setup when price is near a zone, charts, and performance and correlation vs BTC. |
| **🧪 Demo** | Paper-trade any signal or coin and watch it live. The stop and target close it automatically, liquidation is simulated, and funding is tracked. It shows P/L in $ and R, a journal, stats and an equity curve, and exports CSV. Trades are saved in your browser and caught up from 1m candles when you reopen the page. |
| **⏱ Time Machine** | Replays a setup on past candles and runs a Monte Carlo of possible outcomes. |
| **Risk** | Position sizing for a small futures account. It covers leverage (5x default, 20x cap), isolated or cross margin, margin required, an estimated liquidation price, funding and fees (0.05% taker plus 0.02% slippage). It blocks trades whose stop sits beyond liquidation or too close to it. |
| **Liquidations** | A live liquidation feed from the Binance futures stream. |
| **Backtest** | Historical results of the order-block rules after fees. |
| **How it works** | An explanation of the method and the limits. |

Futures is the default market mode. Spot is optional under **Risk → Market mode**.

## Data sources

- Binance futures REST (`fapi.binance.com`) and WebSocket (`fstream.binance.com`)
- Binance spot REST and WebSocket (only in spot mode)

Everything is fetched straight from your browser. Nothing is stored on a server.

## Honest limits

- **Liquidation prices are estimates.** Binance's exact maintenance-margin tiers need an API key, so the real liquidation can come sooner.
- **Backtests:** on 1h and 5m, order-block entries lost money after fees, and 4h was roughly breakeven. Treat signals as ideas to check, not trades to copy. Use the Demo tab first.
- **Demo trades live in one browser.** Clearing site data or switching devices loses them. Export CSV to keep a copy.
- **Mobile:** iOS Safari pauses background tabs, so demo trades update when you reopen the page.

## Run locally

It's a single self-contained file:

```bash
git clone https://github.com/abvivek/crypto-scanner.git
cd crypto-scanner
python3 -m http.server 8000   # then open http://localhost:8000
```

## Disclaimer

This is not investment advice. Crypto futures are high risk. Only trade money you can afford to lose.

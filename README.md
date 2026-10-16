# TradeLab Crypto — Version 1

A phone-friendly, static crypto research dashboard for historical Binance spot candles and paper trading. It does not send real orders.

## Features
- BTCUSDT, ETHUSDT, SOLUSDT
- 5m, 15m and 1h historical candles
- EMA 20, EMA 50, ATR(14), simple rule-based setup
- Entry, stop, target, quantity and risk/reward calculator
- Browser-local paper-trade journal
- No API key and no paid software required for the prototype

## Important limitations
- Uses Binance public spot market-data API. Availability and rate limits can change.
- Not guaranteed to be real-time; the latest candle may still be forming.
- This prototype is for learning and paper trading, not financial advice.
- The rule score is not a probability of winning.
- Paper trades are simplified; fees, slippage, funding, spreads, taxes, and execution quality are not fully modeled.
- Paper journal data stays in localStorage on this browser/device. It is not synced between devices.
- Do not add real broker keys or real-money order execution to this prototype.

## Easiest way to use on a phone
1. Extract the ZIP if your phone supports it.
2. Upload `index.html` to a GitHub repository.
3. In the repository, open Settings → Pages.
4. Choose deploy from a branch, select `main` and `/ (root)`, then save.
5. Wait for GitHub Pages to publish the site and open the provided URL on your phone.
6. Press Refresh data if candles do not load.

GitHub Pages is for static files. This project intentionally does not need a backend server.

## Local development on a computer (optional)
Python 3 is enough to serve the static page:

```bash
python -m http.server 8000
```

Open `http://localhost:8000` in a browser. This command must be run from the folder containing `index.html`.

## Strategy outline
The prototype calculates EMA 20, EMA 50 and ATR(14). It uses the previous candle for its setup checks. A long/short candidate requires a trend condition plus a simple EMA pullback/reclaim condition. This is only an example rule set and has not been demonstrated to be profitable.

## Manual test checklist
1. Open the site and confirm a pair and timeframe are selected.
2. Confirm candle data and timestamp/status load.
3. Switch BTCUSDT → ETHUSDT → SOLUSDT.
4. Switch 5m → 15m → 1h.
5. Check EMA/ATR values appear after candles load.
6. Press “Use suggested setup”; entry, stop and target should fill.
7. Adjust risk percent and confirm quantity updates.
8. Open a paper trade and confirm it appears in the journal.
9. Close it manually and confirm P/L changes.
10. Refresh the page and confirm the journal remains in this browser.
11. Test on mobile portrait and landscape.
12. If data fails, check internet access and retry later.

## Project structure
```text
crypto-trading-v1/
├── index.html
└── README.md
```

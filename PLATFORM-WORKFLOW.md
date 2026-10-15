# AuraFX platform workflow mapped from the supplied screenshots

## 1. Sign in and account setup
- Register/log in; display an explicit demo-only warning until server-backed authentication exists.
- Account management should include profile/contact details, verification status, funding history, statements, account reports, and active sessions.

## 2. Top navigation
- Workspace selector: switch saved workspace layouts (future backend/local preference feature).
- Universal symbol search for forex, indices, commodities, crypto and stocks, subject to the chosen licensed data feed.
- Demo/live environment indicator. The current build is DEMO ONLY; do not add a live toggle until a broker/execution backend is implemented and certified.
- Account strip: cash balance, equity, used/free margin and P/L.
- Funding, notification bell, and gear/settings controls.

## 3. Left navigation
- Watchlists: Popular Markets, Forex Majors, Indices, Commodities, Crypto; custom lists/favorites.
- Markets/Browse: filter by asset class/region/movement and open an instrument detail view.
- News & Analysis: licensed news feed, economic calendar (GDP, CPI, NFP), analyst research and sentiment. These need external data providers; no feed is fabricated in this prototype.
- Performance/SMART Signals: pattern alerts and metrics such as win rate, average hold time and risk/reward. Signals must be labeled informational, not guaranteed recommendations.
- Account Management & History: funding, statements, account reports and verification status.

## 4. Charting workspace
- Main chart with candlestick/line modes; target future support for bar, Heikin-Ashi, Renko, point-and-figure, area and baseline charts.
- Timeframes from seconds/minutes to monthly require a market-data provider and sufficient historical bars.
- Indicators: moving averages, RSI, MACD, Bollinger Bands, Fibonacci and stochastic; drawing tools include trendlines, channels and ranges.
- Compare-symbol overlays and multi-chart layouts (2x2/4x4) are planned UI features, not yet implemented in this prototype.

## 5. Order ticket and risk controls
- Market, limit and stop orders; size in units/lots (standard 100,000, mini 10,000, micro 1,000 where the instrument contract specifies these values).
- Stop loss, take profit and trailing stop controls; optional guaranteed stop loss only if the broker offers it in the user's jurisdiction.
- Order preview should show bid/ask, estimated margin, estimated P/L and a confirmation step. One-click trading should be opt-in and disabled by default.
- Real execution requires server-side validation and a broker API. Browser-only order state is not authoritative.

## 6. Bottom activity panel
- Positions: open trades, unrealized P/L, entry/current price, margin, SL/TP; edit stops, partial close and close-all.
- Orders: pending limit/stop orders and cancellation.
- Price alerts: thresholds and optional email/push/sound notifications.
- History: closed trades, realized P/L, swaps/rollover fees and transactions.

## 7. Platform settings
- Theme selector: System / Light / Dark. System follows `prefers-color-scheme` and reacts when the device theme changes.
- Language and display currency (currency conversion needs reliable FX rates).
- Trading preferences: one-click mode, default size, default SL/TP distances and pip/percentage units.
- Notifications: fills, executions, margin warnings and price alerts; delivery needs notification/email infrastructure.
- Security: authenticator-app or SMS 2FA, active sessions/devices, password and verified phone updates. These require server-side identity/session management.

## 8. Funding, KYC and compliance
- Deposit/withdrawal requests must be created by the backend and reconciled against verified payment-provider webhooks. Never credit an account based only on a browser response.
- Withdrawals require server-side balance/available-margin checks, KYC/AML checks, fraud controls, audit trails and provider payout confirmation.
- KYC documents must be uploaded to private access-controlled storage; do not store IDs/selfies in localStorage.
- Production operation may require licensing, disclosures and provider approval in each target jurisdiction.

## Implementation status
The current files provide a front-end demo with simulated quotes, localStorage data and demo payment responses. The theme selector supports `system`, `light`, and `dark`; mobile styles have been improved. Many screenshot-listed features above are a build specification, not yet functional modules. Do not use this build for real funds.

## Expanded UI added in this revision
- Header now includes universal symbol search, workspace presets, a visible DEMO ONLY label, a quick funding shortcut, notifications, and a settings shortcut.
- New Markets/Browse page groups demo instruments by category.
- New News & Analysis page documents the integration slots for licensed headlines, analyst research and economic calendar events; it deliberately does not invent live news.
- New Performance Analytics page calculates basic statistics from locally stored demo trade history and clearly labels signals as unavailable until a strategy/data provider is connected.
- The trade page now has activity tabs for Positions, Orders, Price Alerts, Trade History and Account Ledger. Price alerts can be saved locally and are not push notifications; pending-order execution remains unimplemented.
- Settings now include System/Light/Dark appearance, language and display-currency preferences, demo leverage, default lot size, default stop-loss/take-profit distances, distance units, order confirmations, one-click preference, and notification preferences.
- Security settings explain that password changes, server sessions, phone verification and SMS/authenticator 2FA require backend identity/session services.
- All client-side data remains demo-only. No real payment processing, real broker execution, guaranteed stop loss, external market feed, live news, push notifications or secure server-side authentication is provided by these files.

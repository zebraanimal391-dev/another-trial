AuraFX updated demo prototype
=============================

Startup fixes:
- HTML paths match the flat folder layout.
- Visible startup errors are displayed if initialization fails.
- Theme setting supports System / Light / Dark; System follows the device preference and responds to OS theme changes.
- Responsive CSS improved for Android/mobile layouts.
- UI clearly labels prices and wallet actions as simulated/demo-only.
- PLATFORM-WORKFLOW.md maps the supplied screenshots to implementation requirements and flags features that still need development.

Local Android testing:
1. Extract this folder.
2. Start a local HTTP server in the folder, e.g. `python -m http.server 8000`.
3. Open http://127.0.0.1:8000/ in Chrome. Admin demo page: /admin.html.

IMPORTANT: Not production-ready for real-money trading.
- Market prices are random simulations, not a real market feed.
- User records, balances, positions and KYC are browser localStorage.
- Admin access is client-side and can be bypassed.
- Payment API is a demo and can simulate successful payments; no real provider backend is included.
- Do not accept real deposits, issue real withdrawals, or collect actual identity documents.

Production requires server-side authentication/authorization, secure database, verified payment webhooks, broker/execution integration, private KYC storage, audit logs, reconciliation, monitoring, and applicable licensing/compliance. Never put provider secret keys in browser JavaScript. Do not merely set PaymentAPI.live=true; the referenced backend does not exist.

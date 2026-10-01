# Strike Price Lab – iPhone PWA

This version is optimized for iPhone 13 Pro and can be installed from Safari as a Home Screen app.

## Core validated formula

For a selected horizon:
- Adjusted Performance = Historical Performance ($) / Holding Divisor
- Projected Target = Current Price + Adjusted Performance
- High = Projected Target
- Mid = Projected Target × (1 - Correction/2)
- Low = Projected Target × (1 - Correction)
- Each target is rounded upward to the selected strike increment

Validated against the supplied thinkBig AAPL example from July 24, 2023:
- Price: $192.75
- 1-year Performance: $39.57
- Divisor: 2
- Correction: 10%
- Low $192 / Mid $202 / High $213

## Default divisors
- 3M: ÷2
- 6M: ÷2
- 1Y: ÷2
- 2Y: ÷1.5
- 3Y: ÷2 (editable)

## Install on iPhone
A PWA needs to be served over HTTPS. A free host such as GitHub Pages or Netlify works.

On iPhone:
1. Open the hosted URL in Safari.
2. Tap Share.
3. Tap Add to Home Screen.
4. Tap Add.

## Windows hosting (simple GitHub Pages route)
1. Create a new GitHub repository.
2. Upload all files from this folder to the repository root.
3. Open repository Settings → Pages.
4. Under Build and deployment, choose Deploy from a branch.
5. Select `main` and `/ (root)`, then Save.
6. Open the generated `https://<username>.github.io/<repo>/` URL on iPhone Safari.
7. Share → Add to Home Screen.

## Data
- Manual mode works without any external service.
- Optional Alpha Vantage mode uses GLOBAL_QUOTE + TIME_SERIES_WEEKLY.
- API key is stored in browser localStorage on the device.
- Freshness and availability depend on the Alpha Vantage plan.

## Files
- index.html – entire UI and calculator
- manifest.webmanifest – install metadata
- sw.js – offline cache/service worker
- icons/ – Home Screen icons

# Portfolio Rebalance Tool

Set target allocations across buckets, enter what you currently hold in each, and get the exact dollar amount to buy or trim in every bucket to return to target. The tool runs entirely in your browser, shows current versus target as paired bars, and totals the buys and trims.

**Live demo:** https://0xelitesystem.github.io/portfolio-rebalance-tool/

**Not financial advice.** This is arithmetic on numbers you type. It does not know your tax situation, trading costs, or what you should own. It only computes the deltas between your current and target weights.

## What it does

The Portfolio Rebalance Tool takes a set of buckets, each with a current dollar value and a target percent, and computes the rebalance. It sums your holdings to a total, multiplies that total by each target percent to get the target dollar amount, and reports the difference as a buy or a trim. Buckets within half a percent of target are marked hold.

Targets that do not sum to 100 percent are flagged, and a single click normalizes them proportionally so the weights balance.

## Use

1. Open `index.html` in a browser, or visit the GitHub Pages site.
2. Edit the bucket names, current values, and target percents. Add or remove buckets as needed.
3. If the targets do not sum to 100 percent, click normalize.
4. Read the action column for each bucket and the buy and trim totals at the bottom.

## Why this exists

Rebalancing is simple arithmetic, but brokerage and budgeting tools that do it want your account linked first. This is one HTML file that works only on the numbers you type, in your browser, with no tracking. MIT licensed.

## Inputs and outputs

Each row holds a bucket name, its current dollar value, and its target percent. The tool outputs, per bucket, the current weight versus target weight as bars and the buy or trim amount, plus a portfolio total and the summed buy and trim figures.

## Method and assumptions

Target dollars for a bucket equals the portfolio total times that bucket's target percent. The delta is target dollars minus current dollars: positive means buy, negative means trim. The tool assumes you rebalance to the current total without adding or withdrawing cash, so total buys equal total trims when targets sum to 100 percent. Fees and taxes are not modeled.

## Privacy

Runs fully client side. No analytics, no network calls, no storage of anything you enter. The only thing the page writes to your browser is your light or dark theme choice, saved in localStorage under the key `theme` when you press the theme button, so the page opens in the same theme next time. Clear site data to remove it. Your numbers never leave the page.

## Run locally

```
git clone https://github.com/0xelitesystem/portfolio-rebalance-tool
cd portfolio-rebalance-tool
```

Then open `index.html` in any browser. Or serve the folder with `python -m http.server` and visit http://localhost:8000.

## Build

No build step. The whole tool is one file, `index.html`, with its CSS and JavaScript inline.

## Related tools

- [position-size-risk-math](https://github.com/0xelitesystem/position-size-risk-math)
- [dca-visualizer](https://github.com/0xelitesystem/dca-visualizer)

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT. Copyright RBL Industries LLC 2026.

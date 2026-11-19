# Topological & Structural Analysis of the Indian Stock Market

Network science assignment (ECS414/614, 2026–27-I term, IISER Bhopal).
A correlation network is built from one year of daily returns of Nifty 500 stocks and analysed with degree distribution, centrality, clustering with sector homophily, and threshold sensitivity.

## Contents

| File | Description |
|---|---|
| `NS_Assignment.ipynb` | Colab notebook with the full pipeline, plots and interpretations |
| `Report.pdf` | Final report (introduction, methodology, results, discussion, conclusion) |
| `nifty500_constituents.csv` | Nifty 500 list from NSE (company, industry, symbol, ISIN) |
| `nse_historical_prices.csv` | Daily adjusted close prices from yfinance (dates × tickers) |

## Method in brief

1. Download the Nifty 500 list and one year of adjusted close prices (`yfinance`, ticker = symbol + `.NS`), saved locally.
2. Compute daily log returns: R_i(t) = ln(P_i(t) / P_i(t-1)).
3. Build an unweighted graph: connect stocks i and j if the Pearson correlation of their returns exceeds r (main analysis r = 0.5).
4. Analyses: (A) degree distribution, (B) top-10 degree, betweenness and eigenvector centrality, (C) clustering and sector homophily, (D) threshold sensitivity.

## Main results (r = 0.5, 491 stocks, 2291 edges)

- Heavy-tailed degree distribution with a few hubs (max degree 114), but an exponential tail fits better than a power law.
- Hubs are financial and domestic-cycle mid-caps (UCO Bank, Jio Financial, Shriram Finance), not index heavyweights.
- Average clustering is about 20 times that of a random graph; 37.7% of edges join stocks of the same sector.
- The network breaks into small clusters above r ≈ 0.65.

## How to run

1. Open the notebook in Google Colab.
2. Run all cells. If the two CSV files are in the working folder they are reused, so no download is needed. Delete them to force a fresh download.

Requirements: `yfinance`, `pandas`, `numpy`, `networkx`, `matplotlib`, `seaborn`, `scipy`.

## Author

Suresh Chandra, Roll No. 23340

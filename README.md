# 📊 Hyperliquid Trader Behavior vs Market Sentiment Analysis

> Uncovering how Bitcoin market sentiment shapes trader behavior and performance on Hyperliquid.

---

## 📌 Project Objective

This project analyzes how Bitcoin market sentiment (Fear/Greed Index) relates to trader behavior and performance on Hyperliquid. The goal is to uncover behavioral patterns and propose actionable trading strategy adjustments.

---

## 📂 Dataset

### Bitcoin Market Sentiment
| Column | Description |
|--------|-------------|
| `date` | Date of sentiment reading |
| `classification` | Sentiment category |
| `value` | Numeric sentiment score |

**Categories:** `Fear` · `Neutral` · `Greed` · `Extreme Greed`

### Hyperliquid Historical Trade Data
| Attribute | Detail |
|-----------|--------|
| Total Trades | 211,224 |
| Trader Accounts | 32 |
| Trading Days | 7 |
| Key Fields | `size`, `PnL`, `side`, `timestamps` |

---

## ⚙️ Methodology

### 1️⃣ Data Preparation
- Cleaned column names and standardized formatting
- Converted Unix timestamps (milliseconds → datetime)
- Aligned datasets at daily level
- Created key metrics:
  - Daily PnL
  - Win rate
  - Trade frequency
  - Position size
  - Long/Short ratio

### 2️⃣ Performance Analysis
Compared the following metrics across sentiment regimes:
- Average PnL
- Win rate
- Large-loss probability (drawdown proxy)

### 3️⃣ Behavioral Segmentation
Applied **KMeans clustering** on the following features:

| Feature | Description |
|---------|-------------|
| Average PnL | Mean profit/loss per trade |
| Volatility | Variability in returns |
| Trade Size | Typical position size |
| Trade Frequency | Number of trades per period |
| Win Rate | Proportion of profitable trades |
| Long/Short Bias | Directional trading tendency |

**Identified 3 behavioral archetypes:**

| Cluster | Archetype |
|---------|-----------|
| 🔵 Cluster 1 | Structured high-volume traders |
| 🟡 Cluster 2 | Low-edge retail traders |
| 🔴 Cluster 3 | High-risk speculative traders |

---

## 🔍 Key Insights

- **Sentiment ≠ Direct Profit Driver** — Sentiment shows weak direct linear correlation with trade profitability.
- **Extreme Greed is Dangerous** — Extreme Greed periods show the highest probability of large losses.
- **Overtrading Hurts** — Higher trade frequency is associated with reduced profitability.
- **Risk-Return Tradeoff Holds** — Higher returns are associated with significantly higher return volatility.
- **Traders Cluster Naturally** — Distinct behavioral archetypes emerge independent of sentiment conditions.

---

## 🚀 How to Run

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 3. Run the analysis

Open and run `sentiment_analysis.ipynb` from the Jupyter interface.

---

## 🗂️ Project Structure

```
├── sentiment_analysis.ipynb   # Main analysis notebook
├── requirements.txt           # Python dependencies
├── data/
│   ├── sentiment.csv          # Bitcoin Fear/Greed Index data
│   └── hyperliquid_trades.csv # Hyperliquid historical trade data
└── README.md
```

---

## 🛠️ Tech Stack

- **Python** — Data processing and analysis
- **Pandas / NumPy** — Data manipulation
- **Scikit-learn** — KMeans clustering
- **Matplotlib / Seaborn** — Visualization
- **Jupyter Notebook** — Interactive analysis environment

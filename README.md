# DSC8307 — Data Mining, Modelling and Analytics: Olist E-commerce Project

Practical work for the Advent 2026 project-based examination (MSc Data Science and Analytics, Uganda Christian University).
The analysis uses the public [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).

## What is in this repository

| Path | Content |
|---|---|
| `olist_analysis.ipynb` | The complete analysis (Tasks 1–5), saved with outputs. Runs top to bottom. |
| `requirements.txt` | Pinned dependencies |
| `data/brazilian-ecommerce.zip` | The unmodified Kaggle download, extracted automatically on first run |
| `figures/` | All figures produced by the notebook. File numbers match the figure numbers in the report (`fig4_seller_segments.png` is Fig. 4); `figS1_k_selection.png` is supplementary |
| `outputs/` | Tables and key results produced by the notebook (`results.json`, association rules, seller segment profiles, unusual-order review queue, rolling-origin and forecast-gap evaluations) |

## How to run

Tested with Python 3.13 (Python 3.11 or newer recommended).

```bash
git clone <this-repo-url>
cd dsc8307-olist-ecommerce
python -m venv .venv
# Windows: .venv\Scripts\activate    macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute olist_analysis.ipynb --output olist_analysis.ipynb
# or open it in Jupyter and choose "Run All"
```

A full run takes about 6–10 minutes on a typical laptop. A fixed random seed (42) is used throughout.

## Tasks covered

1. Data exploration, integrity checks and preparation, with justification
2. Category co-purchase patterns: Apriori association rules with Fisher tests, FDR control and threshold sensitivity
3. Seller segmentation: k-means with silhouette, Davies–Bouldin and bootstrap-stability selection, plus cross-algorithm checks
4. Unusual orders: integrity rules + Isolation Forest / LOF consensus, external validation and a tiered review queue
5. Late-delivery classification and delivery-time regression: a pre-specified main analysis (features fixed before the test block was opened), baselines, out-of-time, rolling-origin and forecast-gap validation, rolling ablation, calibration, conformal prediction intervals and SHAP, plus a clearly labelled post-hoc exploratory feature redesign

## Data licence and attribution

Data: Olist, "Brazilian E-Commerce Public Dataset by Olist", Kaggle, 2018, licensed CC BY-NC-SA 4.0. It is redistributed here unmodified, for non-commercial academic use, with attribution.

# E-commerce Customer Segmentation

## Problem

This project groups retail customers by purchasing behavior using customer-level Recency, Frequency, and Monetary (RFM) features, then profiles the groups and trains a classifier to reproduce K-Means membership.

## Dataset

The bundled `data/data.csv` has 541,909 rows and the transaction columns expected by the loader. The project README identifies it as the UCI Online Retail dataset based on its row count and columns, but the file's provenance has not been independently confirmed. TODO: verify the source before citing UCI as the origin.

## Segments

The recorded k=2 run selects two profiles by RFM means. Lower Recency indicates a more recent purchase; higher Frequency and Monetary indicate more invoices and spend.

| Segment | Cluster | Customers | Mean Recency (days) | Mean Frequency (invoices) | Mean Monetary | Revenue share |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| High-Value Active | 0 | 1,665 | 25.85 | 8.32 | 4,082.86 | 85.05% |
| Low-Value Lapsing | 1 | 2,649 | 134.96 | 1.65 | 451.21 | 14.95% |

The k=4 profile is retained as an alternative in `outputs/analysis_results.json`.

## How to Run

From this folder, with the repository dependencies installed:

```powershell
python main.py
```

From the repository root, run `python CapstoneEcommerceSegmentation/main.py`.

## Package Map

| Module | Purpose |
| --- | --- |
| `data_loader.py` | Loads and summarizes transaction data. |
| `preprocessing.py` | Cleans transactions and calculates line-item revenue. |
| `features.py` | Builds customer RFM features and applies `log1p` and standard scaling. |
| `clustering.py` | Evaluates K-Means cluster counts, compares clustering algorithms, profiles segments, and assesses stability. |
| `classifier.py` | Trains a stratified Random Forest to reproduce segment membership. |
| `evaluation.py` | Calculates classifier metrics and feature importance. |
| `visualization.py` | Creates clustering, segment-profile, and classifier-result charts. |
| `eda.py` | Creates transaction and RFM exploration charts. |
| `main.py` | Runs the analysis and writes the JSON outputs. |

## Dashboard

Open `dashboards/index.html` in a local web server. It reads `outputs/dashboard_data.json` and displays the segment names from its profile records.

## Recorded Run

The current generated outputs record k=2, silhouette 0.4312, cluster sizes 1,665 and 2,649, and mean seed/bootstrap stability ARIs of 0.994 and 0.989. The comparison runs K-Means, hierarchical clustering, and DBSCAN at the selected k and at k=4. K-Means candidates from k=2 through k=10 are evaluated separately by inertia and silhouette.

The Random Forest predicts labels created by K-Means from the same RFM features. Its accuracy measures reproduction of those labels, not prediction of future purchases.

## Presentation

- `reports/Capstone_Ecommerce_Segmentation.pptx` is the final presentation with speaker notes and is the master copy. Edit slide text, charts (right-click, then **Edit Data**), and notes directly in PowerPoint.
- `reports/build_deck.py` is the archived generator for the first deck version. It writes a separate rebuilt presentation and does not overwrite the master deck.
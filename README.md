# BIA — Data Science & AI Projects

Projects from my Diploma in Data Science & AI at Boston Institute of Analytics, Kolkata.

## Projects

| Project | What it does | Techniques | Dataset |
| --- | --- | --- | --- |
| [Capstone](./CapstoneEcommerceSegmentation/) | Segments retail customers by purchasing behavior. | RFM, K-Means, hierarchical clustering, DBSCAN, Random Forest | Online Retail (`data/data.csv`; source provenance TODO) |
| [AdvancedNLP](./AdvancedNLP/) | Classifies IMDB reviews as positive or negative. | LSTM, local GloVe embeddings, tokenization | `IMDB.csv`, `glove.txt` |
| [DecisionTreesEnsembleMethods](./DecisionTreesEnsembleMethods/) | Classifies Iris species. | Decision Tree; optional Random Forest | Iris CSV |
| [DeepLearning](./DeepLearning/) | Classifies images into ten categories. | Convolutional neural network | CIFAR-10 via Keras |
| [DimensionalityReductionFeatureSelection](./DimensionalityReductionFeatureSelection/) | Compares two Iris classification workflows. | PCA, interaction feature, Random Forest | Iris CSV |
| [LogisticRegressionClassificationMetrics](./LogisticRegressionClassificationMetrics/) | Classifies Titanic survival. | Logistic regression, imputation, outlier capping, one-hot encoding | `titanic.csv` |
| [MachineLearningIntroduction](./MachineLearningIntroduction/) | Predicts housing prices. | Simple linear regression, preprocessing, evaluation | Custom housing CSV |
| [ModelEvaluationValidationTechniques](./ModelEvaluationValidationTechniques/) | Classifies Apple stock price direction. | Random Forest, GridSearchCV, cross-validation | Apple stock CSV |
| [MultipleLinearRegressionModelEvaluation](./MultipleLinearRegressionModelEvaluation/) | Predicts vehicle fuel economy (`mpg`). | Multiple linear regression, preprocessing, regression metrics | `car_mileage_dataset.csv` |
| [NLP](./NLP/) | Classifies IMDB reviews as positive or negative. | Embedding, Flatten, Dense neural network | `IMDB.csv` |
| [RNNandLSTMDeeplearningmodels](./RNNandLSTMDeeplearningmodels/) | Predicts stock closing prices from preceding trading days. | RNN and LSTM | `Stock_price.csv` |
| [SVM-KNN](./SVM-KNN/) | Compares Iris classification models. | Linear SVM, 3-neighbor KNN | Iris CSV |
| [TimeSeriesModeling](./TimeSeriesModeling/) | Forecasts monthly rainfall for the Auser aquifer series. | ARIMA, chronological holdout | Auser aquifer CSV |
| [UnsupervisedLearning](./UnsupervisedLearning/) | Clusters wholesale customers by spending features. | K-Means, agglomerative clustering, elbow method, silhouette score | Wholesale customers CSV |

## Capstone highlights

- Modular Python package: `data_loader`, `preprocessing`, `features`, `clustering`, `classifier`, `evaluation`, `visualization`, and `main`; analysis and dashboard data are exported as JSON.
- RFM features are log-transformed and scaled. Monetary skewness is 20.3 before and 0.4 after `log1p` on the bundled data.
- K-Means is evaluated for k=2–10; k=2 is selected at silhouette 0.431, and k=4 is documented as an alternative. The three clustering algorithms are compared at k = 2 and 4.
- Stability uses 20 seed refits and 20 bootstrap refits; mean ARIs are 0.994 and 0.989.
- A 200-tree Random Forest predicts K-Means segment membership from RFM features.

## How to run

Create and activate a virtual environment, install the repository dependencies, then enter a project and run its entry point:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
cd CapstoneEcommerceSegmentation
python main.py
```

For the capstone, start at `main.py` — the notebook is a short runner over the modules. For another project, change into its folder and follow its README if it requires additional arguments.

## License

This project is licensed under the MIT License; see [LICENSE](LICENSE) for details.

**Last Updated:** 2026-10-18
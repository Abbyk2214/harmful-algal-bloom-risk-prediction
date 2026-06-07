# Harmful Algal Bloom Risk Prediction in Maryland Waterways

## Overview

This project uses machine learning to predict harmful algal bloom (HAB) risk in Maryland waterways using publicly available water quality data from the Water Quality Portal (EPA/USGS).

## Dataset

### Data Source
- Water Quality Portal (WQP) API
- EPA and USGS water quality monitoring data

### Study Area
- Maryland waterways

### Time Period
- 2014–2024

### Raw Dataset Size
- Over 1 million water quality observations

## Data Preprocessing

### Preprocessing Steps
1. Downloaded water quality observations from the Water Quality Portal API.
2. Combined yearly downloads into a single dataset.
3. Selected relevant environmental variables.
4. Converted data from long format to wide format.
5. Handled missing values using median imputation.
6. Created a binary target variable representing bloom risk.

### Target Variable Definition

- High Risk = Chlorophyll-a > 25
- Low Risk = Chlorophyll-a ≤ 25

### Final Modeling Features
- Dissolved Oxygen (DO)
- Water Temperature
- pH

**Note:** Nitrogen and phosphorus were downloaded but excluded from the final model due to substantial missing values.

### Final Modeling Dataset
- 30,159 observations
- 3 predictor variables
- 1 target variable

## Machine Learning Models

- Logistic Regression
- Random Forest
- XGBoost
- Tuned Random Forest

## Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

## Results

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---------|---------|---------|---------|---------|---------|
| Logistic Regression | 0.651 | 0.244 | 0.594 | 0.346 | 0.684 |
| Random Forest | 0.827 | 0.446 | 0.467 | 0.457 | 0.795 |
| XGBoost | 0.740 | 0.328 | 0.639 | 0.433 | 0.766 |
| Tuned Random Forest | 0.814 | 0.420 | 0.518 | 0.464 | 0.797 |

## Key Findings

- Water temperature was the strongest predictor of harmful algal bloom risk.
- Ensemble models outperformed Logistic Regression.
- Tuned Random Forest achieved the best overall performance.
- Machine learning can support environmental monitoring and early warning systems.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- Folium
- Requests

## Future Improvements

Several opportunities exist to improve the performance and scope of this project:

- Incorporate additional environmental variables such as rainfall, nutrient runoff, and watershed characteristics.
- Integrate satellite imagery and remote sensing data to better capture bloom conditions.
- Expand the study beyond Maryland waterways to evaluate model performance across different geographic regions.
- Explore advanced machine learning and deep learning techniques.
- Implement time-series forecasting methods to predict bloom events before they occur.

These improvements may increase predictive accuracy and provide stronger support for environmental monitoring efforts.

## Conclusion

This project demonstrated the application of machine learning to environmental monitoring by predicting harmful algal bloom risk in Maryland waterways.

Using over 1 million water quality observations collected from the Water Quality Portal API, a complete data science workflow was developed, including data acquisition, preprocessing, feature engineering, model development, and evaluation.

Among the evaluated models, the Tuned Random Forest achieved the strongest overall performance. Feature importance analysis revealed that water temperature was the most influential predictor, followed by dissolved oxygen and pH.

The results show that machine learning can help identify conditions associated with harmful algal bloom risk and may support future environmental management and water quality decision-making efforts.

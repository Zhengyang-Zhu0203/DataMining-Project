# DataMining-Project
### Project Title  
**Building a Machine Learning Model for Weather Type Prediction Using Multidimensional Meteorological and Environmental Data**  

**Author**  
Zhengyang Zhu


#### Abstract  
This project develops a **Random Forest classifier** to predict weather types (Sunny, Rainy, Cloudy, Snowy) using 11 meteorological and environmental features (e.g., Temperature, Humidity, Precipitation). The model achieves **97.5% accuracy** on a test dataset, outperforming K-Nearest Neighbors (KNN), XGBoost, and Logistic Regression. Key findings highlight the importance of Temperature, UV Index, and Precipitation in weather classification. Future work could explore real-time data integration and hyperparameter optimization for edge devices.  


#### Rationale  
Accurate weather prediction is critical for industries like agriculture, transportation, and energy management. For example:  
- **Agriculture**: Reduces crop yield variability by 15–20% (FAO, 2023).  
- **Transportation**: Lowers weather-related accidents by 30% (U.S. Federal Highway Administration).  
- **Disaster Preparedness**: Cuts economic losses from extreme weather by up to 40% (WMO, 2022).  
Reliable models enable proactive decision-making, enhancing safety and sustainability.  


#### Research Question  
Can a machine learning model accurately classify weather types (Sunny, Rainy, Cloudy, Snowy) using historical meteorological data, and which features are most influential in this classification?  


#### Data Sources  
- **Dataset**: Historical weather data containing 13,200 samples with 11 features:  
  - Numerical: Temperature, Humidity, Wind Speed, Precipitation (%), Atmospheric Pressure, UV Index, Visibility (km), Weather Severity Index (engineered feature).  
  - Categorical: Season, Location, Cloud Cover.  
- **Target Variable**: Weather Type (4 classes).  


#### Methodology  
1. **Data Preprocessing**:  
   - Label encoding for categorical features (Season, Location, Cloud Cover).  
   - Outlier removal using the IQR method, eliminating 1,514 outliers.  
   - Feature scaling with StandardScaler for Wind Speed, UV Index, and Visibility.  
   - Engineered feature: **Weather Severity Index** (weighted sum of Temperature, Humidity, Wind Speed, Visibility).  

2. **Model Development**:  
   - **Random Forest Classifier** chosen for handling mixed data types, non-linear relationships, and robustness to outliers.  
   - Hyperparameter tuning via **sequential grid search** with **Greedy choice** optimized parameters:  
     - `n_estimators=220`, `max_depth=20`, `max_features='sqrt'`.  

3. **Evaluation**:  
   - Metrics: Accuracy, Precision, Recall, F1-Score, Confusion Matrix, ROC-AUC, and Learning Curves.  
   - Cross-validation: 5-fold CV with train-test split (80%/20%).  


#### Results  
- **Model Performance**:  
  | Model               | Accuracy | F1-Score | Recall |  
  |---------------------|----------|----------|--------|  
  | Random Forest       | **97.5%**| 0.976    | 0.975  |  
  | XGBoost             | 96.9%    | 0.969    | 0.969  |  
  | KNN                 | 94.7%    | 0.947    | 0.947  |  
  | Logistic Regression | 93.3%    | 0.933    | 0.934  |  

- **Key Insights**:  
  - **Feature Importance**: Temperature (18.3%), UV Index (16.6%), and Precipitation (15.1%) are most influential.  
  - **Confusion Matrix**: Low misclassification rates (e.g., 98% recall for Snowy and Cloudy types).  
  - **Learning Curve**: Model shows strong generalization with minimal overfitting.  


#### Next Steps  
1. Integrate **real-time weather APIs** (e.g., OpenWeatherMap) for dynamic predictions.  
2. Optimize for **edge devices** (e.g., IoT sensors) using model quantization or lightweight architectures.  
3. Explore **ensemble methods** (e.g., stacking) or deep learning (e.g., neural networks) for further accuracy gains.  
4. Expand to **hyper-local predictions** by incorporating fine-grained location data (e.g., ZIP codes).  


#### Conclusion  
The Random Forest model delivers robust, high-accuracy weather type predictions, making it suitable for industry applications. While highly effective, the model’s reliance on historical data limits its adaptability to unprecedented climate events. For production use, regular retraining with updated datasets and monitoring for concept drift are recommended.  


#### Bibliography  
- [1] L. Breiman, "Random forests," *Mach. Learn.*, vol. 45, no. 1, pp. 5-32, Oct. 2001.
- [2] R. Lagerquist, A. McGovern, and D. J. Gagne II, "Deep learning for spatially explicit prediction of synoptic-scale fronts," *Weather Forecast.*, vol. 32, no. 5, pp. 1817-1837, Oct. 2017.
- [3] World Meteorological Organization, *Guidelines on Machine Learning for Weather Prediction*, WMO-No. 1312, 2022.
- [4] H. Hersbach et al., "The ERA5 global reanalysis," *Q. J. R. Meteorol. Soc.*, vol. 146, no. 730, pp. 1999-2049, Jul. 2020.
- [5] Food and Agriculture Organization, *The Impact of Climate-Smart Agriculture on Food Security*, FAO, 2023.
- [6] International Energy Agency, *Renewable Energy Integration with Weather Forecasting*, IEA, 2023.
- [7] F. Pedregosa et al., "Scikit-learn: Machine learning in Python," *J. Mach. Learn. Res.*, vol. 12, pp. 2825-2830, 2011.
- [8] T. Chen and C. Guestrin, "XGBoost: A scalable tree boosting system," in *Proc. 22nd ACM SIGKDD Int. Conf. Knowl. Discov. Data Min.*, 2016, pp. 785-794.

#### Contact and Further Information  
For questions , please contact: Zhuzhengyang0203@hotmail.com  

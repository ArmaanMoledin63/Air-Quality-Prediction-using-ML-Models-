# Air Quality Index Analysis System

*Advanced analysis and prediction of air quality metrics across different states*

## Project Overview

This data science project analyzes air quality data across different states by processing multiple pollutant parameters (SO₂, NO₂, RSPM, SPM, PM2.5) and calculating the Air Quality Index (AQI). The system implements both regression and classification models to predict air quality categories.

## Implementation Details

### Data Processing
- Removed unnecessary columns: agency, stn_code, date, sampling_date, location_monitoring_station
- Handled missing values using mode imputation for categorical variables
- Implemented zero imputation for numerical missing values
- Performed comprehensive exploratory data analysis with visualizations

### Feature Engineering

#### Index Calculations
1. **SO₂ Index (SOi)**
   ```python
   def cal_SOi(so2):
       si = 0
       if(so2 <= 40):
           si = so2 * (50/40)
       elif(so2 > 40 and so2 <= 80):
           si = 50 + (so2-40) * (50/40)
       # ... additional thresholds
   ```

2. **NO₂ Index (NOi)**
   ```python
   def cal_NOi(no2):
       ni = 0
       if(no2 <= 40):
           ni = no2 * (50/40)
       elif(no2 > 40 and no2 <= 80):
           ni = 50 + (no2-40) * (50/40)
       # ... additional thresholds
   ```

3. **RSPM Index (Rpi)**
   ```python
   def cal_RSPMI(rspm):
       rpi = 0
       if(rpi <= 30):
           rpi = rpi * 50/30
       # ... additional thresholds
   ```

4. **SPM Index (SPMi)**
   ```python
   def cal_SPMi(spm):
       spi = 0
       if(spm <= 50):
           spi = spm * 50/50
       # ... additional thresholds
   ```

### AQI Calculation
```python
def cal_aqi(si, ni, rspmi, spmi):
    aqi = 0
    if(si > ni and rspmi and si > spmi):
        aqi = si   
    if(ni > si and ni > rspmi and ni > spmi):
        aqi = ni
    if(rspmi > si and rspmi > ni and rspmi > spmi):
        aqi = rspmi
    if(spmi > si and spmi > ni and spmi > rspmi):
        aqi = spmi
    return aqi
```

### Air Quality Categories
```
Category        AQI Range
Good            ≤ 50
Moderate        51-100
Poor            101-200
Unhealthy       201-300
Very Unhealthy  301-400
Hazardous       > 400
```

## Machine Learning Models

### Regression Models
1. **Linear Regression**
   - RMSE evaluation on training and testing data
   - R-squared value assessment

2. **Decision Tree Regressor**
   - Implemented with default parameters
   - Performance metrics calculation

3. **Random Forest Regressor**
   - Ensemble learning approach
   - Comparative analysis with other models

### Classification Models
1. **Logistic Regression**
   - Predicts AQI categories
   - Model accuracy evaluation

2. **Decision Tree Classifier**
   - Classification accuracy metrics
   - Kappa score calculation

3. **Random Forest Classifier**
   - Ensemble classification
   - Performance comparison

4. **K-Nearest Neighbors**
   - Implementation for category prediction
   - Accuracy and kappa score evaluation

## Visualizations Implemented
- State-wise pollution analysis
- Pollutant distribution histograms
- Bar plots for different pollutants by state
- Missing value analysis

## Dependencies
```python
pandas
numpy
seaborn
matplotlib
scikit-learn
```

## Key Features
- Comprehensive pollutant analysis
- Multiple model implementations
- Robust data preprocessing
- Detailed visualization components
- Both regression and classification approaches

---

*Developed for environmental quality assessment and prediction by Armaan Moledina*

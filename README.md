# Air Quality Analysis & Prediction System

*Empowering environmental insights through advanced analytics and machine learning*

## Project Overview

This sophisticated environmental analysis system processes and predicts Air Quality Index (AQI) using advanced machine learning algorithms. The system incorporates multiple pollutant metrics including SO₂, NO₂, RSPM, and SPM to generate comprehensive air quality assessments.

## Technical Architecture

### Data Processing Pipeline
```
Raw Data → Preprocessing → Feature Engineering → Model Training → Prediction
```

### Key Components
- **Pollutant Analysis Modules**
  - SO₂ Index Calculator
  - NO₂ Index Calculator
  - RSPM Index Calculator
  - SPM Index Calculator
  - Composite AQI Generator

### Machine Learning Models Implemented
1. **Regression Models**
   - Linear Regression
   - Decision Tree Regressor
   - Random Forest Regressor

2. **Classification Models**
   - Logistic Regression
   - Decision Tree Classifier
   - Random Forest Classifier
   - K-Nearest Neighbors

## Technical Features

### Data Preprocessing
- Null value handling
- Feature selection
- Data normalization
- Categorical encoding

### Advanced Analytics
- Time series analysis
- Geospatial visualization
- Statistical modeling
- Cross-validation techniques

## Performance Metrics

### Model Evaluation Criteria
- RMSE (Root Mean Square Error)
- R-squared values
- Accuracy scores
- Kappa coefficients

### Quality Categories
```
AQI Range    Category
≤ 50         Good
51-100       Moderate
101-200      Poor
201-300      Unhealthy
301-400      Very Unhealthy
> 400        Hazardous
```

## Setup & Dependencies

### Core Requirements
```python
pandas>=1.2.0
numpy>=1.19.0
scikit-learn>=0.24.0
seaborn>=0.11.0
matplotlib>=3.3.0
```

### Environmental Variables
```python
PYTHON_VERSION=3.8
RANDOM_STATE=70
TEST_SIZE=0.2
```

## Usage Guide

### Data Preparation
```python
# Load and preprocess data
df = pd.read_csv('data.csv', encoding='unicode_escape')
df = preprocess_data(df)

# Calculate indices
df['SOi'] = df['so2'].apply(cal_SOi)
df['NOi'] = df['no2'].apply(cal_NOi)
df['AQI'] = calculate_composite_aqi(df)
```

### Model Training
```python
# Split data
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=70
)

# Train model
model = RandomForestClassifier()
model.fit(X_train, y_train)
```

## Future Enhancements

- Real-time data processing pipeline
- Deep learning integration
- API development for external access
- Enhanced visualization capabilities
- Automated reporting system

## Authors

Created by Armaan Moledina

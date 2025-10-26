# sKeeperAI - Time Series Forecasting Project

A machine learning project for time series forecasting using ARIMA models to predict future order values for different raw materials.

## Overview

This project implements time series forecasting models for two different materials:

- **PET12**: Polyethylene Terephthalate forecasting
- **BOPP30**: Biaxially Oriented Polypropylene forecasting

The project uses ARIMA (AutoRegressive Integrated Moving Average) models to generate predictions for future time periods.

## Project Structure

```
sKeeperAI/
├── README.md                    # This file
├── requirements.txt             # Python dependencies
├── .gitignore                  # Git ignore rules
├── timeseries.ipynb           # Main time series analysis notebook
├── timeseriesv0.ipynb         # Version 0 of the analysis
├── using_modelPET12.ipynb     # PET12 model usage and predictions
├── using_modelBOPP30.ipynb    # BOPP30 model usage and predictions
├── model_PET12.pkl            # Trained PET12 ARIMA model
├── model_BOPP30.pkl           # Trained BOPP30 ARIMA model
├── PET12.png                  # PET12 visualization/plot
└── BOPP30.png                 # BOPP30 visualization/plot
```

## Features

- **ARIMA Model Training**: Automated ARIMA model selection and training using pmdarima
- **Time Series Forecasting**: Generate predictions for future time periods
- **Multiple Material Support**: Separate models for PET12 and BOPP30 materials
- **Visualization**: Plot generation for model results and forecasts
- **Model Persistence**: Save and load trained models using joblib

## Installation

1. Clone this repository:

```bash
git clone <your-repository-url>
cd sKeeperAI
```

2. Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Usage

### Running the Analysis Notebooks

1. **Main Analysis**: Open `timeseries.ipynb` to run the complete time series analysis
2. **PET12 Predictions**: Use `using_modelPET12.ipynb` to generate forecasts for PET12
3. **BOPP30 Predictions**: Use `using_modelBOPP30.ipynb` to generate forecasts for BOPP30

### Example Usage

```python
import pandas as pd
import joblib

# Load a trained model
model = joblib.load("model_PET12.pkl")

# Generate forecasts
forecast_periods = 5
forecasts = pd.DataFrame(model.forecast(steps=forecast_periods))
forecasts.columns = ['predictions']

print(forecasts)
```

## Dependencies

- **pandas**: Data manipulation and analysis
- **matplotlib**: Plotting and visualization
- **joblib**: Model serialization and persistence
- **pmdarima**: ARIMA model implementation
- **statsmodels**: Statistical modeling
- **numpy**: Numerical computing
- **scikit-learn**: Machine learning utilities

## Model Details

### PET12 Model

- Generates 5-month forecasts starting from April 2024
- Forecast periods: 2024-04-01 to 2024-08-01

### BOPP30 Model

- Generates 5-month forecasts starting from May 2024
- Forecast periods: 2024-05-01 to 2024-09-01

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).

## Contact

For questions or support, please open an issue in this repository.

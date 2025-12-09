# Sleep Health Predictor 🌙

An AI-powered clinical decision support system for sleep disorder detection and health monitoring, featuring smartwatch integration and advanced analytics.

## Live Demo

[View Live Dashboard](https://ai-sleep-disorder-detection.streamlit.app/)

## Project Overview

This application leverages machine learning to predict and analyze sleep disorders (Healthy, Insomnia, Sleep Apnea) using comprehensive patient health metrics. The system provides a professional analytical dashboard with real-time data visualization and personalized health insights.

![Main Dashboard](images/Screenshot%202025-12-09%20at%207.11.17%E2%80%AFPM.png)
*Figure 1: Main Dashboard Overview*

## Key Features

### Machine Learning Analysis
- **Random Forest Classifier** with 88% prediction accuracy
- **Multi-dimensional Health Metrics** analysis (12+ parameters)
- **Predictive Analytics** for sleep disorder risk assessment
- **Comprehensive Sleep Score** algorithm (0-100 scale)

![Health Metrics Analysis](images/Screenshot%202025-12-09%20at%207.11.36%E2%80%AFPM.png)
*Figure 2: Detailed Health Metrics and Analysis*

### Device Integration
- Smartwatch and wearable device compatibility
- Support for multiple device manufacturers
- Automated health metric synchronization
- Real-time data processing pipeline

![Device Integration](images/Screenshot%202025-12-09%20at%207.11.56%E2%80%AFPM.png)
*Figure 3: Device Connection and Data Synchronization*

### Data Visualization
- **Radar Chart Analysis**: Visual comparison against healthy baselines
- **Risk Assessment Gauges**: Quantitative health metrics visualization
- **Model Interpretability**: Feature importance analysis
- **Temporal Trend Analysis**: Longitudinal health tracking

### Clinical Decision Support
- **Interactive Simulation**: Test health outcome scenarios
- **Personalized Recommendations**: Data-driven health insights
- **Clinical Reporting**: Exportable analysis reports
- **Patient History**: Comprehensive session tracking

## Getting Started

### Prerequisites
- Python 3.8 or higher
- pip package manager
- Git (for version control)

### Installation

1. Clone the repository:
```bash
git clone <your-repo-url>
cd Samsung_Capstone_Sleep_Project
```

2. Create and activate a virtual environment (recommended):
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install required dependencies:
```bash
pip install -r requirements.txt
```

4. Train the initial model (first-time setup):
```bash
python3 src/train_model.py
```

5. Launch the application:
```bash
streamlit run dashboard/main.py
```

The application will be available in your browser at `http://localhost:8501`

## Project Structure

```
Samsung_Capstone_Sleep_Project/
├── dashboard/              # Main application components
│   ├── main.py            # Streamlit dashboard implementation
│   ├── styles.py          # Application styling
│   └── utils.py           # Utility functions
├── src/                   # Core source code
│   ├── train_model.py     # Machine learning model training
│   └── preprocessing.py   # Data preprocessing pipeline
├── models/                # Serialized models and encoders
│   ├── sleep_model_fast.pkl
│   ├── label_encoder.pkl
│   └── occupation_encoder.pkl
├── data/                  # Data storage
│   └── raw/
│       └── Sleep_health_and_lifestyle_dataset.csv
├── images/                # Documentation assets
│   └── dashboard_screenshot.png
├── .streamlit/            # Streamlit configuration
│   └── config.toml
├── requirements.txt       # Python dependencies
└── README.md
```

## 🎮 Usage Guide

### 1. Connect Smartwatch (Optional)
- Select your device from the dropdown
- Click "Connect to Smartwatch"
- Click "Sync Data" to auto-fill health metrics

### 2. Enter Patient Data
- **Demographics**: Gender, Age, Occupation, BMI
- **Sleep & Activity**: Duration, Quality, Activity, Steps
- **Vitals**: Stress, Heart Rate, Blood Pressure

### 3. Run Analysis
- Click "Run Analysis" button
- View diagnosis and risk assessment
- Review personalized recommendations
- Download clinical report

### 4. Explore Features
- **What-If Simulator**: Test lifestyle changes
- **Feature Importance**: See which factors matter most
- **Historical Tracking**: Monitor progress over time

## 🧠 Model Details

### Algorithm
- **Type**: Random Forest Classifier
- **Features**: 12 health metrics

| Class | Precision | Recall | F1-Score |
|--------------|-----------|--------|----------|
| Healthy | 0.95 | 0.98 | 0.97 |
| Insomnia | 0.72 | 0.81 | 0.76 |
| Sleep Apnea | 0.85 | 0.69 | 0.76 |

### Confusion Matrix

| | Predicted Healthy | Predicted Insomnia | Predicted Sleep Apnea |
|-----------------|-------------------|-------------------|----------------------|
| **Actual Healthy** | 98 | 1 | 1 |
| **Actual Insomnia** | 3 | 17 | 1 |
| **Actual Sleep Apnea** | 2 | 2 | 15 |

## Development

### Data Preprocessing
```python
# Example: Handling missing values
df['Sleep_Disorder'] = df['Sleep_Disorder'].fillna('Healthy')
```

### Model Training
```python
from sklearn.ensemble import RandomForestClassifier

# Initialize and train the model
model = RandomForestClassifier(n_estimators=100, random_state=42)
model.fit(X_train, y_train)
```

### Extending Functionality
1. Implement new features in the appropriate module
2. Update the model training pipeline if needed
3. Run test suite: `pytest tests/`

## Contributing

Contributions are welcome. Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Open a pull request

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Dataset: [Sleep Health & Lifestyle Dataset](https://www.kaggle.com/datasets/uom190346a/sleep-health-and-lifestyle-dataset)
- Built with Streamlit and scikit-learn
- Special thanks to the open-source community

## Contact

For inquiries or support, please contact [chandrilmallick1@gmail.com](mailto:chandrilmallick1@gmail.com)

## Deployment

This application is deployed on Streamlit Cloud and accessible at:
**[https://ai-sleep-disorder-detection.streamlit.app/](https://ai-sleep-disorder-detection.streamlit.app/)**

### Deploy Your Own Instance

1. Fork this repository
2. Sign up for [Streamlit Cloud](https://streamlit.io/cloud)
3. Connect your GitHub account
4. Deploy using:
   - **Repository**: Your forked repo
   - **Branch**: `main`
   - **Main file**: `dashboard/main.py`

## Contact

For questions or feedback, please reach out to [chandrilmallick1@gmail.com]

---

**Built with ❤️ for Samsung Capstone Project**

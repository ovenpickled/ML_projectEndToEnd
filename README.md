# Student Performance Prediction System

A machine learning project that predicts student math scores based on various demographic and academic factors. The system uses multiple regression models to provide accurate predictions of student performance.

## 📋 Table of Contents
- [Features](#-features)
- [Technologies Used](#️-technologies-used)
- [Installation](#-installation)
- [Usage](#-usage)
- [Project Structure](#️-project-structure)
- [Training Pipeline](#-training-pipeline)
- [Model Evaluation](#-model-evaluation)
- [API Reference](#-api-reference)
- [Configuration](#-configuration)
- [Monitoring and Logging](#-monitoring-and-logging)
- [Testing](#-testing)
- [Deployment](#-deployment)
- [Performance](#-performance)
- [Troubleshooting](#-troubleshooting)
- [Future Improvements](#-future-improvements)
- [License](#-license)
- [Author](#-author)
- [Contributing](#-contributing)
- [Acknowledgments](#-acknowledgments)

## 🎯 Features

- Predicts math scores based on:
  - Gender
  - Race/Ethnicity
  - Parental Education Level
  - Lunch Type
  - Test Preparation Course
  - Reading Scores
  - Writing Scores
- Implements multiple ML models including Random Forest, XGBoost, and CatBoost
- Web interface for easy predictions
- Comprehensive data preprocessing pipeline
- Model evaluation and selection system

## 🛠️ Technologies Used

- Python 3.10
- Flask
- Scikit-learn
- Pandas
- NumPy
- XGBoost
- CatBoost
- HTML/CSS

## 📦 Installation

1. Clone the repository
```bash
git clone https://github.com/ovenpickled/ML_projectEndToEnd.git
```

2. Create and activate a conda environment
```bash
conda create -p venv python==3.10 -y
conda activate venv/
```

3. Install required packages
```bash
pip install -r requirements.txt
```

## 🚀 Usage

1. Start the Flask server:
```bash
python app.py
```

2. Open your web browser and navigate to your local host (default: http://localhost:5000)

3. Fill in the student information in the web form:
   - Select gender
   - Choose race/ethnicity group
   - Input parental education level
   - Select lunch type
   - Indicate test preparation course completion
   - Enter reading and writing scores

4. Click "Predict your Maths Score" to get the prediction

## 🗂️ Project Structure

```
├── artifacts/           # Stored models and data files
├── src/
│   ├── components/     # Core implementation modules
│   ├── pipeline/      # Training and prediction pipelines
│   ├── utils.py       # Utility functions
│   ├── logger.py      # Logging configuration
│   └── exception.py   # Custom exception handling
├── templates/          # HTML templates
├── app.py             # Flask application
└── requirements.txt    # Project dependencies
```

## 🔄 Training Pipeline

The project implements a comprehensive training pipeline:

1. **Data Ingestion**: Loads and splits the dataset into training and testing sets
2. **Data Transformation**: 
   - Handles missing values
   - Performs numerical scaling
   - Applies one-hot encoding for categorical variables
3. **Model Training**:
   - Trains multiple regression models
   - Performs hyperparameter tuning
   - Selects the best performing model

## 📊 Model Evaluation

The system evaluates multiple regression models:
- Random Forest Regressor
- Decision Tree Regressor
- Gradient Boosting Regressor
- Linear Regression
- XGBoost Regressor
- CatBoost Regressor
- AdaBoost Regressor

Models are evaluated using R-squared score, with the best performing model being automatically selected for predictions.

## 📡 API Reference

### Prediction Endpoint
```http
POST /predictdata
```
| Parameter | Type | Description |
|-----------|------|-------------|
| gender | string | Student's gender (male/female) |
| ethnicity | string | Race/ethnicity group (A-E) |
| parental_level_of_education | string | Parent's education level |
| lunch | string | Lunch type (standard/free/reduced) |
| test_preparation_course | string | Test prep completion status |
| reading_score | integer | Reading test score (0-100) |
| writing_score | integer | Writing test score (0-100) |

## ⚙️ Configuration

The project uses the following configuration files:
- `setup.py`: Package configuration and dependencies
- `requirements.txt`: Python package requirements
- Model hyperparameters are configured in `src/components/model_trainer.py`

## 📝 Monitoring and Logging

- Custom logger implementation in `src/logger.py`
- Logs stored in `logs/` directory
- Training metrics tracked in `catboost_info/`
- Custom exception handling in `src/exception.py`

## 🧪 Testing

To run tests:
```bash
# Unit tests
python -m pytest tests/

# Model validation
python src/components/model_trainer.py
```

## 🌐 Deployment

### Local Deployment
```bash
python app.py
```

### Production Deployment Guidelines
1. Use production WSGI server (e.g., Gunicorn)
2. Set `debug=False` in Flask application
3. Implement proper security measures
4. Configure environment variables

## 📈 Performance

- Model achieves R² score > 0.80 on test data
- Average prediction time: < 100ms
- Handles concurrent requests efficiently
- Regular model retraining recommended for optimal performance

## ❗ Troubleshooting

Common issues and solutions:

1. **Installation Issues**
   - Ensure Python 3.10 is installed
   - Check conda environment activation
   - Verify all dependencies are installed

2. **Prediction Errors**
   - Validate input data format
   - Check log files for detailed error messages
   - Ensure model files exist in artifacts/

## 🔄 Future Improvements

Planned enhancements:
1. Add more feature engineering techniques
2. Implement deep learning models
3. Add API authentication
4. Create Docker container
5. Add batch prediction capability
6. Implement model versioning
7. Add real-time monitoring dashboard

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Aryan Ghate**
- Email: aryanghate29@gmail.com
- GitHub: [@ovenpickled](https://github.com/ovenpickled)

## 🤝 Contributing

Contributions, issues, and feature requests are welcome. Feel free to check issues page if you want to contribute.

### Contributing Guidelines
1. Fork the repository
2. Create a new branch
3. Make your changes
4. Submit a pull request

## 🙏 Acknowledgments

- Dataset provided by Kaggle
- Inspired by various ML projects
- Thanks to all contributors

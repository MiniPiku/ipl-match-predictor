# IPL Win Probability Predictor 🏏

A machine learning project that predicts the win probability of IPL (Indian Premier League) cricket matches in real-time during the second innings. This application uses historical match data to provide dynamic probability predictions based on the current state of the match.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Installation](#installation)
- [Usage](#usage)
- [Dataset](#dataset)
- [Model Architecture](#model-architecture)
- [Data Preprocessing](#data-preprocessing)
- [Visualization](#visualization)
- [Future Improvements](#future-improvements)

## 🎯 Overview

This project analyzes IPL match data to predict the probability of a batting team winning during the second innings chase. The model takes into account various factors including:
- Current run rate and required run rate
- Wickets in hand
- Runs and balls remaining
- Team strengths
- Venue conditions

## ✨ Features

- **Real-time Prediction**: Calculate win probability based on current match state
- **Interactive Web Interface**: User-friendly Streamlit application
- **Visual Analytics**: Match progression visualization
- **Team & Venue Support**: All 8 major IPL teams and multiple venues
- **ML Model**: Logistic Regression based prediction system

## 🛠️ Technology Stack

- **Python** - Core programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Scikit-learn** - Machine learning library
- **Streamlit** - Web application framework
- **Matplotlib** - Data visualization
- **Pickle** - Model serialization

## 📦 Installation

### Prerequisites

- Python 3.7 or higher
- pip package manager

### Setup Steps

1. Clone the repository:
```bash
git clone <repository-url>
cd ipl-win-probability-predictor
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

3. Ensure you have the dataset files (`matches.csv` and `deliveries.csv`) in the parent directory

4. Train the model (optional if `pipe.pkl` already exists):
   - Open `Untitled.ipynb` in Jupyter Notebook
   - Run all cells to generate the `pipe.pkl` model file

5. Run the Streamlit application:
```bash
streamlit run app.py
```

The application will open in your default web browser at `http://localhost:8501`

## 🎮 Usage

### Web Interface

1. Select the batting team (team chasing)
2. Select the bowling team (team defending)
3. Choose the host city
4. Enter the target runs
5. Input current score, overs completed, and wickets fallen
6. Click "Predict Probability" to get win/loss percentages

### Notebook Analysis

The Jupyter notebook (`Untitled.ipynb`) provides:
- Data exploration and preprocessing
- Model training and evaluation
- Match progression analysis
- Visualization of win probability over time

## 📊 Dataset

The project uses IPL match data from Kaggle containing:
- **matches.csv**: Match-level information including teams, venues, winners
- **deliveries.csv**: Ball-by-ball delivery data for each match

### Data Cleaning Steps

- Standardized team names (e.g., Delhi Daredevils → Delhi Capitals)
- Filtered out Duckworth-Lewis (D/L) affected matches
- Focused on 8 major IPL teams
- Calculated derived features:
  - Current run rate (CRR)
  - Required run rate (RRR)
  - Runs and balls remaining
  - Wickets in hand

## 🤖 Model Architecture

- **Algorithm**: Logistic Regression
- **Preprocessing**: One-Hot Encoding for categorical variables (teams, city)
- **Pipeline**: Scikit-learn Pipeline with ColumnTransformer
- **Features**:
  - Batting team
  - Bowling team
  - City
  - Runs left
  - Balls left
  - Wickets remaining
  - Target
  - Current run rate
  - Required run rate

### Model Performance

The model predicts win probability based on historical IPL data patterns and achieves reasonable accuracy for real-time predictions.

## 📈 Data Preprocessing

Key preprocessing steps include:
1. Merging match and delivery data
2. Filtering second innings data
3. Standardizing team names
4. Calculating match state features
5. Handling missing values
6. Removing invalid records (e.g., balls_left = 0)

## 📉 Visualization

The notebook includes visualization capabilities to track:
- Win probability progression over innings
- Wickets fallen per over
- Runs scored per over
- Match state evolution

## 🚀 Future Improvements

- [ ] Incorporate player performance data
- [ ] Add weather conditions as a feature
- [ ] Implement ensemble methods (Random Forest, XGBoost)
- [ ] Include historical head-to-head statistics
- [ ] Add time-series features
- [ ] Deploy to cloud platform
- [ ] Create mobile application
- [ ] Real-time data integration

## 📝 License

This project is for educational purposes.

## 👤 Author

Developed as part of an innovative machine learning project.

## 🙏 Acknowledgments

- IPL data source: Kaggle
- Scikit-learn documentation
- Streamlit community

---

**Note**: This is a predictive model based on historical data and should be used for entertainment and educational purposes only.

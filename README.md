# 🏁 F1 Race Winner Prediction using XGBoost

## Overview

This project uses Machine Learning to predict the probability of each Formula 1 driver winning a race.

The model is trained on historical driver performance, team performance, track history, reliability, practice sessions, and qualifying data. It generates win probabilities for selected drivers and ranks them from most likely to least likely winner.

Built using manually curated Formula 1 data, Microsoft Excel, Python, and XGBoost.

Current goal:

- Predict race winner
- Generate driver win probabilities
- Rank drivers before a race weekend

Future goal:

- Predict full race finishing positions
- Predict podium probabilities
- Build a larger multi-season prediction system

---

## Project Motivation

Formula 1 results are influenced by many factors:

- Driver form
- Team performance
- Qualifying pace
- Reliability
- Track characteristics
- Race strategy

This project attempts to combine these factors into a single machine learning model that estimates each driver's chance of winning a race.

---

## Dataset

Each row in the dataset represents a driver before a specific race.

### Target Variable

```text
race_winner

1 = Winner
0 = Not Winner
```

---

## Features Used

### Driver Performance

- Season average finish position
- Season average qualifying position
- Last 3 races average finish position
- Last 3 races average qualifying position
- Championship points
- Championship position

### Team Performance

- Team championship position
- Team points
- Team average finish position
- Team average qualifying position

### Track History

- Average finish position at the track
- Average qualifying position at the track
- Number of wins at the track
- Number of podiums at the track

### Reliability

- Driver mechanical DNFs this season
- Team mechanical DNFs this season
- Engine manufacturer mechanical DNFs this season

### Weekend Performance

- FP1 gap to fastest
- FP2 gap to fastest
- FP3 gap to fastest
- Sprint qualifying gap
- Sprint finish position
- Qualifying gap to pole

### Additional Context

- Round number
- Race or sprint weekend
- Driver
- Team
- Engine supplier

---

## Data Collection

The dataset was manually collected, cleaned, validated, and prepared using Microsoft Excel.

Excel was used for:

- Data collection
- Data cleaning
- Data validation
- Feature engineering
- Dataset preparation
- CSV generation

The processed CSV files were then imported into Python for machine learning training and prediction.

---

## Machine Learning Model

The project uses:

### XGBoost Classifier

Reasons for choosing XGBoost:

- Excellent performance on tabular datasets
- Handles non-linear relationships well
- Strong results with relatively small datasets
- Captures interactions between features
- Generally outperforms Logistic Regression and Random Forest on structured racing data

---

## Example Prediction Output

```text
🏁 Barcelona-Catalunya GP Winner Prediction

P1 | George Russell    | Mercedes        | 41.94%
P2 | Lewis Hamilton    | Ferrari         | 20.46%
P3 | Kimi Antonelli    | Mercedes        |  9.71%
P4 | Max Verstappen    | Red Bull Racing |  1.13%
```

The driver with the highest probability is considered the predicted winner.

It should not be considered 100% correct. Formula 1 can be unpredictable, and a genius strategy call, a safety car, a weather change, or a reliability issue can completely change the outcome. The model also does not currently account for race pace during practice sessions.

---

## Current Limitations

This model does not currently account for:

- Safety Cars
- Virtual Safety Cars
- Dynamic weather changes
- Pit stop execution
- Tire degradation modelling
- Team strategy decisions
- Driver mistakes
- Race incidents

These factors can significantly affect real race outcomes.

---

## Future Improvements

Planned improvements include:

- Multi-season training dataset
- Finishing position prediction
- Podium probability prediction
- Feature importance analysis
- Hyperparameter optimization
- Automated data collection pipeline
- Reliability trend modelling
- Track-specific characteristics
- Driver performance trend analysis

---

## Tech Stack

### Data Collection

- Microsoft Excel

### Machine Learning

- Python
- Pandas
- NumPy
- Scikit-Learn
- XGBoost

### Development

- Anaconda
- Jupyter Notebook
---



## Results

The model outputs win probabilities rather than absolute predictions.

Example:

```text
Russell         41.94%
Hamilton        20.46%
Leclerc         9.71%
Verstappen      1.13%
```

This reflects how likely each driver appears to win based on available pre-race data.

---

## Disclaimer

Formula 1 races are highly dynamic events.

A driver with a 40% predicted chance of winning can still lose, while a driver with a 10% chance can still win due to strategy, weather, reliability, or race incidents.

This project predicts probabilities, not certainties.

---

## Author

Built as a personal machine learning project combining Formula 1 analytics, manual data engineering, and XGBoost-based race prediction.

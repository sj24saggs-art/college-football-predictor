# College Football Bowl Game Predictor 🏈

This project is a machine learning endeavor to predict the outcomes of NCAA college football bowl games. It explores two distinct modeling methodologies that both use season-average statistics to compare team performance.

The primary goal is to compare these methods and determine the most effective features for predicting winners in high-stakes matchups.

## 🔬 Methodologies Explored

This project evaluates and compares two distinct feature engineering approaches to predict game outcomes.

### 1\. Score Regression & SVM

This model finds the most effective features for predicting college football bowl game outcomes based on regular-season performance.

  * **Feature Engineering:** The model calculates the average regular-season performance statistics for every team in each season.
  * **Predictive Features:** The model uses the difference between the two opponents' season-long average statistics for a given bowl game.
  * **SVM Usage:** The model uses Support Vector Regression (SVR) to predict scores and Support Vector Classification (SVC) to predict the winner.
  * **Target:** The model predicts both the winner (using classification) and the final score (using regression).

### 2\. Differential Regression Model

This is the primary and most successful approach because it uses the full seasonal stats for both teams to predict the score difference, leading to a more accurate prediction.

  * **Feature Engineering:** The average performance statistics (e.g., avg points for, avg passing yards) are calculated for every team in every season, using all game types.
  * **Predictive Features:** For a given game, the model is provided with the full seasonal stats for both the home and away teams.
  * **Cross-Validation:** A robust season-by-season cross-validation is used, where each season's bowl games serve as the test set, with the model being trained on all other seasons.
  * * **Target:** `score_difference` (predicted using Linear Regression).

## 🛠️ Tech Stack

  * **Python**
  * **Pandas** for data manipulation
  * **NumPy** for numerical operations
  * **Scikit-learn** for machine learning models and metrics
  * **Matplotlib** for data visualization

## 🚀 Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

Make sure you have Python (3.8+) installed. You will also need to install the required libraries.

```sh
pip install pandas numpy scikit-learn matplotlib
```

### Installation

1.  Clone the repo
    ```sh
    git clone https://github.com/sj24saggs-art/college-football-predictor.git
    ```
2.  Navigate into the project directory
    ```sh
    cd college-football-predictor
    ```

## 📁 Project Structure

```
├── data/
│   └── cfb_box-scores_2002-2024.csv
├── notebooks/
│   ├── data_exploration.ipynb
│   ├── differential_model.ipynb
│   └── model_training.ipynb
├── .gitignore
└── README.md
```

## 📚 Data Source

The dataset used is the "College Football (NCAAF) Box Scores 2002-2024" dataset, publicly available on Kaggle.

  * **Source:** [Kaggle Dataset](https://www.kaggle.com/datasets/cviaxmiwnptr/college-football-team-stats-2002-to-january-2024)

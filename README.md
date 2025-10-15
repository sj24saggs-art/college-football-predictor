# College Football Bowl Game Predictor 🏈

This project is a machine learning endeavor to predict the outcomes of NCAA college football bowl games. It explores two distinct modeling methodologies: a direct, game-level differential model and a more complex replication of the approach from the Stanford CS229 report, ["Predicting the Outcome of College Bowl Games"](https://www.google.com/search?q=https://cs229.stanford.edu/proj2015/101_report.pdf).

The primary goal is to compare these methods and determine the most effective features for predicting winners in high-stakes matchups.

## 🔬 Methodologies Explored

This project evaluates and compares two distinct feature engineering approaches to predict game outcomes.

### 1\. Direct Differential Model

This is a baseline approach that creates features by directly calculating the difference in statistics between the home and away teams for each individual game. The model is trained on these direct, single-game differentials to establish a baseline prediction accuracy.

  * **Features:** `rank_difference`, `pass_yards_diff`, `rush_yards_diff`, etc.
  * **Target:** `score_difference`

### 2\. Season-Average Differential Model 

This is the primary, more advanced methodology. It assumes that a team's performance over an entire regular season is a better predictor of a bowl game outcome.

  * **Feature Engineering:** The average regular-season performance statistics (e.g., average points for, average passing yards) are calculated for every team in every season.
  * **Predictive Features:** For a given bowl game, the model's features are the *difference between the two opponents' season averages*.
  * **Cross-Validation:** A robust season-by-season cross-validation is used, where each season's bowl games serve as the test set, with the model being trained on all other seasons.

## 📊 Results

The project evaluates four distinct models based on the **Season-Average** methodology. The final model, a **Logistic Regression with feature selection**, proved to be the most effective at predicting game winners.

#### Winner Selection Accuracy by Season (Logistic Regression Model)

This chart displays the final model's accuracy for each individual season's bowl games.

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

## 📈 Usage

The entire analysis pipeline for the main methodology is contained within the Jupyter Notebook.

1.  Place the dataset `cfb_box-scores_2002-2024.csv` inside the `/data` directory.
2.  Open and run the `notebooks/model_training.ipynb` notebook.

The notebook cells are organized sequentially to perform data loading, cleaning, feature engineering, and the training and evaluation of all models.

## 📁 Project Structure

```
├── data/
│   └── cfb_box-scores_2002-2024.csv
├── notebooks/
│   └── model_training.ipynb
├── .gitignore
└── README.md
```

## 📚 Data Source

The dataset used is the "College Football (NCAAF) Box Scores 2002-2024" dataset, publicly available on Kaggle.

  * **Source:** [Kaggle Dataset](https://www.kaggle.com/datasets/cviaxmiwnptr/college-football-team-stats-2002-to-january-2024)

## 🙏 Acknowledgements

  * Credit to the original authors of the Stanford CS229 paper for the foundational methodology.

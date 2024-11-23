# IPL First Innings Score Prediction

## Overview
This repository provides a machine learning model to predict the **first innings score** of IPL matches based on several match parameters. The project uses historical IPL data for training and incorporates multiple regression techniques to optimize prediction accuracy.

---

## Features
- Data cleaning and preprocessing tailored for IPL datasets.
- Implementation of regression models:
  - **Linear Regression**
  - **Decision Tree Regression**
  - **Random Forest Regression**
  - **Adaptive Boosting (AdaBoost)**
- Evaluation and comparison of models using error metrics like MAE, MSE, and RMSE.
- A **custom function** to predict scores dynamically based on match details.
- Sample predictions using historical matches for verification.

---

## Dataset
The project uses an IPL dataset containing match details such as:
- Teams
- Overs
- Runs
- Wickets
- Performance in the last 5 overs

### Data Cleaning Steps:
1. Removed irrelevant columns like `mid`, `venue`, `batsman`, etc.
2. Filtered out inconsistent teams to maintain data reliability.
3. Focused on data from overs ≥ 5 for accurate predictions.
4. Converted date strings into Python `datetime` objects for effective data handling.

---

## Model Development

### Algorithms Implemented:
1. **Linear Regression**  
   Best-performing model for this dataset based on evaluation metrics.
2. **Decision Tree Regression**  
   Performed well but overfitted the training data.
3. **Random Forest Regression**  
   Improved accuracy over Decision Tree but didn't outperform Linear Regression.
4. **AdaBoost Regression**  
   Attempted to enhance Linear Regression but showed minimal improvement.

### Final Model:
- The **Linear Regression model** was selected for its simplicity and effectiveness.

---

## Installation and Usage

### Prerequisites:
- Python 3.x
- Required libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `sklearn`

### Installation:
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/ipl-score-prediction.git
   cd ipl-score-prediction
   ```
2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

### Usage:
1. Add the IPL dataset as `IPL Data Set.csv` in the project directory.
2. Run the Jupyter Notebook or Python script to train and evaluate models.
3. Use the `predict_score()` function for predictions:
   ```python
   predicted_score = predict_score(
       batting_team='Chennai Super Kings',
       bowling_team='Mumbai Indians',
       overs=10.2,
       runs=68,
       wickets=3,
       runs_in_prev_5=29,
       wickets_in_prev_5=1
   )
   print(f"Predicted Score Range: {predicted_score - 10} to {predicted_score + 5}")
   ```

---

## Predictions
The model is trained on IPL data from **2008 to 2016** and tested on matches from **2017 to 2019**. Below are sample predictions:

| Date         | Match                                   | Actual Score | Predicted Range      |
|--------------|-----------------------------------------|--------------|-----------------------|
| 14-Apr-2019  | Delhi Daredevils vs. Sunrisers Hyderabad | 155/7        | 145 to 160           |
| 10-May-2019  | Delhi Daredevils vs. Chennai Super Kings | 147/9        | 137 to 152           |
| 11-Apr-2019  | Rajasthan Royals vs. Chennai Super Kings | 151/7        | 141 to 156           |

---

## Limitations
- Score prediction is inherently challenging due to the dynamic nature of cricket.
- The model's performance is affected by features not captured in the dataset, such as player form, pitch conditions, and weather.

---

## Contributing
Contributions are welcome! Feel free to open issues or submit pull requests to improve the codebase.

---

## License
This project is licensed under the [MIT License](LICENSE).

---

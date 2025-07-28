# 🏋️‍♂️ Campus Gym Crowdedness Predictor - Kaggle ML

A machine learning project to forecast gym crowdedness based on historical data. This model helps students and staff find the best time to visit the gym with minimal wait.

> 📅 Data sampled every 10 minutes for a year  
> 🧠 Models used: **Linear Regression**, **Neural Network**, **Random Forest**  
> 📊 Goal: Predict how crowded the gym will be at a given timestamp

---

## 📦 Dataset

- **Source**: [Kaggle – Crowdedness at the Campus Gym](https://www.kaggle.com/datasets/nsrose7224/crowdedness-at-the-campus-gym)
- **Frequency**: Every 10 minutes
- **Duration**: 1 year
- **Key columns**:
  - `timestamp`: Date and time of the measurement
  - `count`: Number of people in the gym at that time

---

## 📁 Project Structure

```bash
campus-gym-crowdedness/
├── data/
│   ├── raw/                   # Original Kaggle CSV
│   └── processed/             # Cleaned and feature-engineered data
├── notebooks/
│   ├── eda.ipynb              # Exploratory data analysis
│   ├── linear_regression.ipynb
│   ├── polynomial_regression.ipynb
│   └── random_forest.ipynb
├── src/
│   ├── data_preparation.py    # Load, clean, feature engineer
│   ├── train_model.py         # Train and save models
│   ├── predict.py             # Make predictions
│   └── evaluate.py            # Plot and compare metrics
├── models/                    # Serialized trained models (e.g., .pkl files)
├── requirements.txt
├── README.md
└── LICENSE
🧹 Preprocessing & Feature Engineering
Parse timestamps and sort chronologically

Handle missing values (if any)

Extract features:

hour, day_of_week, is_weekend, etc.

Generate polynomial features for MPR

Create train-test split (e.g., last month for testing)

🤖 Models Used
1. Linear Regression
Simple, fast baseline

Works decently for daily trends

2. 
Captures nonlinear fluctuations

3. Random Forest
Tree-based model for nonlinear and complex patterns

Outperformed other models in test metrics

📊 Evaluation Metrics
RMSE	Root Mean Squared Error
R² Score	Proportion of variance explained
Residuals and mean log residuals

You can find evaluation results in notebooks/evaluate.ipynb or by running:

bash
Copy
Edit
python src/evaluate.py
🛠️ How to Run
1. Clone the repository
bash
Copy
Edit
git clone https://github.com/yourusername/campus-gym-crowdedness.git
cd campus-gym-crowdedness
2. Install dependencies
bash
Copy
Edit
pip install -r requirements.txt
3. Download the dataset
Download the Kaggle dataset and place the CSV file in data/raw/.

4. Preprocess the data
bash
Copy
Edit
python src/data_preparation.py
5. Train a model
bash
Copy
Edit
python src/train_model.py --model random_forest
Options: linear, polynomial, random_forest

6. Predict crowdedness
bash
Copy
Edit
python src/predict.py --datetime "2025-07-28 15:00"
📈 Visualizations
Line plots of actual vs predicted counts

Error distributions

Heatmaps by time-of-day and weekday

All visualizations are in the notebooks/ folder.

🔮 Example Use Case
"Is 6 PM on Monday too crowded?"
Run a prediction to find out and plan your workout more efficiently.

🙌 Acknowledgments
Dataset from @nsrose7224

Inspired by real-time campus gym usage tracking projects


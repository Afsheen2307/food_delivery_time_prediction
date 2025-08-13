# food_delivery_time_prediction

Food Delivery Time Prediction
Predicting delivery time is crucial for customer satisfaction and operational efficiency in food delivery platforms.
This project uses Python and Machine Learning to estimate the time required for an order to be delivered based on historical delivery data.

Features

Calculate distance between restaurant and delivery location using the Haversine formula.

Analyze effects of delivery partner age, ratings, vehicle type, and order type on delivery time.

Train and evaluate multiple ML regression models.

Generate predictions for new orders.

 Dataset
The dataset contains:

| Column                                                       | Description                            |
| ------------------------------------------------------------ | -------------------------------------- |
| `Delivery_person_Age`                                        | Age of the delivery partner            |
| `Delivery_person_Ratings`                                    | Average customer rating of the partner |
| `Restaurant_latitude` / `Restaurant_longitude`               | Coordinates of the restaurant          |
| `Delivery_location_latitude` / `Delivery_location_longitude` | Coordinates of the delivery location   |
| `Type_of_order`                                              | Order category (e.g., Snacks, Drinks)  |
| `Type_of_vehicle`                                            | Vehicle used for delivery              |
| `Time_taken (min)`                                           | Actual delivery time in minutes        |


 Installation

 # Clone the repository
git clone https://github.com/your-username/food-delivery-time-prediction.git
cd food-delivery-time-prediction

# Create a virtual environment (optional)
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt


 Usage
 Train the Model
 python src/train_model.py --data data/deliverytime.csv --save_model models/model.pkl

Predict Delivery Time
from src.train_model import load_model
import pandas as pd

model = load_model("models/model.pkl")
new_order = pd.DataFrame({
    'Delivery_person_Age': [29],
    'Delivery_person_Ratings': [4.5],
    'distance': [5.2]
})
print(f"Predicted Time: {model.predict(new_order)[0]:.2f} minutes")


Project Workflow
1.Data Loading & Cleaning
2.Feature Engineering (distance calculation, time-based features)
3.Exploratory Data Analysis (EDA)
4Model Training (Linear Regression, Decision Tree, Random Forest, etc.)
5.Evaluation (MSE, RMSE, R²)
6.Prediction on New Data



📈 Results
1.Positive correlation between distance and delivery time.
2.Younger delivery partners generally deliver faster.
3.Higher-rated partners tend to be more efficient.

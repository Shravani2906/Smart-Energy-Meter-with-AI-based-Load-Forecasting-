# Smart Energy Meter with AI-based Load Forecasting

## Problem Statement
With the increasing complexity of energy consumption patterns in urban areas, predicting daily energy usage accurately is crucial for optimizing grid operations, reducing costs, and promoting energy efficiency. Traditional energy monitoring systems can measure consumption but lack predictive capabilities. There is a need for a system that not only monitors electricity usage but also forecasts future load to assist utilities and consumers in planning and reducing energy wastage.

## Proposed Solution
Develop a Smart Energy Meter system integrated with AI-based load forecasting. The system will:
1. Collect daily energy consumption data from smart meters.
2. Use historical consumption data to predict future energy usage patterns.
3. Provide insights for energy planning, peak load management, and demand response strategies.

By employing a deep learning model, the solution predicts daily mean energy consumption using temporal features like year, month, and day of the week.

## Project Description
The Smart Energy Meter with AI-based Load Forecasting monitors electricity usage and predicts daily energy consumption using historical smart meter data. A deep learning model takes temporal features (Year, Month, Day of Week) to forecast mean daily energy usage. This helps in efficient energy management, peak load planning, and reducing wastage. Predictions are evaluated using Mean Squared Error (MSE) and visualized through loss curves and actual vs predicted plots.

## Approach
1. **Data Collection:**
   - Use the London Smart Meter dataset from Kaggle containing daily electricity consumption readings.
2. **Data Preprocessing:**
   - Load and sample the dataset for faster processing.
   - Handle missing values in energy readings by filling them with the mean.
   - Extract temporal features such as Year, Month, and Day of Week.
3. **Feature Scaling:**
   - Normalize input features using MinMaxScaler to improve neural network training efficiency.
4. **Modeling:**
   - Use a deep learning regression model (Sequential neural network with Dense layers).
   - Input features: Year, Month, DayOfWeek  
   - Target: Daily mean energy consumption (`energy_mean`)  
   - Optimization: Adam optimizer, MSE loss, Early stopping to prevent overfitting.
5. **Model Training & Validation:**
   - Split data into training and testing sets.
   - Train the model and validate performance on unseen data.
6. **Prediction & Evaluation:**
   - Predict daily energy consumption.
   - Evaluate performance using MSE and visualization (loss curves, scatter plots, smoothed line plots).

## Methodology
1. **Library Setup & Dataset Acquisition:**
   - Upload Kaggle API key, install Kaggle, and download the dataset.
2. **Data Loading & Sampling:**
   - Read the dataset using pandas and take a subset for faster experimentation.
3. **Feature Engineering:**
   - Convert dates to datetime format, set as index, and create features: Year, Month, DayOfWeek.
4. **Preprocessing:**
   - Handle missing values and scale features for neural network input.
5. **Model Development:**
   - Construct a deep learning regression model using Keras Sequential API.
   - Layers: Dense(64) → Dense(32) → Dense(1)
6. **Training:**
   - Train model with early stopping to avoid overfitting.
   - Monitor training and validation loss.
7. **Evaluation & Visualization:**
   - Evaluate predictions using MSE.
   - Visualize results via:
     - **Loss curves**
     - **Scatter plots**
     - **Smoothed line plots** (Actual vs Predicted consumption)

## Output Observation
1. **Loss Plot:** Training and validation loss decrease steadily, showing good model learning without overfitting.  
2. **Scatter Plot:** Predicted values closely match actual energy consumption (points near y = x).  
3. **Smoothed line Plot:** Predicted trend follows actual energy usage, confirming accurate forecasting.   

## Tech Stack
- Python (Pandas, NumPy, Matplotlib, Seaborn)
- TensorFlow / Keras
- Scikit-learn
- Kaggle dataset (London Smart Meter data)

## Future Scope
- Extend model to hourly load forecasting.  
- Integrate with IoT-enabled smart meters.  
- Deploy as a web dashboard for real-time monitoring.  


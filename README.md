# Predictive-Maintenance-Binary-Classification

#### **Introduction**

This project focuses on predicting machine failures using machine learning models, with a primary objective to enhance predictive maintenance in industrial settings. Predictive maintenance, which is crucial for minimizing downtime and optimizing machine performance, relies on data-driven insights to preemptively address potential failures. In this project, we leveraged advanced machine learning algorithms and innovative feature engineering techniques to develop a predictive model capable of accurately forecasting machine failure conditions.

#### **Dataset and Initial Analysis**

The dataset used for this project contained various features related to machine operations, including:

- **Air Temperature [K]**
- **Process Temperature [K]**
- **Rotational Speed [rpm]**
- **Torque [Nm]**
- **Tool Wear [min]**
- **Machine Failure Modes (TWF, HDF, PWF, OSF, RNF)**

Each failure mode represents a specific type of machine malfunction, providing a granular perspective on the conditions leading to failures. Initially, the data was explored to understand the distribution of features, correlations, and potential anomalies. This exploration provided insights into the complex relationships between various operational parameters and failure outcomes.

#### **Feature Engineering**

Feature engineering played a pivotal role in this project, transforming raw data into meaningful features that could enhance model performance. We derived several new features, such as:

- **Power**: Calculated using the formula \( \text{Power} = \text{Torque} \times \left( \text{Rotational Speed} \times \frac{2 \pi}{60} \right) \)
- **Temperature Difference**: \( \text{Process Temperature} - \text{Air Temperature} \)
- **Interaction Terms**: Products and ratios of features like power, temperature difference, rotational speed, etc.

These engineered features aimed to capture the complex interactions and dynamics within machine operations, providing a richer dataset for the models to learn from.

#### **Model Selection and Hyperparameter Tuning**

We employed a stacking ensemble approach, combining three powerful models: LightGBM, Balanced Random Forest (BRF), and CatBoost. Each model has unique strengths, with LightGBM offering fast training speed and high efficiency, BRF addressing class imbalance, and CatBoost handling categorical features effectively.

Hyperparameter tuning was conducted using Optuna, a sophisticated optimization framework, to fine-tune each model's parameters. This process involved exploring a wide range of hyperparameters to identify the optimal settings for maximizing performance. The best parameters were saved and used for final model training.

#### **Model Training and Evaluation**

The final model was trained on the preprocessed and feature-engineered dataset. We utilized metrics such as Accuracy, Precision, Recall, F1 Score, and ROC AUC to evaluate the model's performance:

- **LightGBM**:
  - Accuracy: 0.994
  - Precision: 1.000
  - Recall: 0.828
  - F1 Score: 0.906
  - ROC AUC: 0.978

- **Balanced Random Forest**:
  - Accuracy: 0.9935
  - Precision: 1.000
  - Recall: 0.814
  - F1 Score: 0.898
  - ROC AUC: 0.987

- **CatBoost**:
  - Accuracy: 0.992
  - Precision: 0.935
  - Recall: 0.829
  - F1 Score: 0.879
  - ROC AUC: 0.988

- **Stacking Model**:
  - Accuracy: 0.994
  - Precision: 1.000
  - Recall: 0.828
  - F1 Score: 0.906
  - ROC AUC: 0.988

The stacking ensemble model demonstrated superior performance, effectively capturing the intricacies of machine failure dynamics. Its high recall and precision ensured that potential failures were accurately predicted, reducing the risk of false positives and negatives.

#### **Predictive Functionality and Practical Application**

To facilitate real-world application, we developed a user-friendly prediction function that accepts new operational inputs and forecasts potential failures. This function allows operators to enter parameters such as temperature, speed, torque, and tool wear, enabling timely interventions and maintenance scheduling.

Furthermore, the entire workflow, including preprocessing, feature engineering, and prediction, was encapsulated within a scalable pipeline. This design ensures seamless integration into existing industrial systems, supporting real-time monitoring and decision-making.

#### **Conclusion**

This project successfully demonstrated the potential of machine learning models to revolutionize predictive maintenance in industrial settings. By harnessing advanced algorithms and innovative feature engineering, we developed a robust predictive tool that can significantly enhance operational efficiency and safety. Future work may involve integrating real-time data feeds and exploring adaptive learning techniques to further refine the model's predictive capabilities. This approach sets the foundation for more intelligent, data-driven maintenance strategies, paving the way for smarter industrial operations.

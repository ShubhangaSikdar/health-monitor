# health-monitor
📌Overview of Health Monitoring System
This study proposes an artificial system that acts as a decision support system for analyzing the patient’s vitals (temperature, body mass index, blood pressure, and room temperature) to both classify the patient's health condition as well as estimate his or her resting heart rate at the same time. A cascade design is employed whereby the output from the classification step is used directly as the input for the regression process.

📊Dataset:
| Property | Details |
| :--- | :--- |
| Size | 500 patient records |
| Features | Temperature (°C), BMI, Systolic BP, Diastolic BP, Room Temperature |
| Target (Classification) | Condition — fever / high_bp / low_bp / normal |
| Target (Regression) | Heart Beat (bpm) — continuous |
| Missing Values | None |


⚙️Methodology
1. Exploratory Data Analysis (7 Layers)
• Skewness and feature distribution analysis (close to normal, no transformations needed)
• Outlier detection using IQR – no outliers found
• Heat map of correlation — Strongest linear predictor: Systolic BP & Heart Beat: r = 0.78
• Scatter plot + boxplot of feature vs target by condition
• Visualization of PCA in 2D - Clear cluster separation for all 4 conditions
• 3D visualization with multiple axes (BMI x Systolic BP x Heart Beat)
• Parallel Coordinates Plot

2. Feature Engineering & Cascade Architecture
• Creation of engineered features within the cardiovascular disease domain
• Cascade architecture where the classification model is used to predict the regression feature
• Insight: Patients with fever have an average heart beat rate of about 95 bpm compared to those without fever, who have an average rate of about 68 bpm – the 27 bpm difference is the greatest predictor for regression.

3. Modelling & Evaluation
| Task | Type | Key Metrics |
| :--- | :--- | :--- |
| Condition prediction | Multi-class classification | Accuracy, F1-score, Precision, Recall |
| Heart rate prediction | Regression | MAE, RMSE, R² |

💡Key Results
• Classification: Most informative features are Systolic BP and Temperature
• PCA analysis verifies complete linear separation in all 4 conditions
• Cascade architecture gives superior performance in regression compared to a standalone classifier
• Room Temperature has least variation across conditions, hence low information gain.

🛠️Tech Stack
• Language: Python 3.8+/
• ML: scikit-learn/
• Data: pandas, NumPy/
• Visualisation: matplotlib, seaborn/
• Dimensionality Reduction: PCA (sklearn.decomposition)/
• Encoding: LabelEncoder, OrdinalEncoder

🔑Skills:
• Multi-tasking in classification and regression in the same pipeline/
• Creation of cascaded models based on expert knowledge/
• Development of medical features from vital sign data/
• Evaluation of models through multiple metrics in two different machine learning tasks



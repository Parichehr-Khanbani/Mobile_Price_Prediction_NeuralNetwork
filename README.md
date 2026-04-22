# **Mobile Price Range Prediction _ Neural Network**
***Machine learning project that predicts mobile phone price ranges from hardware specifications using Logistic Regression and Neural Networks, achieving up to 98% accuracy.***
<p align="center">
  <img src="https://github.com/Parichehr-Khanbani/Mobile_Price_prediction_NeuralNetwork/blob/main/assets/Mobile_Phone_Evolution.jpg" alt="Mobile Price Banner" width="100%">
</p>
This project focuses on building and evaluating machine learning models to classify mobile phones into four price categories based on their technical specifications.

# 1.Project Overview
workflow of this project includes: 
*  feature engineering
*  exploratory data analysis
*  preprocessing
*  model training and hyperparameter tuning
*  performance comparison.

# 2. Dataset
The dataset contains 2000 samples and 21 features of mobile phone specifications and their corresponding price range category.

| Feature           | Description                                                                                                               |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------- |
| **battery_power** | Battery capacity of the phone in milliampere-hours (mAh).                                                                 |
| **blue**          | Indicates whether the phone has Bluetooth (1 = Yes, 0 = No).                                                              |
| **clock_speed**   | Processor speed in gigahertz (GHz).                                                                                       |
| **dual_sim**      | Indicates whether the phone supports dual SIM cards (1 = Yes, 0 = No).                                                    |
| **fc**            | Front camera resolution in megapixels.                                                                                    |
| **four_g**        | Indicates whether the phone supports 4G technology (1 = Yes, 0 = No).                                                     |
| **int_memory**    | Internal storage memory in gigabytes (GB).                                                                                |
| **m_dep**         | Mobile depth (thickness) in centimeters.                                                                                  |
| **mobile_wt**     | Weight of the phone in grams.                                                                                             |
| **n_cores**       | Number of processor cores.                                                                                                |
| **pc**            | Primary (rear) camera resolution in megapixels.                                                                           |
| **px_height**     | Display resolution height in pixels.                                                                                      |
| **px_width**      | Display resolution width in pixels.                                                                                       |
| **ram**           | RAM size in megabytes (MB).                                                                                               |
| **sc_h**          | Screen height in centimeters.                                                                                             |
| **sc_w**          | Screen width in centimeters.                                                                                              |
| **talk_time**     | Battery talk time duration on a single charge.                                                                            |
| **three_g**       | Indicates whether the phone supports 3G technology (1 = Yes, 0 = No).                                                     |
| **touch_screen**  | Indicates whether the phone has a touchscreen (1 = Yes, 0 = No).                                                          |
| **wifi**          | Indicates whether the phone supports WiFi (1 = Yes, 0 = No).                                                              |
| **price_range**   | Target variable indicating the price category of the phone (0 to 3, where each number represents a different price tier). |

# 3.Workflow summary
The project followed a structured machine learning workflow:

3.1.Feature Engineering
*  Two additional features were created to improve model performance:
   *  px_total to capture overall display resolution
   *  screen_area to represent physical screen size
     
   These features provided more informative representations of display characteristics.

3.2.Data Preprocessing
*  Split into training, validation, and test sets
*  Standardization applied using StandardScaler
*  No missing values present
*  Features retained based on predictive usefulness

3.3.Model Development

*  Model 1: Logistic Regression implemented on original data
*  Model 2: Logistic Regression implemented on transformed data
*  Model 3: Neural Network
  
# 4.Models Implemented

Two primary models were trained and optimized:
*  Model 1: Logistic Regression
    *  Solver: lbfgs / saga (during tuning)
    *  Regularization applied
    *  Hyperparameters optimized using cross-validation
    *  Final model retrained on full training + validation data

*  Model 2: Neural Network (MLPClassifier)
    *  Architecture: (100, 100) hidden layers
    *  Activation: tanh
    *  Solver: lbfgs / adam
    *  Learning rate and regularization optimized
    *  Early stopping applied during tuning

# 5.Model Evaluation & Conclusion
Models were evaluated using a separate test set with the classification metrics inclusing accuracy and F1-score (macro).
| Model               | Accuracy | F1 Macro |
| ------------------- | -------- | -------- |
| Logistic Regression | 0.9825   | 0.9825   |
| Neural Network      | 0.9475   | 0.9475   |

Key Findings:

Logistic Regression outperformed the Neural Network:
*  Higher overall accuracy and F1 score
*  Better precision across all price classes
*  Fewer misclassifications
*  Stronger generalization performance
*  The confusion matrix showed that Logistic Regression made only minimal errors and achieved near-perfect classification.
  
<p align="center">
  <img src="https://github.com/Parichehr-Khanbani/Mobile_Price_prediction_NeuralNetwork/blob/main/assets/confusion matrix.png" alt="Confusion Matrix banner" width="100%">
</p>

Key conclusions:
*  RAM is the strongest predictor of price range
*  Logistic Regression achieved the best overall performance with 98.25% accuracy
*  Neural Networks performed well but did not surpass Logistic Regression
*  The problem is highly structured and largely linearly separable

Logistic Regression was selected as the final model due to its superior accuracy, reliability, and interpretability.





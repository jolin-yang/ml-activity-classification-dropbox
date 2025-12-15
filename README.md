#  Team 1 (Dropbox) - 📊📱 Predicting Human Physical Activity Using Smartphone Sensor Data
---

### 👥 **Team Members**

| Name             | GitHub Handle | Contributions                                                             |
|------------------|---------------|--------------------------------------------------------------------------|
| Jolin Yang    | @jolin-yang | EDA, feature engineering, subsampling (to handle class imbalance), Logistic Regression model training and evaluation |
| Jocelyn Chan   | @jocelynchan042     | EDA, feature engineering, oversampling (to handle class imbalance), K-NN model training and evaluation |
| Rebecca Michel     | @rebeccamichel1266  | EDA, feature engineering, Random Forest model training and evaluation                 |
| Ayoub Sougrati      | @asougrati       | EDA, feature engineering, class weighting (to handle class imbalance), hyperparameter tuning  |
| Ekin Chakma       | @ekin2038    | EDA, feature engineering, hyperparameter tuning, Simple Neural Network model training and optimization         |

---
## 📌 **Objective**

Use smartphone time-series accelerometer and gyroscope data to build a supervised ML classifier that predicts human physical movement (like sitting, walking, laying down, etc.), transforming raw sensor data into meaningful health insights.


## 🎯 **Project Highlights**

- Trained, tuned, and evaluated 4 different machine learning models (Logistic Regression, K-NN, Random Forest, Simple Neural Network) to predict human physical activity.
- Gained exposure to time-series data, multiclass classification, sensor data, and windowing techniques.
- Achieved 93% accuracy, ~93% precision, and ~93% recall for the (tuned) Logistic Regression model, demonstrating strong predictive performance for healthcare and wellness-related applications.
- Generated actionable health insights to inform data-driven decision-making in healthcare contexts.
- Gained hands-on experience across the full end-to-end machine learning pipeline, from EDA to model deployment. 
  
---

## 👩🏽‍💻 **Setup and Installation**

* How to clone the repository
* How to install dependencies
* How to set up the environment
* How to access the dataset(s)
* How to run the notebook or scripts

---

## 🏗️ **Project Overview**

- This was our Fall AI Studio Project for the fall portion of the Break Through Tech Program. 
- In this project, we were partnered with **Dropbox**, and our Challenge Advisor was **Ameya Bhatawdekar**.
- A little bit about Dropbox...
  - **Dropbox**: A cloud workspace designed for storing, sharing, and collaborating on files in real-time.
  - Relevance to our project:
    - **Dropbox Dash**: A parallel to Dropbox’s own AI that understands and anticipates user intent from sequences of actions across files, messages, and tools.
    - Both Dropbox Dash and our classifiers leverage temporal pattern recognition to enable intelligent, proactive assistance.
- **Project Goal**: Turn raw, messy sensor data (accelerometer/gyroscope data) into clear labels (ie. walking, sitting, running, laying) and extracting useful, action-ready health insights. 
 - Real-life Relevance: 
According to the World Health Organization, nearly 31% of adults worldwide, or 1.8 billion people, do not get enough daily physical activity. With so many adults not getting enough activity, we decided to build a machine learning model that processes raw sensor data and predicts human activity.

Understanding human activity through smartphone sensors isn’t just a technical challenge; it’s a gateway to improving real lives. Our model can help researchers design better fitness apps, enable healthcare providers to monitor patients remotely, and even empower individuals to maintain healthier habits. By transforming raw motion data into meaningful insights, our ML classifier can promote well-being and drive innovation across health-focused technologies.

---

## 📊 **Data Exploration**

**You might consider describing the following (as applicable):**

* The dataset(s) used: origin, format, size, type of data
* Data exploration and preprocessing approaches
* Insights from your Exploratory Data Analysis (EDA)
* Challenges and assumptions when working with the dataset(s)

**Potential visualizations to include:**

* Plots, charts, heatmaps, feature visualizations, sample dataset images

---

## 🧠 **Model Development**

**You might consider describing the following (as applicable):**

* Model(s) used (e.g., CNN with transfer learning, regression models)
* Feature selection and Hyperparameter tuning strategies
* Training setup (e.g., % of data for training/validation, evaluation metric, baseline performance)


---

## 📈 **Results & Key Findings**

**You might consider describing the following (as applicable):**

* Performance metrics (e.g., Accuracy, F1 score, RMSE)
* How your model performed
* Insights from evaluating model fairness

**Potential visualizations to include:**

* Confusion matrix, precision-recall curve, feature importance plot, prediction distribution, outputs from fairness or explainability tools

---

## 🚀 **Next Steps**

**You might consider addressing the following (as applicable):**

* What are some of the limitations of your model?
* What would you do differently with more time/resources?
* What additional datasets or techniques would you explore?

---

## 📝 **License**

If applicable, indicate how your project can be used by others by specifying and linking to an open source license type (e.g., MIT, Apache 2.0). Make sure your Challenge Advisor approves of the selected license type.

**Example:**
This project is licensed under the MIT License.

---

## 📄 **References** (Optional but encouraged)

Cite relevant papers, articles, or resources that supported your project.

---

## 🙏 **Acknowledgements** (Optional but encouraged)

Thank your Challenge Advisor, host company representatives, TA, and others who supported your project.

#  Team 1 (Dropbox) - 📊📱 Predicting Human Physical Activity Using Smartphone Sensor Data
---

### 👥 **Team Members**

| Name             | GitHub Handle | Contributions                                                             |
|------------------|---------------|--------------------------------------------------------------------------|
| Jolin Yang    | @jolin-yang | EDA, feature engineering, subsampling (to handle class imbalance), Logistic Regression model training and evaluation, GitHub repository and README |
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

* To clone the repository, open the VSCode terminal and run the following commands:
  - **git clone** https://github.com/jolin-yang/ml-activity-classification-dropbox.git
  - **cd ml-activity-classification-dropbox**

* To access the dataset, navigate to the directory titled 'UCI-HAR dataset' or download it here at https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones. 

* To install Jupypter Notebooks, run the following command in the terminal:
  - **pip install notebook**
* In this project, we distributed the different tasks/steps among our five team members and created separate notebooks for each task to maintain modularity and organization. As a result, all of the code for this project lives in separate notebooks instead of just one.
  - To explore the steps we took for feature engineering, navigate to the directory titled 'Feature Engineering', and run the separate notebooks. To explore the process behind training, tuning, and evaluating our 4 different models, navigate to the directory titled 'Model Training, Tuning, and Evaluation', and run the notebooks. To explore the additions/enhancements we made to our project after completing the main steps and having some time leftover, navigate to the directory titled 'New Additions'.
    
* To run a notebook, first open the notebook in VSCode and either by (1) clicking on the **Run All** button in the menu or (2) entering **jupyter notebook notebook_name.ipynb** in the terminal, with notebook_name.ipynb being the name of the notebook you want to run. 

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

**Why this matters**...  

According to the World Health Organization, nearly 31% of adults worldwide, or 1.8 billion people, do not get enough daily physical activity. With so many adults not getting enough activity, we decided to build a machine learning model that processes raw sensor data and predicts human activity.

Understanding human activity through smartphone sensors isn’t just a technical challenge; it’s a gateway to improving real lives. Our model can help researchers design better fitness apps, enable healthcare providers to monitor patients remotely, and even empower individuals to maintain healthier habits. By transforming raw motion data into meaningful insights, our ML classifier can promote well-being and drive innovation across health-focused technologies.

---

## 📊 **Data Exploration**

* **Dataset: UCI-HAR (Human Activity Recognition Using Smartphones) dataset**
  - Dataset was split into test and train folders, and most files were in the form of .txt files instead of .csv files we were most used to working with.
      - 561 features
      - 10,299 rows
        - Training set: 7,352 rows
        - Test set: 2,947 rows
 
- Dataset Attributes: 
  - Contained no missing values
  - Had some class imbalance (ie. the "LAYING” and “STANDING" classes were more prevalent in the dataset compared to other classes)    

- We didn't need to address missing values because the dataset contained none.    

- Although there was some class imbalance in the dataset, as mentioned above, we ultimately chose to leave the classes as is since the classes were only slightly unbalanced - in which we considered the imbalance to be negligible - and our baseline Logistic Regression model still performed relatively well.    
  
  However, after finalizing our models and having some time leftover near the end of our project, we decided to test out different techniques (oversampling, undersampling, class weighting) to address the class imbalance and see the difference it had (if any) on the performance of the models.  

- One of the biggest challenges we had while working with the dataset was having a limited understanding of the scientific terms in the dataset, especially when we were exploring its features, and what exactly each of them represented. The dataset's README was helpful in clearing up some of our confusion, we also conducted our own outside research we did to gain a more thorough understanding of the dataset and its features. 



**Exploratory Data Analysis (EDA) Visualizations**

 
<img width="580" height="591" alt="image" src="https://github.com/user-attachments/assets/09924858-0c36-4e75-9eeb-3e92560cfbc4" />

Figure: A bar plot displaying the distribution of Activity classes in the training dataset.      




<img width="587" height="455" alt="image" src="https://github.com/user-attachments/assets/18ce2c4f-f8c1-4c09-84ee-a90392319c85" />    

<img width="1085" height="790" alt="image" src="https://github.com/user-attachments/assets/b7146490-2f04-496f-b384-972c59ea4e8e" />    

Figure: A heatmap displaying the correlation between the first 30 features in the dataset.      


---

## 🧠 **Model Development**

* **Models Used**:
  - Logistic Regression
  - K-NN
  - Random Forest
  - Simple Neural Network
    
* **Feature Engineering**: 
  - Performed two rounds of feature engineering
    - 1st (preliminary) round:
      - Evenly split up the 561 features among our five team members
        - ~100-120 features per person
      - Each person performed correlation analysis on their subset to identify highly correlated features and select the most informative features
      - Correlation analysis involved looking for features with > 0.9 correlation and removing one of them
      - **274 features remain**
    - 2nd round:
      - Combine all the features we had selected from the 1st round
      - Perform another correlation analysis on this subset of features to remove any remaining redundant features and further reduce the featureset.
      - **131 features remain**

  - **561 total features → 131 final features ≈ 77% decrease in featureset**

  At the end of our project, we had some time leftover, so we decided to see how the models would have performed had we only used one round of feature engineering as opposed to two.
  - One Round of Feature Engineering:
    - Used entire dataset, undivided
    - Reduced features by < 1%
    - Found that more features -> better accuracy

    - Model Performance
      - Logistic Regression: 96.2% accuracy
      - Simple Neural Network: 94.9% accuracy


* **Hyperparameter Tuning**
  - Used GridSearch CV
    
* **Training setup**
  - 70% of data for training/validation, 30% of data for testing
  - Baseline performance with Logistic Regression model: ~93% accuracy

---

## 📈 **Results & Key Findings**

* **Performance Metrics**
  - Accuracy
  - Precision
  - Recall
  - F-1 Score
  - Loss (for Simple Neural Network)
    

| Model                                                             |         Accuracy          |       Precision       |      Recall      |      F-1 Score      |
|-------------------------------------------------------------------|----------------------|----------------------|--------------------|--------------------|
| Optimized Logistic Regression Classifier           | 0.898 |  0.326 | 0.846 |--------------------|
| Optimized K-NN Classifier                 | 0.890 |  0.603 | 0.851 |--------------------|
| Optimized Random Forest Classifier               | 0.885 |  0.334 | 0.848 |--------------------|
| Optimized Simple Neural Network Classifier                 | 0.85 |  --  | -- |--------------------|
    
#### **Best-performing model: Logistic Regression**

**Visualizations:**

<img width="677" height="567" alt="image" src="https://github.com/user-attachments/assets/655bdaf1-fffd-462f-8cf1-4b7c70348926" />     

Figure: The confusion matrix for the tuned Logistic Regression model.      


<img width="1856" height="650" alt="image" src="https://github.com/user-attachments/assets/f268283a-5d10-41be-a7b6-fb06f78c43c5" />
Figure: The visualizations displaying the relationship between epoch and accuracy and epoch and loss for the tuned Simple Neural Network model.      

---

## 🚀 **Next Steps**

- Consider ensemble models to improve accuracy.
  
- Retraining all our models using the features from one round of feature engineering (probably would expect to see better model accuracy overall). 
  
- **Deploy machine learning model on a user-friendly interface.**
  1. Finalize model and pre-processing: use our Logistic Regression model
  2. Package model: save training pipeline for serialization
  3. Build server-based inference pipeline: API
     - Easier to update model versions and centralized monitoring
     - Python FastAPI or Flask app → predict endpoint
  4. Define expected input schema: what the API requires to match trained data
  5. Implement real-time preprocessing: convert raw signals
  6. Containerization: use Docker
  7. Deploy to cloud platform: becomes a public service
     - Use Google Cloud Run → beginner-friendly

**Limitation of Logistic Regression Model:**
- Appears to have trouble distinguishing between walking upstairs versus walking downstairs. 

---

## 📝 **License**
N/A

---

## 🙏 **Acknowledgements** 

Special thanks to our Challenge Advisor Ameya, our Break Through Tech TA Andrii, and of course, the entire Break Through Tech Team (especially Maxime and Chu) for making this incredible opportunity possible!    

We truly appreciate the time and effort you all have dedicated into supporting and guiding us throughout each step of this project; your mentorship has made this experience so incredibly rewarding and it means a lot to us. 

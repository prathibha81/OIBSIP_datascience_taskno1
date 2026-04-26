# TASK 1
#  Iris Flower Classification



##  Project Overview

This project focuses on building a Machine Learning model to classify iris flowers into three species — **Setosa, Versicolor, and Virginica** — based on their physical measurements.

The project demonstrates the complete ML workflow including data analysis, preprocessing, model building, evaluation, and prediction.



##  Problem Statement

The objective of this project is to develop a supervised machine learning model that can accurately classify iris flowers into their respective species using four input features: sepal length, sepal width, petal length, and petal width. The model should learn patterns from the dataset and generalize well to unseen data.



##  Dataset Description

* Dataset: Iris Dataset (from Scikit-learn)
* Total Samples: 150
* Features:

  * Sepal Length (cm)
  * Sepal Width (cm)
  * Petal Length (cm)
  * Petal Width (cm)
* Target Classes:

  * Setosa (0)
  * Versicolor (1)
  * Virginica (2)

The dataset is clean, balanced, and widely used for classification tasks.



##  Exploratory Data Analysis (EDA)

Key observations from the dataset:

* No missing values were found
* All classes are equally distributed (balanced dataset)
* Petal length and petal width are highly correlated
* Setosa class is clearly separable from the other two classes
* Versicolor and Virginica show slight overlap

Visualization techniques such as pairplots and heatmaps were used to understand relationships between features.



##  Data Preprocessing

The following preprocessing steps were applied:

1. Separation of features (X) and target (y)
2. Train-test split (80% training, 20% testing)
3. Feature scaling using StandardScaler

Feature scaling was necessary because KNN is a distance-based algorithm.



##  Train-Test Split

The dataset was split into:

* Training Data: 80%
* Testing Data: 20%

This ensures that the model is evaluated on unseen data, which helps measure its generalization ability.



#  K-Nearest Neighbors (KNN) — Detailed Explanation



##  What is KNN?

K-Nearest Neighbors (KNN) is a **supervised machine learning algorithm** used for classification and regression. In this project, it is used for classification.

It is a **non-parametric** and **lazy learning algorithm**, meaning it does not assume any underlying distribution and does not build an explicit model during training.



##  Core Idea of KNN

KNN works based on the principle:

> “Similar data points exist close to each other.”

When a new data point is given, the algorithm:

1. Calculates the distance between the new point and all training data points
2. Selects the **K nearest neighbors**
3. Assigns the class based on **majority voting**



##  Example

If K = 3:

Neighbors:

* Setosa
* Setosa
* Versicolor

Prediction → **Setosa**



##  Distance Calculation

KNN uses distance metrics such as:

* Euclidean Distance (most common)
* Manhattan Distance

### Euclidean Distance Formula:

d = √[(x1 - x2)² + (y1 - y2)²]

This helps determine how close data points are to each other.



##  Choosing the Value of K

The value of K is very important:

* Small K (e.g., 1 or 3):

  * Sensitive to noise
  * May lead to overfitting

* Large K:

  * Smooth decision boundary
  * May lead to underfitting

In this project, **K = 3** was used for optimal performance.



##  How KNN Works in This Project

1. The model stores all training data
2. When a new sample is given:

   * It calculates distances
   * Finds nearest neighbors
   * Predicts the majority class



##  Important Characteristics

* KNN does not learn a formula — it memorizes data
* Prediction time is slower compared to training
* Performance depends heavily on:

  * Choice of K
  * Distance metric
  * Feature scaling



##  Why Feature Scaling is Important in KNN

KNN is distance-based, so:

If features have different scales:

Example:

* Feature A = 1000
* Feature B = 1

 Feature A will dominate distance calculation 

To avoid this, we use **StandardScaler** to normalize all features.



##  Advantages of KNN

* Simple and easy to understand
* No training phase (lazy learning)
* Works well with small datasets
* Effective for non-linear boundaries



##  Disadvantages of KNN

* Slow for large datasets
* Sensitive to noise
* Requires feature scaling
* Choosing K can be tricky



##  Model Training

The KNN model was trained using the training dataset:

* Algorithm: KNeighborsClassifier
* K value: 3



##  Model Evaluation

* Accuracy Achieved: **100%**
* Confusion Matrix showed high correctness with minimal errors

This indicates that the model performs well on unseen data.



##  Predictions

The trained model can predict the species of a new flower by taking its measurements as input and applying the learned patterns.



##  Key Insights

* Petal features are the most important for classification
* The dataset is simple and well-structured
* KNN performs very well on this dataset
* Proper preprocessing improves performance



##  Future Improvements

* Try advanced models like Random Forest and SVM
* Perform hyperparameter tuning
* Use cross-validation
* Deploy the model using Streamlit



##  How to Run the Project

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the notebook:

```bash
jupyter notebook iris_classification.ipynb
```

---

##  Author

Ummalla Prathibha
Data Science Intern

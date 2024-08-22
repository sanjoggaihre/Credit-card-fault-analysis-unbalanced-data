# Credit_Card_Fault_Analysis

In this project, I used Kaggle datasets. The datasets has around 250000 geniune data, and 490 faulty data.
Due to the unbalanced dataset, we got the biased model. To overcome this, we have used two approach

## Approach 1: UpSampling

In this method, the faulty data is upsampled to around 250000 data. But it cause repetition of datasets which results in 100% accuracy of the model. So, I used another approach

## Approach 2: Downsampling

In this method, geniune data is downsampled to around 490 data. Then I have trained the model using two methods:

    # Method 1 : Using Keras Sequential Model
    I got an accuracy of 92% using keras sequential model

    # Method 2 : Using gradient descent implementation
    I have implemented the gradient descent algorithm to update the weight and bias. Then I tested the data using test_set, and got a same accuracy of 92%

## Hyperparameter Tunning
Also, I have implemented the hyperparameter tunning to calculate the best hyperparameter for the model. For this I have used KerasClassifier and GridSearchCV. Among the various parameters, 92% accuracy is achieved using activation': 'relu', 'batch_size': 64, 'epochs': 10, 'learning_rate': 0.01, 'optimizer': 'sgd'.

## Model interpretability
I have used SHAP to visualize the models features. By using the SHAP graph we can find out which feature is most important for predicting the credit card fault analysis. SHAP summary plot visualizes the SHAP values to understand feature importance and the impact of each feature on model predictions

**Use case of SHAP:**
* Generally, we treat the deep learning models as a black box. We don't know which features are important
* Let's take an example of a Bank Loan Approval System. We feed the details about age, location, salary, and other financial metrics. Some customers may be unsure why their loans are rejected. So, if he/she wants to understand why the loan is denied, we can use the SHAP plot to describe the contributing features for loan approval or rejection.
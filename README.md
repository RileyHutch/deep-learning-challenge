# Overview of the Analysis

The purpose of this analysis is to build a neural network model that predicts whether an organization will successfully use funding from Alphabet Soup. The model uses historical funding data to learn which features correlate with success, which in turn will help the foundation identify the most promising funding applicants.

## Data Preprocessing

- **Target Variable:**
  - **IS_SUCCESSFUL** – This binary variable indicates whether the funding was used effectively.

- **Feature Variables:**
  - **APPLICATION_TYPE** (with a cutoff applied to manage its 17 unique values)
  - **AFFILIATION**
  - **CLASSIFICATION** (with a cutoff applied to manage its 71 unique values)
  - **USE_CASE**
  - **ORGANIZATION**
  - **STATUS**
  - **INCOME_AMT**
  - **SPECIAL_CONSIDERATIONS**
  - **ASK_AMT** (with a cutoff applied to manage its 8,747 unique values)

- **Removed Variables:**
  - **EIN**
  - **NAME**  
  These identification columns were removed because they are not predictive features for the model.

## Compiling, Training, and Evaluating the Model

### Model Architecture Details

The neural network is defined as follows (as seen in the provided code):

- **First hidden layer (100 neurons): ReLU activation**  

- **Second hidden layer (80 neurons): ReLU activation**  

- **Third hidden layer (60 neurons): ReLU activation**  
 
- **Fourth hidden layer (40 neurons): ReLU activation**  
 
- **Output layer (1 neuron): Sigmoid activation**  

**Total Trainable Parameters:** 20,321

### Model Performance

After training, the model achieved:
- **Accuracy:** 73.00%
- **Loss:** 0.5533

### Steps to Increase Model Performance

- Applied a cutoff value to the **ASK_AMT** variable due to its high number of unique values, thereby reducing noise and potential overfitting from this feature.
- Experimented with the number of neurons in each layer, as well as adding 2 additional hidden layers which led to the final architecture detailed above.
- Changed the output layer from a linear activation function to a sigmoid to help better predicict the binary classification of "IS_SUCCESSFUL".
- Added an extra 20 epochs to the model to help better fit the data.

## Summary

- The deep learning model uses a sequential architecture with five dense layers, featuring a decreasing number of neurons (100, 80, 60, 40, and 1) across the layers.
- Data preprocessing involved:
  - Selecting **IS_SUCCESSFUL** as the target variable.
  - Using relevant features while removing non-informative identification columns (**EIN** and **NAME**).
  - Applying a cutoff on **ASK_AMT**, **APPLICATION_TYPE**, and **CLASSIFICATION** to handle their larger than normal number of unique values.
- The model achieved a training accuracy of 73.00% with a loss of 0.5533.

- **Further Options**  
  If I was to continue tyring to improve the accuracy of this model I would look into using PCA to help analyze which vairables were most impactful and remove or diminish the least impactful.

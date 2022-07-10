# Neural Network Charity Analysis
## Overview of the analysis
Alphabet Soup is a foundation company that invests in other organizations according to some criteria. Distributing the funds effectively across eligible companies is one of the most important purposes of this company as well. Over the years Alphabet soup has interacted with over 34000 companies and gathered their internal data as well as classification status from Alphabet Soup's aspect. With the help of machine learning, we applied some deep learning techniques such as Keras and tried to determine in case of any investment, if the certain company will be successful or not. 

- We get the data with the outcome (this section falls to supervised learning)
- Cleaned the data 
- Converted the objects to integer
- Scaled the data (For outliers)
- Split the data into Training and Testing Set
- set the Keras model with hidden layers and neurons and epochs
- evaluate the outcome.

As a result, we tried to achieve if our data is sufficient to understand and determine a successful company and can we apply this model to the future or not.
## Results
### _Data Preprocessing_
#### - _What variable(s) are considered the target(s) for your model?_
According to our purpose, I determined the target as **IS_SUCCESSFUL—Was the money used effectively**
#### - _What variable(s) are considered to be the features of your model?_
After dropping the EIN, NAME and INCOME_AMT columns the features are:

APPLICATION_TYPE—Alphabet Soup application type

AFFILIATION—Affiliated sector of industry

CLASSIFICATION—Government organization classification

USE_CASE—Use case for funding

ORGANIZATION—Organization type

STATUS—Active status

SPECIAL_CONSIDERATIONS—Special consideration for application

ASK_AMT—Funding amount requested

####  _What variable(s) are neither targets nor features, and should be removed from the input data?_
EIN Number (Feature)
NAME of the company (Feature)   
INCOME_AMT, the income of the company (*) (Feature)

### Compiling, Training, and Evaluating the Model
#### _How many neurons, layers, and activation functions did you select for your neural network model, and why?_

hidden_nodes_layer1 = 50 Neurons  Activation Function= Relu

hidden_nodes_layer2 = 30 Neurons Activation Function= tanh

hidden_nodes_layer3 = 20 Neurons Activation Function= tanh
 
hidden_nodes_layer4 = 15 Neurons Activation Function= tanh

Outcome Layer  Activation Function= Sigmoid

- Reason:(1) I decided to go with the "ReLU" activation code in the layers because our model was pretty complex and multilayer. ReLU evaluates the values between 0 (zero) and infinite so no negative values are available. Also, we do not encounter with **Vanishing Gradient** problem here because maximum  Threshold values are infinity.

- Reason(2): We have four hidden layers because we are restricted to add new data to feed our model. With extra layers, we can train existing data better!

#### _Were you able to achieve the target model performance?_
with the total extra steps below that, I take to improve the model I only developed it ****0.02 %**** 

#### _What steps did you take to try and increase model performance?_
- Step1: Besides the EIN and NAME, I removed the INCOME_AMT column as well.
- Step2: APPLICATION_TYPE column binding increased from 500 to 1000
- Step3: Since we cannot add more data to our model, I added 2 more layers to train better the existing features
- Step4: I reduced the neurons on each layer to prevent overfitting
- Step5: Increased epochs to 400 to produce more effective coefficients. However, I increased the overfitting possibility here.

### BEFORE OPTIMIZING THE MODEL

![image](https://user-images.githubusercontent.com/98247252/178129659-e19c5b0c-9e45-46dd-9b13-f96c91a74628.png)

### AFTER OPTIMIZING THE MODEL

![image](https://user-images.githubusercontent.com/98247252/178129673-4e5de436-bb67-4c9c-9fe5-5880b3abf97b.png)

## Summary

Overall, optimizing the model with changing input data (features), increasing epochs and layers, reducing the neurons on each hidden layer and applying the ReLU activation function to each layer did not give a better result. My recommendation is to come together with the team and evaluate the input column's importance and if possible add more data to the source data. (to make it wider with more columns.)








































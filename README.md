# deep-learning-challenge
## Report on Neural Network Model

### Overview
A tool was created for the nonprofit foundation Alphabet Soup which helps to select the applicants for funding with the best chance of success in their ventures. Alphabet Soup's business team provided a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. The data set contains the following columns that capture the metadata about each organization:   
    EIN and NAME—Identification columns  
    APPLICATION_TYPE—Alphabet Soup application type    
    AFFILIATION—Affiliated sector of industry  
    CLASSIFICATION—Government organization   
    USE_CASE—Use case for funding  
    ORGANIZATION—Organization type  
    STATUS—Active status  
    INCOME_AMT—Income classification  
    SPECIAL_CONSIDERATIONS—Special considerations for application  
    ASK_AMT—Funding amount requested  
    IS_SUCCESSFUL—Was the money used effectively  

This data set was used to create a binary classifier that can predict whether applicatns will be successful if funded by Alphabet Soup.

### Process
#### Data Preprocessing
* EIN and Name identification columns were frmoved from the data set
* Created cutoff point to bin "rare" categorical variables into a new category "other" for "CLASSIFICATION" and "APPLICATION_TYPE"
* Used pd.get_dummies() to encode categorical variables
* Split the preprocessed data into a features arra, X, and a target array, y.
* Used the arrays and the train_test_split function to split the data into training and testing datasets.
* Sclaed the training and testing features datasets by creating a StandardScaler instance, and fitted it to the training data, using the transform function.

### Complie, Train, and Evaluate the Model
* Create a neural network model using Tensor Flow and Keras
* First hidden layer: 80 nodes, activation: relu
* Second hidden layer: 30 nodes, activation: rel
* Output layer: 1 mnode, activation: sigmoid, as the output is a binary classification between 0 and 1.
* Resulted in an accuracy of 72.7%

![Screenshot (88)](https://github.com/ColleenKarwoski/deep-learning-challenge/assets/119438532/a3c73c89-cd65-4ed4-8f74-ee758508789d)


#### Optimization attempt 1
* Lowered the "APPLICATION_TYPE" AND "CLASSIFICATION" cutouff to 100 using the same hyperparameters for the model as above. This resulted in an accuracy sore of 73.0%
   
   ![Screenshot (89)](https://github.com/ColleenKarwoski/deep-learning-challenge/assets/119438532/bebfde4f-3b8d-4a66-9e39-4bf012140f10)

### Optimization attempt 2
  * For my second attempt, the number of nodes in each layer was increased, which resulted in an accuracy score of 73.0%

![Screenshot (90)](https://github.com/ColleenKarwoski/deep-learning-challenge/assets/119438532/976708bf-8d70-4d75-ad43-ef99da8e75ca)

### Optimization attempt 3
  * For the third attempt, a third layer was added. This resulted in an accuracy score of 73.2%

![Screenshot (91)](https://github.com/ColleenKarwoski/deep-learning-challenge/assets/119438532/90a15e8e-8950-4cd9-9ce4-f21ff6320a53)

### Summary
Of the original and 3 optimization attempts, the models were not able to achieve the target predictive accuracy of 75%. The highest accuracy score was achieved in attempt 3 with an accuracy score of 73.2%. The hypertuning of the model produced only minimal changes in the accuracy score of the models. I would consider using an automated optimization neural network in order to attain higher accuracy.

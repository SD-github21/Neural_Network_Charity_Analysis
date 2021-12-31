# Neural Network Charity Analysis

The purpose of the Neural Network Charity analysis was to utilize machine learning and neural networks to create a binary classifier capable of predicting whether nonprofit organizations funded by AlphabetSoup will be successful. The first step was to preprocess the data for the neural network model. The second step was to compile, train, and evaluate the model. Third, steps were taken in an effort to optimize the neural network model. Finally the results of the overall deep learning model as well as a recommendation for a different model are provided.  

## Resources
- Data Sources: charity_data.csv
- Software: Jupyter Notebook, Pandas, scikit-learn, tensorflow

## Results

### Data Preprocessing Information

  - The variable "IS_SUCCESSFUL" was considered as the target of the neural network model
  - All other variables in the dataset were initially considered as features of the neural network model
  - However, the two identification variables, i.e., "EIN" and "NAME" were removed as they were considered neither features or targets

### Compiling, Training, and Evaluating the Initial Neural Network Model

  - The number of input features used for the initial neural network model was 43.
  - Two hidden layers were added to the model with the first layer containing 80 hidden nodes and the second layer containing 30 hidden nodes. The output layer contained 1 neuron.
  - The activation function "Rectified Linear Unit (ReLU)" was used for the first and second hidden layers while the activation function "Sigmoid" was used for the output layer, due to the project calling for a binary classifier. 
  - The above specifications of the neural network model were chosen in an effort to match the weekly challenge starter code. However, the following StackExchange discussion provided some guidance regarding model selection parameters, where one of the methods indicated that the number of hidden neurons (e.g., 80 and 30 for the current analysis) should be less than twice the size of the input layer (e.g., 86):

    https://stats.stackexchange.com/questions/181/how-to-choose-the-number-of-hidden-layers-and-nodes-in-a-feedforward-neural-netw
    
  - The following image depicts the model structure:

  ![image](https://user-images.githubusercontent.com/85533099/147799175-0b998066-d4c5-4956-a825-1be2bba1a015.png)

  - Evaluation of the model is summarized in the image below:
  
  ![image](https://user-images.githubusercontent.com/85533099/147799331-73a74f2d-5062-463f-bcb8-b846b304ff3a.png)

### Optimizing the Neural Network Model

  - First, two additional features, e.g., "APPLICATION_TYPE" and "SPECIAL_CONSIDERATIONS", were dropped with the identification columns ("EIN" and "NAME") in an effort reduce the number of input features for our neural network model. These two variables seemed to pertain only to the application process and seemed to be superfluous features to include in the neural network model. Therefore, these were considered "noisy variables" and dropped from further analyses. 
  
  - Second, elements were added to the neural network model, which included:
    - Adding 40 neurons to the second hidden layer
    - Adding one new hidden layer with 30 neurons
    - The third hidden layer included a different activation function from the others, i.e., "Leaky Rectified Linear Unit (Leaky ReLU)"
   
  - A summary of the optimized neural network model is depicted in the image below:
   
   ![image](https://user-images.githubusercontent.com/85533099/147799634-3ba9af16-9ccc-4bb0-8623-7d4d5a6e953e.png)

  - Evaluation of the model is summarized in the image below:

  ![image](https://user-images.githubusercontent.com/85533099/147799927-ebb47657-2fb5-4d00-a446-95b3d59a0301.png)

### Summary and Recommendation

  - As indicated above, the accuracy of the initial neural model was 0.724 while the accuracy of the optimized model was 0.703. Here, we see how adding more neurons and hidden layers does not necessarily enhance a deep learning model and in fact, can reduce its accuracy from a more simpler model. Both models fell short of a desired predictive accuracy of at least 75%. Therefore, it is recommended that a different model be tested in order to determine whether a simpler model would demonstrate better performance and achieve a higher accuracy score than 75%. For the current analysis, a Random Forest classifier appears be the best choice to explore using a different model to differentiate between successful and unsuccessful nonprofits for the following reasons:
    - Random Forest classifiers can be used for a binary classification problems such as the current analysis 
    - They can train on large datasets such as the one utilized in the current analysis
    - They use minimal code and can achieve comparable predictive accuracy as deep learning models but at a much faster rate


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
  - The above specifications of the neural network model were chosen in an effort to match the provided starter code for this challenge. However, the following StackExchange discussion provided some guidance regarding model selection parameters, where one of the methods indicated that the number of hidden neurons (e.g., 80 and 30 for the current analysis) should be less than twice the size of the input layer (e.g., 86):

    https://stats.stackexchange.com/questions/181/how-to-choose-the-number-of-hidden-layers-and-nodes-in-a-feedforward-neural-netw
    
  - The following image depicts the initial neural network model structure:

  ![image](https://user-images.githubusercontent.com/85533099/147799175-0b998066-d4c5-4956-a825-1be2bba1a015.png)

  - The initial neural network model weights were saved at an increment of every 5 epochs. 
  
  - Evaluation of the initial neural network model is summarized in the image below:
  
  ![image](https://user-images.githubusercontent.com/85533099/147799331-73a74f2d-5062-463f-bcb8-b846b304ff3a.png)

  - The initial neural network model was saved to an HDF5 file.
 
### Optimizing the Neural Network Model -- Attempts #1 - #3

  - First, two additional features, e.g., "APPLICATION_TYPE" and "SPECIAL_CONSIDERATIONS", were dropped with the identification columns ("EIN" and "NAME") in an effort reduce the number of input features for our neural network model. These two variables seemed to pertain only to the application process and seemed to be superfluous features to include in the neural network model. Therefore, these were considered "noisy variables" and dropped from further analyses. 
  
  - Second, elements were added to or removed from the neural network model, which included:
    - Adding a varying number of neurons to hidden layers
    - Adding new hidden layers or removing hidden layers
    - Adding different activation functions, i.e., including "Leaky Rectified Linear Unit (Leaky ReLU)" along with the "Rectified Linear Unit (ReLU)" and the "Sigmoid" functions
    - As noted above, specifications were explored according to the three rules of thumb noted in the StackExchange website discussion referenced above. The number of hidden neurons chosen satisfied one of the three possibilities mentioned, i.e., (1) between the size of the input layer and the size of the output layer; (2) approximately two-thirds the size of the input layer, plus the size of the output layer, and (3) less than twice the size of the input layer.
    - A summary of each model was generated
    - The optimized neural network model weights were saved at an increment of every 5 epochs. 
    - Evaluations of each model were conducted
    - Each optimized  neural network model was saved to files named "AlphabetSoupCharity_Optimization1.h5", "AlphabetSoupCharity_Optimization2.h5", and "AlphabetSoupCharity_Optimization3.h5".
     
  - A summary of the optimized neural network model Attempt #1 is depicted in the image below:
   
    ![image](https://user-images.githubusercontent.com/85533099/147799634-3ba9af16-9ccc-4bb0-8623-7d4d5a6e953e.png)

  - Evaluation of the optimized neural network model Attempt #1 is summarized in the image below:

    ![image](https://user-images.githubusercontent.com/85533099/147831587-e7812630-2611-4ca8-80ac-97242c568f6f.png)
  
  - A summary of the optimized neural network model Attempt #2 is depicted in the image below:
  
    ![image](https://user-images.githubusercontent.com/85533099/147842421-da5ff2dd-82f2-403b-8129-c23d39bc8e57.png)
  
  - Evaluation of the optimized neural network model Attempt #2 is summarized in the image below:
  
    ![image](https://user-images.githubusercontent.com/85533099/147842425-74d39051-35e3-4230-80cb-8a45a8873d7b.png)

  - A summary of the optimized neural network model Attempt #3 is depicted in the image below:
    
    ![image](https://user-images.githubusercontent.com/85533099/147842431-ac491984-a2ea-4513-bebe-e722ab75f058.png)
  
 - Evaluation of the optimized neural network model Attempt #3 is summarized in the image below:
    
    ![image](https://user-images.githubusercontent.com/85533099/147842439-e5d7bf94-b32e-4e3c-b1ce-241f5e643d24.png)
 

### Summary and Recommendation

  - As indicated above, the accuracy of the initial neural model was 0.724 while the accuracy of the optimized model was 0.703. Here, we see how changing the number of neurons and hidden layers as well as the activation functions did not necessarily enhance the deep learning models and in fact, could reduce accuracy from a more simpler model. All of the optimized models as well as the initial neural network model fell short of a desired predictive accuracy of at least 75%. Therefore, it is recommended that a different model be tested in order to determine whether a simpler model would demonstrate better performance and achieve a higher accuracy score. For the current analysis, a Random Forest classifier appears to be the best choice to explore to differentiate between successful and unsuccessful nonprofits for the following reasons:
    - Random Forest classifiers can be used for a binary classification as needed in the current analysis 
    - They can train on large datasets such as the one utilized in the current analysis
    - They use minimal code and can achieve comparable predictive accuracy as deep learning models but at a much faster rate


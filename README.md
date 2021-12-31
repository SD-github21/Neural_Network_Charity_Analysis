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
  - Two hidden layers were added the model with the first layer containing 80 hidden nodes and the second layer containing 30 hidden nodes. The output layer contained 1 neuron.
  - The activation function "Rectified Linear Unit (ReLU)" was used for the first and second hidden layers while the activation function "Sigmoid" was used for the output layer, due to the project calling for a binary classifier. 
  - The above specifications of the neural network model were chosen in an effort to match the weekly challenge starter code. However, the following StackExchange discussion provided some guidance regarding model selection parameters, where one of the methods indicated that the number of hidden neurons should be less than twice the size of the input layer:

    https://stats.stackexchange.com/questions/181/how-to-choose-the-number-of-hidden-layers-and-nodes-in-a-feedforward-neural-netw
    
  - The following image depicts the model structure:

![image](https://user-images.githubusercontent.com/85533099/147799175-0b998066-d4c5-4956-a825-1be2bba1a015.png)

  - Evaluation of the model is summarized in the image below:
 ![image](https://user-images.githubusercontent.com/85533099/147799278-c69820d3-3748-4092-98bb-10aaad4f38c6.png)



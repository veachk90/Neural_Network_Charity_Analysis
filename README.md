# Neural_Network_Charity_Analysis

#### Overview 
The goal of this analysis was to use existing data from charity events to predict whether future charities would be successful in using their funds effectively. Success, in this case, was primarily determined as a binary value given in one column of the provided data, rather than a set of objective criteria. In order to make the predictions, the data were used to train and evaluate an artificial neural network.

#### Results

Data Preprocessing
-What variable(s) are considered the target(s) for your model?
  The target variable was the 'IS_SUCCESSFUL' column given in the data. That is, This column was separated from the rest, which were then used as features that could     be  analyzed in order to predict the target variable.
-What variable(s) are considered to be the features for your model?
  The features were APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT
-What variable(s) are neither targets nor features, and should be removed from the input data?
  NAME and EIN were dropped from the data set, as neither would be likely to determine a given charity's success.
Compiling, Training, and Evaluating the Model
-How many neurons, layers, and activation functions did you select for your neural network model, and why?
  In the first attempt, I included three layers: the input layer, one hidden layer, and an output layer. In the input layer, since there were a total of 36 features 
  after one-hot encoding, there were 36 nodes. In the hidden layer, I included 5 nodes. Finally, the output layer only included one node, as that is all that is         necessary in binary classification problems. I wanted to start with a relatively simple neural network to see if it would suffice in making accurate predictions, as   neural networks have a tendancy to overfit the data if they are too complex. 
-Were you able to achieve the target model performance?
  I was not able to achieve target model performance. The specified accuracy to reach was 75%. However, the neural network model was only able to achieve about 71%,     with   a loss of about .58. 
-What steps did you take to try and increase model performance?
  Because accuracy was low, and loss was high, I judged that it was unlikely that the model was overfitting the data. Thus, I sought to increase the model's capacity     by increasing the number of nodes in the hidden layer to 50, then including a second hidden layer with 25 nodes. I also included a third hidden layer with 5 nodes,     which then fed into the output layer, still with a single node. Ultimately, this had little effect. Accuracy was still low, and loss was still high, so I determined   that the  problem would likely be with the data themselves. Initially, I had binned those categorical variables with greater than 10 unique values by placing any       entries that were unlikely to have significant impact into an 'Other' bin. This helped reduced the number of unique values for the categorical variables. The next     solution to attempt was to increase the number of unique values, thereby reducing the count of those in the 'Other' bins. Again, this had little impact on the total   outcome.
  
#### Summary 
Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.

Overall, the results were unimpressive. Accuracy on all three main attempts was between 70% and 72%, with loss at .58. This is likely due to the data not being easily classified by a neural network. Thus, I would most likely recommend a Random Forest classification model. This is because random forest models are resistant to outliers and 'noisy' data, which can make it difficult to train a neural network. Random forsts can also provide feature importance, or which features are most likely to have an impact on the outcome when making predictions. 

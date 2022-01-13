# Neural_Network_Charity_Analysis

## Overview of the loan prediction risk analysis:
The purpose of this analysis is to use the features in the provided dataset to help Beks create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup. 

## Results:
* Data Preprocessing: this analysis has been performed by importing and reading the data from the charity_data.csv file
* variable considered as the target for our model:  IS_SUCCESSFUL
* variables considered to be the features for our model: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT
Variables that are neither targets nor features, and should be removed from the input data: EIN, NAME
* Compiling, Training, and Evaluating the Model
* How many neurons, layers, and activation functions did you select for your neural network model, and why?
Number of Hidden Layers	2	Deep neural network is necessary for complex data, good starting point with low computation time.
Architecture (hidden_nodes1, hidden_nodes2)	(80, 30)	First layer has roughly two times the number of inputs (43), smaller second layer offers shorter computation time.
Hidden Layer Activation Function	Relu	Simple choice for inexpensive training with generally good performance.
Number of Output Nodes	1	Model is a binary classifier and should therefore have one output predicting if IS_SUCCESSFUL is True or False.
Output Layer Activation Function	sigmoid	Provides a probability output (value between 0 and 1) for the classification of IS_SUCCESSFUL.
Verifying with the testing set, we obtain the following results:
Loss: 0.5648046731948853
Accuracy: 0.7271137237548828
### Result of the Neural Network model![Results](https://user-images.githubusercontent.com/89410157/149258204-8b98af32-1c24-40ec-a0de-4e9b1a23c9b7.png)
 
* Were you able to achieve the target model performance?
We were not able to optimize our model in order to achieve a target predictive accuracy higher than 75%.

* What steps did you take to try and increase model performance?
Our first attempt was to increase the number of Attempt 1 Increase the number of epochs to 200. 
Verifying with the testing set, we obtain the following results :
Loss: 0.571734607219696
Accuracy: 0.7268804907798767
We can see that the result did not increase a lot
### Attempt 1 with 200 epochs![Attempt 1 with 200 epochs](https://user-images.githubusercontent.com/89410157/149258230-52b4eb72-3c90-4e81-96f3-e8a162954c85.png)
 In our second attempt we try to increase hidden layers to 3 with 80, 40, and 30 nodes and  relu activation function at inner layers.
Verifying with the testing set, we obtain the following results:
Loss: 0.6139729022979736
Accuracy: 0.7259474992752075
### Attempt 2 with 3 hidden layers![Attempt 2 with 3 hidden layers](https://user-images.githubusercontent.com/89410157/149258242-173a8004-3645-4c76-86ef-a6a2e9d92d2f.png)
On the third attempt we decrease the number of Input Features by replacing for example the income_counts if it is less than 3000. We also decrease the aff_counts when it is less that 15000. 
We also drop the "SPECIAL_CONSIDERATION_N".
Verifying with the testing set, we obtain the following results:
Loss: 0.5619295835494995
Accuracy: 0.7315452098846436
### Attempt 3 by reducing the number of Input Features![Attempt 3 by reducing the number of Input Features](https://user-images.githubusercontent.com/89410157/149258261-af64f340-d62c-498e-8769-9c1cc5135194.png)

## Summary: 
We can see that the result of the nural network model does not exceed 73% of accuracy. The optimization we have made doesn’t help the meet the target accuracy of 75%.
Looking at the results we recommend using the SVM models. The SVM model take similar amounts of time to train on the input data compare to the deep learning one. The only noticeable difference between the two models is implementation—the amount of code required to build and train the SVM is notably less than the comparable deep learning model. As a result, many data scientists will prefer to use SVMs by default, then turn to deep learning models, as needed.


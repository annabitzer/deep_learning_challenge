# Deep Learning Challenge
The purpose of this analysis was to create a neural network model which could predict the success of non-profit startup organizations, to assist the non-profit foundation Alphabet Soup in deciding which business ventures to provide funding to. Data from over 34000 past business ventures were used to create and train the model.

# Results

## Data Pre-Processing
-   Target Variable:  IS_SUCCESSFUL (was the money used effectively)
-   Features: APPLICATION_TYPE (Alphabet Soup application type)
              AFFILIATION (Affiliated sector of industry)
              CLASSIFICATION (Government organization classification)
              USE_CASE (Use case for funding)
              ORGANIZATION (Organization type)
              STATUS (Active status) 
              INCOME_AMT (Income classification)
              SPECIAL_CONSIDERATIONS (Special considerations for application)
              ASK_AMT (Funding amount requested)
  - Dropped Variables: EIN and NAME (for identification only)
  - Additional pre-processing: The application type and classification features were simplified, where uncommon results were combined as the result "other" for each column.

## Compiling, Training, and Evaluating the Initial Model

![image](https://github.com/annabitzer/deep_learning_challenge/assets/149126016/de96c459-e44d-40be-b114-59f095d16fec)
In the first version of the model, there were two hidden layers with relatively small amounts of neurons (11 & 13), the commonly used relu activation function was employed, and the model was trained for 100 epochs. This was intended to be a starting point, starting with a smaller amount of resources to see how the model would perform. 

-  Accuracy: 0.731
-  Loss: 0.552

## Optimization Attempts
Three additional versions of the model were optimized and trained in an attempt to improve performance. Many steps were taken to try and improve performance.

- Preprocessing Optimization Steps:
    The preprocessing of the CLASSIFICATION column was tweaked to combine a smaller amount of results into the "other" column, in case information was being lost by combining too many results.
    The STATUS and SPECIAL_CONSIDERATIONS columns were dropped to simplify the dataset.

- Model Building Optimization Steps:
    ![image](https://github.com/annabitzer/deep_learning_challenge/assets/149126016/857042f0-398d-497e-a977-9584d7fd7fc0)
  Additional neurons and an additional hidden layer were added in an attempt to increase performance. A third hidden layer (seen above) did not seem to have any affect on performance, and the increase of neurons from 25 to 100 in each layer (not pictured) also did not increase  performance.

  ![image](https://github.com/annabitzer/deep_learning_challenge/assets/149126016/194da4f2-02bc-4507-9532-05434ccf2168)
  A version of the model was tested using the tanh activation function for each hidden layer rather than the relu activation function.

  ![image](https://github.com/annabitzer/deep_learning_challenge/assets/149126016/0a6fd193-0e9f-4b5e-9ad4-7c5ca26064b8)
  Finally, the number of epochs was increased from 100 to 150, to give the model more time to train.

## Optimization Outcome
Ultimately, the attempts taken to optimize the model did not result in the desired model performance of 75% accuracy. All three optimization attempt actually resulted in lower accuracy than the first model, the various additions of resources did not provide the desired outcome of a more accurate model.

# Summary
Overally, the model did have moderate accuracy performance of 73.1%, but fell short of the target performance of 75% accuracy. I do feel that some additional data pre-processing could be done to simplify the dataset further, and perhaps result in a payoff of higher accuracy - perhaps binning the "ASK_AMT" column into similar stratifications as the "INCOME_AMT". Additionally, a different machine learning model could be tested, such as a random forest model. Random forest models are a good choice for complex datasets such as this one, and are robust against outliers and possible overfitting.  

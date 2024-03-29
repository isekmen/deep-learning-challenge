# Deep Learning Challenge

## Desription
The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

* **EIN** and **NAME**—Identification columns
* **APPLICATION_TYPE**—Alphabet Soup application type
* **AFFILIATION**—Affiliated sector of industry
* **CLASSIFICATION**—Government organization classification
* **USE_CASE**—Use case for funding
* **ORGANIZATION**—Organization type
* **STATUS**—Active status
* **INCOME_AMT**—Income classification
* **SPECIAL_CONSIDERATIONS**—Special consideration for application
* **ASK_AMT**—Funding amount requested
* **IS_SUCCESSFUL**—Was the money used effectively

## Instructions

### Step 1: Preprocess the Data

Using the knowledge of Pandas and scikit-learn’s `StandardScaler()`, you’ll need to preprocess the dataset. This step prepares you for Step 2, where you'll compile, train, and evaluate the neural network model.

1. Read in the charity_data.csv to a Pandas DataFrame, and be sure to identify the following in your dataset:
  * What variable(s) are the target(s) for your model?
  * What variable(s) are the feature(s) for your model?
2. Drop the `EIN` and `NAME` columns.
3. Determine the number of unique values for each column.
4. For columns that have more than 10 unique values, determine the number of data points for each unique value.
5. Use the number of data points for each unique value to pick a cutoff point to bin "rare" categorical variables together in a new value, `Other`, and then check if the binning was successful.
6. Use `pd.get_dummies()` to encode categorical variables.
7. Split the preprocessed data into a features array, `X`, and a target array, `y`. Use these arrays and the `train_test_split` function to split the data into training and testing datasets.
8. Scale the training and testing features datasets by creating a `StandardScaler` instance, fitting it to the training data, then using the `transform` function.


### Step 2: Compile, Train, and Evaluate the Model

Using your knowledge of TensorFlow, you’ll design a neural network, or deep learning model, to create a binary classification model that can predict if an Alphabet Soup-funded organization will be successful based on the features in the dataset. You’ll need to think about how many inputs there are before determining the number of neurons and layers in your model. Once you’ve completed that step, you’ll compile, train, and evaluate your binary classification model to calculate the model’s loss and accuracy.

1. Continue using the Jupyter Notebook in which you performed the preprocessing steps from Step 1.
2. Create a neural network model by assigning the number of input features and nodes for each layer using TensorFlow and Keras.
3. Create the first hidden layer and choose an appropriate activation function.
4. If necessary, add a second hidden layer with an appropriate activation function.
5. Create an output layer with an appropriate activation function.
6. Check the structure of the model.
7. Compile and train the model.
8. Create a callback that saves the model's weights every five epochs.
9. Evaluate the model using the test data to determine the loss and accuracy.
10. Save and export your results to an HDF5 file. Name the file `AlphabetSoupCharity.h5`.

### Step 3: Optimize the Model

Using your knowledge of TensorFlow, optimize your model to achieve a target predictive accuracy higher than 75%.

Using any or all of the following methods to optimize your model:

* Adjust the input data to ensure that no variables or outliers are causing confusion in the model, such as:
  * Dropping more or fewer columns.
  * Creating more bins for rare occurrences in columns.
  * Increasing or decreasing the number of values for each bin.
  * Add more neurons to a hidden layer.
  * Add more hidden layers.
  * Use different activation functions for the hidden layers.
  * Add or reduce the number of epochs to the training regimen.

**Note**: If you make at least three attempts at optimizing your model, you will not lose points if your model does not achieve target performance.

1. Create a new Jupyter Notebook file and name it `AlphabetSoupCharity_Optimzation.ipynb`.
2. Import your dependencies and read in the `charity_data.csv` to a Pandas DataFrame.
3. Preprocess the dataset like you did in Step 1, Be sure to adjust for any modifications that came out of optimizing the model.
4. Design a neural network model, and be sure to adjust for modifications that will optimize the model to achieve higher than 75% accuracy.
5. Save and export your results to an HDF5 file. Name the file `AlphabetSoupCharity_Optimization.h5`.

### Step 4: Write a Report on the Neural Network Model

For this part of the assignment, you’ll write a report on the performance of the deep learning model you created for AlphabetSoup.

The report should contain the following:

1. **Overview** of the analysis: Explain the purpose of this analysis.

The purpose of the charity funding analysis for Alphabet Soup was to predict where the company would approve/make investments. Our goal was to use machine learning and neural networks to apply target/features on the dataset, create a binary classifier that was capable of predicting whether investors would be successful if funded by Alphabet Soup. We started with 34,000 organizations and 12 columns that captured the metadata about each organization and their past funding outcomes. This project compromised of the following 3 steps: 
- Preprocessing the data for the neural network 
- Compile, Train and Evaluate the Model 
- Optimizing the model

2. **Results**: Using bulleted lists and images to support your answers, address the following questions.

  * Data Preprocessing
    * What variable(s) are the target(s) for your model?
      - **IS_SUCCESSFUL** is the target that is marked 1 for successful. The latter indicates that the company's past funding was successful.
    * What variable(s) are the features for your model?
      - **IS_SUCCESSFUL**,  is the feature column chosen data for the model.
    * What variable(s) should be removed from the input data because they are neither targets nor features?
      - **EIN** and **Name** should be removed from the input data because they are neither targets nor features
  
* Compiling, Training, and Evaluating the Model
    * How many neurons, layers, and activation functions did you select for your neural network model, and why?
    - For the neural network model there were 2 hidden layers. The first layer had 80 neurons, the second has 30 there is also an output layer. The first and second hidden layer have the "relu" activation function. Relu is faster to compute and does not activate all the neurons at the same time. The output node was 1 and the activation function that was used was ‘Sigmoid’ as this model output is a binary classification between 0 and 1.

   
![pic 1](https://github.com/isekmen/deep-learning-challenge/assets/101214487/d47307e1-50ef-46e9-ac48-08981e1e2a55)

![pic 2](https://github.com/isekmen/deep-learning-challenge/assets/101214487/b92cbd4e-6d3e-4b53-b1a6-8d36a90fbbf5)

    * Were you able to achieve the target model performance?
      - Yes, by optimizing the model, the accuracy increased from 73% to 79%.

![pic 3](https://github.com/isekmen/deep-learning-challenge/assets/101214487/5419ca28-fb1b-4bec-be51-b66f97131d6c)


![pic 6](https://github.com/isekmen/deep-learning-challenge/assets/101214487/78c31e34-070f-40f7-9ef3-52311ef07f7f)

    * What steps did you take in your attempts to increase model performance?
      - It required converting the NAME column into data points, and adding a third hidden layer.

![pic 4](https://github.com/isekmen/deep-learning-challenge/assets/101214487/fbb66473-cfa9-462f-93db-b835a1971fb6)

![pic 5](https://github.com/isekmen/deep-learning-challenge/assets/101214487/14e39172-ab2f-4201-83c0-c20ca95e229d)


3. **Summary**: Summarize the overall results of the deep learning model.

This neural network trained model was automatically optimized using the keras-tuner method. It achieved 79% prediction accuracy with a 0.4752 loss. Converting NAME column into data points and adding aditional hidden layer performed the best and achieved the target predictive accuracy higher than 75%.

An alternate possibility to using a Neural Network is Random Forest. Random Forest is less expensive, has a faster performance, and requires less preprocessing and training is simpler.

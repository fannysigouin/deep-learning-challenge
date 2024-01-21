# Alphabet Soup Charity - Neural Network Model Report

## Overview

A nonprofit foundation, Alphabet Soup, wants a tool to help select applicants for funding that have the best chance of success in their ventures. The features in the provided dataset were used to create a binary classifier that can predict whether applicants will be successful if fundded by Alphabet Soup.

Alphabet Soup provided a CSV file containing more than 34,000 organizations that have received funding from the foundation over the years, capturing metadata about each organization such as their affiliated sector of industry, government organization classification, use case for funding, organization type, special considerations, and funding amount requested.

## Results

### Data preprocessing:
- The target variable for this model was the `IS_SUCCESSFUL` column from the provided CSV file.
- The feature variables for this model included the remaining columns `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`, `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS`, and `ASK_AMT`.
- Two columns were dropped from the dataframe, `EIN` and `NAME` as they were neither features nor the target variable.
- For the initial model in `AlphabetSoupCharity.ipynb`, the rare values in the `APPLICATION_TYPE` and `CLASSIFICATION` columns were binned, and the categorical values were encoded using `pd.get_dummies()`.

### Compiling, training, and evaluating the model:

The initial model in `AlphabetSoupCharity.ipynb` started with an input layer with 80 neurons and a `relu` activation function, followed by a hidden layer with 40 neurons and a `relu` activation function. Lastly, the model had an output layer with a `sigmoid` activation function. The number of neurons chosen for the input layer was based on the number of features in the preprocessed dataset (41). The hidden layer had less neurons (40) allowing the model to get closer to identifying a pattern.

After training the initial model on 100 epochs, it produced the following results when evaluated on testing data:
- Loss: 0.5809
- Accuracy: 0.7275

The initial model thus did not achieve the target performance of 75% accuracy.

In `AlphabetSoupCharity_Optimization.ipynb`, multiple attempts were made to optimize the model. In addition to the columns that were already dropped in the initial model, the `SPECIAL_CONSIDERATIONS` and `STATUS` columns - both were binary columns (Y/N and 0/1) with N and 0, respectively, accounting for 0.07% and 0.01% of the dataset, thus not significantly contributing to the outcome. The cutoff value for the binning of the `APPLICATION_TYPE` column was also increased from 500 to 1,000. The unique values in the `INCOME_AMT` column were also binned.

The first attempt to optimize the model kept the same number of hidden layers and neurons as the initial model, as well as the same activation functions. After training the model for 100 epochs, the loss and accuracy it produced did not represent any improvement over the initial model.

The second optimization attempt added a third hidden layer with 20 neurons and kept the same activation functions. Again, this iteration did not produce significantly better results than the previous models.

The third attempt changed the activation functions for the input and hidden layers from `relu` to `tanh`, keeping the same number of layers and neurons. However, this model also did not perform better than previous ones.

The fourth attempt kept `tanh` as the input and hidden layers' activation functions but added a fourth hidden layer with 20 nodes. The third hidden layer also increased from 20 to 40 nodes, however the model's performance remained relatively the same.

Lastly, a fifth attempt was made to optimize the model byu increasing the number of nodes in the second hidden layer from 40 to 80, and the number of nodes in the fourth hidden layer from 20 to 40. Even with this fifth attempt, the model's performance did not significantly improve.

Initial model:
- Loss: 0.5809
- Accuracy: 0.7275

First optimization attempt:
- Loss: 0.5599
- Accuracy: 0.7299

Second optimization attempt:
- Loss: 0.5624
- Accuracy: 0.7271

Third optimization attempt:
- Loss: 0.5593
- Accuracy: 0.7298

Fourth optimization attempt:
- Loss: 0.5604
- Accuracy: 0.7273

Fifth optimization attempt:
- Loss: 0.5612
- Accuracy: 0.7276

## Summary

In summary, the overall performance of the model would not be satisfactory to implement at the Alphabet Soup foundation due to its lack of accuracy and high loss percentage. 

The model performed best in its third iteration, with the lowest loss of 55.9% and the best accuracy of 0.729%. The model in this iteration had three hidden layers with 80, 40, and 20 neurons respectively, all with a `tanh` activation function, and an output layer with a `sigmoid` activation function.


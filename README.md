# Deep Learning Challenge: Alphabet Soup Charity

This repository contains my work for the 21st challenge of the UofT SCS edX Data Bootcamp.

## Background

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

- EIN and NAME—Identification columns
- APPLICATION_TYPE—Alphabet Soup application type
- AFFILIATION—Affiliated sector of industry
- CLASSIFICATION—Government organization classification
- USE_CASE—Use case for funding
- ORGANIZATION—Organization type
- STATUS—Active status
- INCOME_AMT—Income classification
- SPECIAL_CONSIDERATIONS—Special considerations for application
- ASK_AMT—Funding amount requested
- IS_SUCCESSFUL—Was the money used effectively

## Summary

This challenge was completed by preprocessing the data, binning rare values in certain columns and encoding categorical columns. After separating the target and features from the dataset, the data was split into training and testing datasets. A first neural network model, in `AlphabetSoupCharity.ipynb`, was ran on the training data, achieving an accuracy of 72.75% with a loss of 58.1%. Multiple attempts were made in `AlphabetSoupCharity_Optimization.ipynb` to optimize the model and improve its performance, including changing the activation functions of the input and hidden layers, increasing the number of hidden layers and the number of neurons within each layer, and further preprocessing of the data by removing and binning additional columns and values.

A full breakdown of the model and optimization attempts can be found in `AlphabetSoupCharity_Report.md`.

## References

IRS. Tax Exempt Organization Search Bulk Data Downloads https://www.irs.gov/charities-non-profits/tax-exempt-organization-search-bulk-data-downloads.
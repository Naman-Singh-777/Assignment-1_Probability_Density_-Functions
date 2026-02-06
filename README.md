# Assignment 1 Probability Density Functions

This repository contains the solution to Assignment-1 (Title: Learn Probability Density Functions using Roll-Number-Parameterized Non-Linear Model).
The dataset is to be uploaded to colab from the attached zip folder and is to be run along with the code file.

## Student Information

Year: 3rd Year B.Tech CSE

Roll Number: 102317144

## Problem Statement

The task is to learn parameters of a probability density function using NO2 data from India Air Quality dataset. The transformation is based on my roll number.

## Methodology

### Step 1: Data Transformation

I loaded the India Air Quality dataset from Kaggle and extracted the NO2 column values. After that I applied the transformation formula given in the assignment.

The transformation formula is: z = x + ar*sin(br*x)

For my roll number 102317144, I calculated:
- ar = 0.05 * (102317144 % 7) = 0.25
- br = 0.3 * (102317144 % 5 + 1) = 1.5

### Step 2: Parameter Estimation

I needed to estimate three parameters for the probability density function: p(z) = c * e^(-λ(z-μ)²)

The approach I used was:

First I calculated μ (mu) which is the mean of all transformed z values.

Then I found λ (lambda) using the formula λ = 1/(2*variance).

Finally I calculated c which is the normalization constant using c = √(λ/π).

This basically fits a Gaussian-like distribution to the transformed data.

### Step 3: Implementation Details

I used pandas library for loading and handling the CSV data. For mathematical calculations I used numpy. Before doing any calculations I removed all NaN (missing) values from the NO2 column. I used vectorized operations which makes the code run faster.

## Results

After running the code on the complete dataset I got these parameter values:

mu (μ) = [your value here]

lambda (λ) = [your value here]

c = [your value here]

Total number of data points used: [fill this in]

## Dataset Information

I used the India Air Quality Data from Kaggle. The link is https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data

The specific feature I used was NO2 which represents nitrogen dioxide pollution levels measured across different cities in India.

The main file used is city_day.csv

## Files in This Repository

solution.ipynb contains the complete Python code in Jupyter notebook format

data.csv is the dataset file

README.md is this documentation file

## How to Run the Code

Step 1: Upload the dataset CSV file to Google Colab

Step 2: Open the solution notebook file

Step 3: Run all the cells in order

Step 4: The output will show the three parameter values

## Libraries Required

The code uses two main Python libraries:

pandas for data manipulation

numpy for numerical calculations

Both are pre-installed in Google Colab so no extra installation needed.

## Key Observations

The transformation formula changes the distribution of data based on the roll number. This means different students will get different results.

The sine function in the transformation adds a non-linear component to the data which makes it more interesting.

The parameter values depend heavily on the variance of the transformed data.

After transformation, the data roughly follows a Gaussian pattern which is why this PDF form works well.

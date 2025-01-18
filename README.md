# Wine Quality Assessment
![Python](https://img.shields.io/badge/Python-blue?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-orange?logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-red?logo=keras&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-blue?logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-yellowgreen?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-blueviolet?logo=matplotlib&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-lightblue?logoColor=white)

## Abstract

The Wine Quality Assessment project aims to predict and classify wine quality using machine learning models based on chemical attributes of red and white wines. The dataset, sourced from the UCI Machine Learning Repository, includes 11 numerical features and quality scores assigned by wine experts. Two approaches were developed: (1) Regression models to predict quality on a continuous scale (0-10) and (2) Classification models to categorize wines into four quality levels (Bad, Medium, Good, Excellent). The combined dataset (6,497 samples) includes an added type feature to distinguish red and white wines. Neural networks were designed with 12 inputs for both tasks, demonstrating the application of deep learning to regression and classification problems.

## The Original Data:
Wine makers from Portugal studied many types of wine both quantitatively and qualitatively. For each wine they measured 11 numerical chemical attributes (e.g., chlorides, density, pH value) and they asked 3 or more “experts” to assign a “quality value” (0 to 10), recording the median score from the experts.

The data is originally provided by the Machine Learning Repository of the University of California - Irvine (UCI) in two csv files:

winequality-red.csv ….. (4898 red wines)
[Link for the Dataset winequality-red.csv](http://archive.ics.uci.edu/ml/machine-learning-databases/wine-quality/winequality-red.csv)

winequality-white.csv ….. (1599 white wines)
[Link for the Dataset winequality-white.csv](http://archive.ics.uci.edu/ml/machine-learning-databases/wine-quality/winequality-white.csv)

## Adapting the data for a REGRESSION model (red & white together), target = quality (0 to 10)
The two files will be considered together (red & white wines) for a total of 4898 + 1599 = 6497 samples and one more attribute (‘type’) will be added to each sample, to identify if the sample is from a red (type = 1) or a white (type = 0) wine.

Therefore, the neural network for solving this regression problem, will have:
• 12 inputs in the first layer (the 11 original attributes AND the new ‘type’ attribute)
• 1 output processing element in the output layer, since the result will be a single number (0 to 10)

Changing the targets to CLASSIFY 4 QUALITY LEVELS (3 or less = “BAD” & level 1; 4, 5, or 6 = “MEDIUM” & level 2 ; 7 or 8 = “GOOD” & level 3; 9 or more = “EXCELLENT” & level 4)

A CLASSIFICATION MODEL, will provide as output an indication of the QUALITY LEVEL (BAD, MEDIUM, GOOD or EXCELLENT) of each wine sample.
To implement this, the 6497 x 1 ‘level’ array will be ‘one-hot-encoded’ to yield a 6497 x 4 array, where each of the 6497 samples will have as target a 4-element array where 3 of the numbers will be 0 and only one will be 1

Therefore, the network to perform classification of the wines into the 4 LEVELS of quality will have;
• 12 inputs in the first layer (the 11 original attributes AND the new ‘type’ attribute)
• 4 processing elements in the output layer. Ideally one of them would turn to 1 and three would remain at 0, to indicate that the input sample belongs to one of the 4 levels of quality.

In Summary, the developed project contains TWO TYPES OF MODELS:
[1] REGRESSION MODELS: regmodl
[2] CLASSIFICATION MODELS: clasmodl


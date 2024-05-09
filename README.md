# House Price Predictor

## Overview

This repository contains code for a house price predictor. The predictor is built using Python and utilizes custom machine learning functions from `My_ML_Lib`, `pandas` for data manipulation, and `matplotlib` for visualization.

## Usage

To use the house price predictor, follow these steps:

1. Install the required libraries: `My_ML_Lib`, `pandas`, and `matplotlib`.
2. Clone this repository to your local machine.
3. Ensure you have a dataset named `test.csv` containing the test data.
4. Import the necessary modules:

```python
import My_ML_Lib as my
import pandas as pd
import matplotlib.pyplot as plt
x_train = my.get_data("test.csv", "test", "all", "")
X = my.prepare_data(x_train, "Id")
inn = [12, 13, 8, 10, 26, 24, 15, 2, 1, 7, 28, 11, 27, 5, 6]
x_final = my.drop_index(X, inn)
x_final["Id"]=x_train["Id"].tolist()
mod = my.load_model("finalized_model_using_regression_1.pkl")
my.save_ans(mod, x_final, "answer.csv", "Id", "SalePrice")
```

#Files
house_price_predictor.py: Python script containing the code for the house price predictor.
finalized_model_using_regression_1.pkl: Pre-trained machine learning model for house price prediction.
test.csv: Test dataset containing features for house price prediction.
answer.csv: Output file containing predicted house prices.

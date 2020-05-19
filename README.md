# M5 SALES FORECASTING
### Descriptive analysis

This notebook's goal is to explore the data at hand and understand how we can make (decent) predictions with it.

## The Project
In this competition, the fifth iteration, you will use hierarchical sales data from Walmart, the world’s largest company by revenue, to forecast daily sales for the next 28 days. The data, covers stores in three US States (California, Texas, and Wisconsin) and includes item level, department, product categories, and store details. In addition, it has explanatory variables such as price, promotions, day of the week, and special events. Together, this robust dataset can be used to improve forecasting accuracy.

## The Evaluation

This competition uses a Weighted Root Mean Squared Scaled Error (RMSSE). Extensive details about the metric, scaling, and weighting can be found in the M5 Participants Guide.

### Submission File

Each row contains an id that is a concatenation of an item_id and a store_id, which is either validation (corresponding to the Public leaderboard), or evaluation (corresponding to the Private leaderboard). You are predicting 28 forecast days (F1-F28) of items sold for each row. For the validation rows, this corresponds to d_1914 - d_1941, and for the evaluation rows, this corresponds to d_1942 - d_1969. (Note: a month before the competition close, the ground truth for the validation rows will be provided.)

The files must have a header and should look like the following:

id,F1,...F28
HOBBIES_1_001_CA_1_validation,0,...,2
HOBBIES_1_002_CA_1_validation,2,...,11
...
HOBBIES_1_001_CA_1_evaluation,3,...,7
HOBBIES_1_002_CA_1_evaluation,1,...,4


## The data

We start by loading packages and the data. Originally, we have 4 different data files:

* calendar.csv - Contains information about the dates on which the products are sold.
* sales_train_validation.csv - Contains the historical daily unit sales data per product and store [d_1 - d_1913]
* sample_submission.csv - The correct format for submissions. Reference the Evaluation tab for more info.
* sell_prices.csv - Contains information about the price of the products sold per store and date.

One month prior to the competition deadline the file *sales_train_evaluation.csv*, including sales [d_1 - d_1941], will be made available.
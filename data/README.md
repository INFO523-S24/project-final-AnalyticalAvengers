
## Description of the Dataset:

The dataset “crash_data” that will be used for this project has been sourced from the official website of the Massachusetts Registry of Motor Vehicles. This dataset was chosen due to the relevance it holds in today’s day and age that is witness to an unfortunate increase in road accidents since the past 30 years. Analysing this data can help find patterns to create an algorithm or model that can predict crashes which could extensively assist in preventing accidents and possible deaths. By working on this data, we can contribute with identification of place/time of possible accidents that could aid in ensuring safer travel experiences for the public.

The dataset consists of 72 dimensions, some of which are - Crash Number, City Town/Name, Crash Date, Crash Severity, Crash Time, Crash Year, Max Injury Severity Reported, Age of Driver - Youngest Known, Age of Driver - Oldest Known etc.



```{python}
#| label: initial-EDA
#| echo: false
#| message: false

import numpy as np
import pandas as pd
# Read in the data
url = 'data/crash_data.csv'
crash_data = pd.read_csv(url)

# # Display dimensions of the dataset
dimensions = crash_data.shape
print(f"Dimensions of the dataset: {dimensions} \n")

# Display data types of each column
data_types = crash_data.dtypes
print("Display the data types for each feature:")
print(data_types)

numerical_vars = crash_data.select_dtypes(include = ['int64', 'float64']).columns.tolist()
categorical_vars = crash_data.select_dtypes(include = ['object', 'category']).columns.tolist()

# Display the counts of numerical and categorical variables
print(f"\nNumber of numerical variables: {len(numerical_vars)}")
print(f"Number of categorical variables: {len(categorical_vars)}")
print('\n')

crash_data.head()

```




# How to import the dataset for usage?
This module will help you import the dataset.  
The dataset contains the data from the Data Logger installed at AISSMS Institute of Information Technology, Pune.  
The dataset is semicolon separated instead of comma separated.  
Also, the column names contain unwanted data logger titles. Column names contain IOITSecure447> which is not useful at all and hence is dropped from the column names.
Hence, with the following code, you can import the dataset and rename the columns with the Python Pandas module.  

---

# Code (python3)

import pandas as pd  
dataset = pd.read_csv(r"file_path.csv", sep = ";", na_values=["NA", "NaN", "Missing", "Null", "NULL"])  
new_column_names = [col.split(">", 1)[-1].strip() for col in dataset.columns]  
data.columns = new_column_names  
data.head()  

---
The above code creates a python pandas dataframe called "dataset" and then stores the values from the csv file in the dataframe.

# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.

# DATASET:
https://www.kaggle.com/datasets/wasiqaliyasir/breast-cancer-dataset/code

## NAME: Kamesh D
## REG: 212222240043

# PROGRAM:
```py
import pandas as pd
import matplotlib.pyplot as plt

# 1 & 2: Load the CSV file
try:
    file_path = 'Breast_cancer_dataset.csv'
    data = pd.read_csv(file_path)

    # 3: Create a synthetic date range for the length of the data
    # We'll pretend each patient was recorded on a subsequent day starting from Jan 1, 2023.
    # The number of periods will match the number of rows in the data.
    date_range = pd.date_range(start='2023-01-01', periods=len(data), freq='D')

    # 4: Set the new date range as the index of the DataFrame
    data.set_index(date_range, inplace=True)

    # 5: Plot the time series of 'radius_mean'
    plt.figure(figsize=(12, 6))
    plt.plot(data.index, data['radius_mean'], label='Mean Radius Over Time (Simulated)', color='purple')

    # 6: Customize the plot
    plt.title('Simulated Time Series of Tumor Mean Radius', fontsize=16)
    plt.xlabel('Simulated Date', fontsize=12)
    plt.ylabel('Mean Radius', fontsize=12)
    
    # 7: Add a grid and legend
    plt.grid(True)
    plt.legend()
    
    plt.tight_layout()

    # 8: Display the plot
    plt.show()

except FileNotFoundError:
    print(f"Error: The file '{file_path}' was not found.")
except KeyError as e:
    print(f"Error: A required column {e} was not found in the CSV file.")


```



# OUTPUT:

<img width="1189" height="590" alt="image" src="https://github.com/user-attachments/assets/8949a2b0-c9c9-4558-a0e3-17409999001e" />





# RESULT:
Thus we have created the python code for plotting the time series of given data.

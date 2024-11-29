# Documentation for Statistical Analysis and Visualization Project

## Overview
This project performs **statistical analysis** and **visualization** on a dataset using Python libraries: **Pandas**, **NumPy**, **Matplotlib**, and **SciPy**. The program calculates basic statistical measures (mean, median, and mode) for each column in the dataset and visualizes these statistics using bar plots.

---

## Requirements
1. Python installed on your system.
2. Libraries:
   - **Pandas** for data manipulation and analysis.
   - **NumPy** for numerical computations.
   - **Matplotlib** for plotting and visualization.
   - **SciPy** for advanced statistical operations.

To install the required libraries, use:
```bash
pip install pandas numpy matplotlib scipy
```

---

## Input
- The dataset is provided in a **CSV file** named `data.csv`.
- The file should be located in the same directory as the script or its path should be correctly specified in the `file_path` variable.

---

## Workflow
1. **Read Data**:
   - The program reads the dataset using Pandas' `read_csv()` function.
   - A preview of the first 5 rows of the dataset is printed using `data.head()`.

2. **Statistical Analysis**:
   - **Mean**:
     - Computed for each column using `data.mean()`.
   - **Median**:
     - Computed for each column using `data.median()`.
   - **Mode**:
     - Computed using `data.mode().iloc[0]` to retrieve the most frequent value in each column.

3. **Visualization**:
   - Bar plots are created for mean, median, and mode values of all columns using Matplotlib.
   - Subplots are arranged in a single row with three plots for side-by-side comparison.

---

## Code Explanation

### 1. Importing Libraries
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy import stats
```
These libraries provide functionalities for data analysis, statistical computation, and visualization.

---

### 2. Reading the Dataset
```python
file_path = 'data.csv'
data = pd.read_csv(file_path)
print("Data Preview:")
print(data.head())
```
- The dataset is read into a Pandas DataFrame named `data`.
- `data.head()` displays the first 5 rows to give a quick preview.

---

### 3. Calculating Statistical Measures
```python
mean_values = data.mean()
median_values = data.median()
mode_values = data.mode().iloc[0]
```
- **Mean**: Average of each column.
- **Median**: Middle value of each column when sorted.
- **Mode**: Most frequent value. The `.iloc[0]` ensures the mode is selected correctly even if multiple modes exist.

---

### 4. Printing Results
```python
print("\nMean Values:")
print(mean_values)
print("\nMedian Values:")
print(median_values)
print("\nMode Values:")
print(mode_values)
```
The computed statistics are displayed for the user to inspect.

---

### 5. Visualization
```python
plt.figure(figsize=(12, 6))

plt.subplot(1, 3, 1)
mean_values.plot(kind='bar', title='Mean Values')
plt.xlabel('Columns')
plt.ylabel('Mean')

plt.subplot(1, 3, 2)
median_values.plot(kind='bar', title='Median Values', color='orange')
plt.xlabel('Columns')
plt.ylabel('Median')

plt.subplot(1, 3, 3)
mode_values.plot(kind='bar', title='Mode Values', color='green')
plt.xlabel('Columns')
plt.ylabel('Mode')

plt.tight_layout()
plt.show()
```
- **Subplots**: Three bar plots are arranged in one row to display mean, median, and mode values for each column.
- **Customizations**:
  - Titles, axis labels, and colors differentiate the plots.
  - `tight_layout()` ensures proper spacing between plots.

---

## Output
1. **Console Output**:
   - The first 5 rows of the dataset.
   - Calculated mean, median, and mode values for all columns.

2. **Visualization**:
   - A figure with three bar plots comparing the mean, median, and mode values for each column.

---

## How to Run the Program
1. Ensure the required libraries are installed.
2. Save the script as a `.py` file (e.g., `statistics_analysis.py`).
3. Place the dataset file (`data.csv`) in the same directory or update the `file_path` variable with the correct location.
4. Run the script:
   ```bash
   python statistics_analysis.py
   ```
5. View the statistical analysis in the console and the visualization in a pop-up window.

---

## Example Dataset Format (`data.csv`)
| Column1 | Column2 | Column3 |
|---------|---------|---------|
| 10      | 20      | 15      |
| 15      | 25      | 10      |
| 20      | 30      | 20      |

---

## Possible Enhancements
1. **Support for Missing Values**:
   - Handle missing or invalid data using Pandas' `fillna()` or `dropna()` methods.
2. **Additional Statistics**:
   - Compute standard deviation, variance, and percentiles.
3. **Interactive Visualization**:
   - Use libraries like **Plotly** for interactive plots.
4. **Dynamic File Input**:
   - Allow users to specify the CSV file path via input.

---

## Conclusion
This project provides an efficient way to analyze and visualize basic statistics from a dataset. It can be extended for more comprehensive data analysis tasks.

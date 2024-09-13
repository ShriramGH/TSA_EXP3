### Developed by : Shriram S
### Register No.: 212222240098
### Date :

# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the Methi vegetable price.

### ALGORITHM:

1. Import the necessary packages

2. Find the mean, variance and then implement normalization for the data.

3. Implement the correlation using necessary logic and obtain the results

4. Store the results in an array

5. Represent the result in graphical representation as given below.

### PROGRAM:

```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Load the CSV file
file_path = '/content/prices.csv'
data = pd.read_csv(file_path)

# Extract the 'Methi Price' data
methi_data = data['Methi'].dropna().values

# Mean
data_mean = np.mean(methi_data)

# Variance
data_var = np.var(methi_data)

# Normalized data
normalized_data = (methi_data - data_mean) / np.sqrt(data_var)

# Compute the autocorrelation function (ACF)
acf_result = np.correlate(normalized_data, normalized_data, mode='full')

# Take only the positive lags
acf_result = acf_result[len(acf_result)//2:]

# Plot the ACF
plt.figure(figsize=(10, 5))
plt.stem(acf_result[:36], use_line_collection=True)
plt.xlabel('Lag')
plt.ylabel('Autocorrelation')
plt.title('Autocorrelation Function (ACF) of Methi Prices')
plt.show()


```
### OUTPUT:

![image](https://github.com/user-attachments/assets/bc482f84-f5e9-4662-b9aa-81a7e4a57f3b)


#### Autocorrelation Function (ACF) of Methi Prices

![image](https://github.com/user-attachments/assets/7ed196da-c26c-471e-8f03-8cb861f80c1a)



### RESULT:

####     Thus auto correlation function in python is successfully implemented.

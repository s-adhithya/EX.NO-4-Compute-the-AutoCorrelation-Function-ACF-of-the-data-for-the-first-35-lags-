# EX.NO-4-Compute-the-AutoCorrelation-Function-ACF-of-the-data-for-the-first-35-lags-

## AIM:
To Write a Program to time series analysis and decomposition on the monthly average temperature of a city/country

## Equipments Required:
Hardware – PCs
Anaconda – Python 3.7 Installation / Jupyter notebook
## Procedure:
1 Import the numpy and matplotlib.pyplot modules.

2 Find the mean, variance and then implement normalization for the data.

3 Implement the correlation using necessary logic and obtain the results

4 Store the results in an array

5 Represent the result in graphical representation as given below.

## Program:
```
import matplotlib.pyplot as plt
import numpy as np

data = np.array([12.0, 24.0, 7.0, 20.0, 7.0, 22.0, 18.0, 22.0, 6.0, 7.0, 20.0, 13.0, 8.0, 5.0, 8.0])

plt.title("Autocorrelation Plot")
plt.xlabel("Lags")
plt.acorr(data, maxlags=14)
print("The Autocorrelation plot for the data is:")


plt.show()

program 2:
data = [12.0, 24.0, 7.0, 20.0, 7.0, 22.0, 18.0, 22.0, 6.0, 7.0, 20.0, 13.0, 8.0, 5.0, 8.0]

# Delay (lag) range that we are interesting in
lags = range(15)

# Pre-allocate autocorrelation table
acorr = len(lags) * [0]

# Mean
mean = sum(data) / len(data)

# Variance
var = sum([(x - mean)**2 for x in data]) / len(data)

# Normalized data
ndata = [x - mean for x in data]
# Go through lag components one-by-one
for l in lags:
    c = 1 # Self correlation

    if (l > 0):
        tmp = [ndata[l:][i] * ndata[:-l][i]
            for i in range(len(data) - l)]

        c = sum(tmp) / len(data) / var
        print(c)
        acorr[l] = c

plt.title("Autocorrelation Plot")
plt.xlabel("Lags")
plt.plot(acorr)
print("The Autocorrelation plot for the data is:")
plt.show()
```

## Output:
![Screenshot 2023-10-13 153128](https://github.com/s-adhithya/EX.NO-4-Compute-the-AutoCorrelation-Function-ACF-of-the-data-for-the-first-35-lags-/assets/113497423/f5e93903-6db1-49d6-a385-7795a64219a4)
![Screenshot 2023-10-13 153223](https://github.com/s-adhithya/EX.NO-4-Compute-the-AutoCorrelation-Function-ACF-of-the-data-for-the-first-35-lags-/assets/113497423/461b20bd-5e6a-4e4f-8094-24a9541ff80e)

## RESULT:
Thus we have successfully implemented the auto correlation function using above mentioned program.

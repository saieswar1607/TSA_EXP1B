# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
### Date: 05/03/2024

## AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
## ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
## PROGRAM:
### Regular Differencing
```
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
data=pd.read_csv("/content/AirPassengers.csv",parse_dates=['Month'],index_col='Month')
data.head()
passengers['shifted_value']=passengers['#Passengers'].shift(1)
passengers['difference_value']=passengers['#Passengers']-passengers['shifted_value']
passengers.dropna(inplace=True)
print(passengers)
passengers.plot(kind='line')
```

### Seasonal Adjustment
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose
data=pd.read_csv("/content/AirPassengers.csv",parse_dates=['Month'],index_col='Month')
passengers=pd.DataFrame(data)
result=seasonal_decompose(passengers['#Passengers'],model='additive',period=1)
seasonal=result.seasonal
passengers['Seasonal_value']=passengers['#Passengers']-seasonal
passengers.dropna(inplace=True)
print(passengers)
passengers.plot(kind='line')
```
### Log Transformation
```
import numpy as np
import pandas as pd
data= pd.read_csv('AirPassengers.csv')
data.head()
data.dropna(inplace=True)
x=data['Month']
y=data['#Passengers']
data_log=np.log(data['#Passengers'])
X=data['Month']
Y=data_log
import matplotlib.pyplot as plt
plt.plot(x,y)
plt.xlabel('Original Data')
plt.plot(X,Y)
plt.xlabel('Log- Transformed data')
```

## OUTPUT:

REGULAR DIFFERENCING:
![1](https://github.com/saieswar1607/TSA_EXP1B/assets/93427011/3af16d37-0cec-4715-af5e-c37e807ee819)



SEASONAL ADJUSTMENT:
![2](https://github.com/saieswar1607/TSA_EXP1B/assets/93427011/20a001e7-7129-429a-884f-3055b1d84c18)


LOG TRANSFORMATION:
![3](https://github.com/saieswar1607/TSA_EXP1B/assets/93427011/eba61afc-2f25-4b96-b3f6-364a1f7e790c)
![4](https://github.com/saieswar1607/TSA_EXP1B/assets/93427011/94942c8c-405b-40a0-8a53-28a1cbb71193)





## RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.

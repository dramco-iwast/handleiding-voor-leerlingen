---
layout: default
title: Data Manipulation in Python
parent: SP 5 Analyse meetresultaten
nav_order: 3
has_toc: true
---


## Read CSV File

```python
# Import pandas (if no module named pandas -> pip install pandas)
import pandas as pd 

# Read csv file 
sensor_data = pd.read_csv("iwast.csv") 

# Show the first 5 entries
print(sensor_data.head(5))
```

Result:

```
   Sensor ID  Motherboard ID Motherboard Name  ...               value                 timestamp unit
0          2               2            Marge  ...  20.939999999999998  2020-01-22T15:34:48.000Z   °C
1          2               2            Marge  ...                1035  2020-01-22T15:34:48.000Z  hPa
2          2               2            Marge  ...                 418  2020-01-22T15:34:48.000Z    -
3          2               2            Marge  ...               35.62  2020-01-22T15:34:48.000Z    %
4          2               2            Marge  ...  20.950000000000003  2020-01-22T15:35:51.000Z   °C

[5 rows x 7 columns]
```

## Filtering Data

```python
# replacing blank spaces with '_' because programming language do not like blank spaces!
sensor_data.columns =[column.replace(" ", "_") for column in sensor_data.columns] 

print(sensor_data.head(5))
  
# filter out data so we only keep the sensor dat coming from motherboard Marge with metric Temperature
marge_data = sensor_data.query('Motherboard_Name == "Marge" and metric=="Temperature"') 

print(marge_data.head(5))
```

Results:

```
   Sensor_ID  Motherboard_ID Motherboard_Name  ...               value                 timestamp unit
0          2               2            Marge  ...  20.939999999999998  2020-01-22T15:34:48.000Z   °C
1          2               2            Marge  ...                1035  2020-01-22T15:34:48.000Z  hPa
2          2               2            Marge  ...                 418  2020-01-22T15:34:48.000Z    -
3          2               2            Marge  ...               35.62  2020-01-22T15:34:48.000Z    %
4          2               2            Marge  ...  20.950000000000003  2020-01-22T15:35:51.000Z   °C

[5 rows x 7 columns]
```

```
    Sensor_ID  Motherboard_ID Motherboard_Name       metric               value                 timestamp unit
0           2               2            Marge  Temperature  20.939999999999998  2020-01-22T15:34:48.000Z   °C
4           2               2            Marge  Temperature  20.950000000000003  2020-01-22T15:35:51.000Z   °C
8           2               2            Marge  Temperature  20.939999999999998  2020-01-22T15:36:51.000Z   °C
12          2               2            Marge  Temperature  20.939999999999998  2020-01-22T15:37:59.000Z   °C
16          2               2            Marge  Temperature  20.939999999999998  2020-01-22T15:38:55.000Z   °C
```

## Plot Some Sensor Data
```python
import seaborn as sns; sns.set()
import matplotlib.pyplot as plt

# convert raw timestamps to datetime that pandas can understand
# raw: 2020-01-22T15:34:48.000Z
marge_data['timestamp'] =  pd.to_datetime(marge_data['timestamp'])
# ensure the values are interpreted as floats 
marge_data["value"] = marge_data["value"].astype(float)

# plot the temperature data and group based on the sensor_ID
ax = sns.scatterplot(x="timestamp", y="value", hue="Sensor_ID", data=marge_data)
plt.show()
```


## Compute Air Quality Index
```python
# Import pandas (if no module named pandas -> pip install pandas)
import pandas as pd 
import os

# ensure we are in the same path as our Python code
abspath = os.path.abspath(__file__)
dname = os.path.dirname(abspath)
os.chdir(dname)

# Read csv file 
sensor_data = pd.read_csv("iwast-aqi.csv") 


# replacing blank spaces with '_' because programmisng language do not like blank spaces!
sensor_data.columns =[column.replace(" ", "_") for column in sensor_data.columns] 

  
sensor_data['timestamp'] =  pd.to_datetime(sensor_data['timestamp'])
print(sensor_data.head(5))

# get out the temperature and humidity data
sensor_data_temp = sensor_data.query('metric=="Temperature"')
sensor_data_humidity = sensor_data.query('metric=="Humidity"') 

# Merge the two dataframes based on their timestamp
sensor_data_merged = pd.merge_asof(left=sensor_data_humidity, right=sensor_data_temp, on='timestamp', by="Motherboard_Name", direction="nearest", suffixes=("_humidity", "_temp"))
print(sensor_data_merged.head(5))

def compute_aqi(row):

    dataTemperature = row["value_temp"]*100
    dataHumidity = row["value_humidity"]*1000

    if ((dataTemperature) >= 2100):
        AQI_temp = ((50*(dataTemperature - 2100.0)/29)+50)/100
    else:
        AQI_temp = ((50*(2100.0 - dataTemperature)/41)+50)/100
    

    if ((dataHumidity) >= 40000):
        AQI_hum = ((5*(dataHumidity - 40000.0)/6)+500)/1000
    else:
        AQI_hum = ((5*(40000.0 - dataHumidity)/4)+500)/1000


    return AQI_temp + AQI_hum


# Use the function "compute_aqi" to compute the AQI per row with the definiation above
sensor_data_merged["AQI"] = sensor_data_merged.apply(compute_aqi, axis=1)     


print(sensor_data_merged.head(5))


import seaborn as sns; sns.set()
import matplotlib.pyplot as plt
ax = sns.lineplot(x="timestamp", y="AQI", hue="Motherboard_Name", data=sensor_data_merged)
plt.show()
```
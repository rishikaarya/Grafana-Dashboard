# WEATHER MONITORING FOR NAGPUR

### INTRODUCTION
The dataset includes weather data recorded over a specific period for Nagpur. Each entry includes the exact date and time of recording, capturing variations in meteorological parameters such as temperature, dew point, and humidity. This detailed timestamping allows for in-depth analysis of daily and seasonal weather patterns, helping to identify trends and anomalies over the observed period.

### DATASET: NAGPUR WEATHER DATASET
 
![image](https://github.com/user-attachments/assets/c3e22a6e-4903-4f3a-9d3a-ae8737cb0be9)

Number of rows: **10,497**

Number of columns: **19**

### VARIABLE DESCRIPTION
1. month: The month of the recorded data (string format).
2. time: The time of the recorded data (string format).
3. day/night: Indicates whether the data was recorded during the day or night (string format).
4. temperature: The temperature in degrees Fahrenheit (integer format).
5. condition: The weather condition (e.g., Cloudy, Haze) (string format).
6. dew_point: The dew point temperature in degrees Fahrenheit (integer format).
7. heat_index: The heat index in degrees Fahrenheit (integer format).
8. humidity_%: The humidity percentage (integer format).
9. pressure: The atmospheric pressure in inches of Mercury (Hg) (float format).
10. visibility: The visibility in miles (float format).
11. windchill: The wind chill temperature in degrees Fahrenheit (integer format).
12. Wind_direction: The direction of the wind in degrees (integer format).
13. gust: The wind gust speed in miles per hour (integer format).
14. wind_speed: The wind speed in miles per hour (integer format).
15. uv_desc: The description of the UV index (e.g., Low) (string format).
16. uv_index: The UV index (integer format).
17. clouds: The cloud cover description (e.g., OVC - Overcast, SCT - Scattered) (string format).
18. rain: A boolean indicating if it rained (True/False).
19. Rain_today: A string indicating if it rained today (Yes/No).

### GRAFANA DASHBOARD 

https://github.com/user-attachments/assets/80d07c43-77e8-49a8-87f3-e6ef200033b4

### CHARTS

1. How does humidity change over time?
   
   **Humidity Trends Over Time**
   
   <img width="614" alt="Screenshot 2024-12-06 at 10 27 22 AM" src="https://github.com/user-attachments/assets/dca8c3bf-eb41-4afb-8b6a-055f75129eda">
   
   **Query:** SELECT MEAN(HumidityPercentage) FROM data GROUP BY time(1m)
   
   **Observation:** Humidity levels fluctuate throughout the observed period but remain within a moderate range
   
   **Insights:** The humidity trends chart for Nagpur shows significant fluctuations within the observed hour, with notable peaks around 23:00 and 23:10, indicating periods of increased moisture. The frequent variability suggests dynamic weather conditions, potentially influenced by evening cooling or local meteorological events. Overall, the chart highlights the rapid changes in humidity, which could correlate with other weather parameters for deeper analysis.

2. How does the average heat index differ across various weather conditions?

   **Average Heat Index by Weather Condition**

   <img width="632" alt="Screenshot 2024-12-06 at 10 41 11 AM" src="https://github.com/user-attachments/assets/f509d185-8018-484a-8c09-4dfafcbb1212">


   **Query:** SELECT MEAN(HeatIndex) FROM data GROUP BY condition
   
   **Observation:** Cloudy conditions have an average heat index of 71.7, haze conditions rise to 86.3, and thunder conditions peak at 90.3, indicating increasing warmth and humidity.

   **Insights:** Severe weather conditions, like Thunder, are linked to higher heat indices, while cloudy weather has the lowest heat index due to less sunlight and lower humidity.

#Comparative Analysis of Air Quality in Major Cities

Authors: Aditya Vikram Bagaria (50479384) – abagaria@buffalo.edu, Avnish Surendra Rai (50488246) – avnishsu@buffalo.edu
________________________________________

#Task List

| ID | Task Description | Due Date | Status |
| --- | --- | --- | --- |
| 1 | Search APIs for online dynamic data | 2023-04-28 | DONE |
| 2 | Generate API key | 2023-04-28 | DONE |
| 3 | Prepare Project Proposal | 2023-05-08 | DONE |
| 4 | Retrieve the current AQI for each city | 2023-05-05 | DONE |
| 5 | Create a bar chart of the AQI values | 2023-05-05 | DONE |
| 6 | Retrieve the latitude and longitude for each city | 2023-05-05 | DONE |
| 7 | Plot the locations of the cities on a map using the Cartopy library | 2023-05-06 | DONE |
| 8 | Retrieve hourly air quality data for each city | 2023-05-06 | DONE |
| 9 | Create a time series plot of the AQI values for each city | 2023-05-07 | DONE |
| 10 | Create a correlation matrix plot for air quality parameter and AQI for each city | 2023-05-07 | DONE |
| 11 | Create a table of the time of the day with the highest and lowest AQI for each city | 2023-05-08 | DONE |
| 12 | Update this table with detailed list of tasks | 2023-05-08 | DONE |
| 13 | Create a pie chart for each city showing the distribution of air parameters to find the most prevalent parameter for each city. | 2023-05-09 | WIP |
| 14 | Create box plots for each city showing the distribution of AQI values over time | 2023-05-10 | WIP |
| 15 | Create a heat map for each city showing the AQI values over time | 2023-05-12 | WIP |
| 16 | Identifying which parameters are most strongly correlated with AQI | 2023-05-13 | WIP |
| 17 | Prepare the presentation and the report | 2023-05-15 | TBD |
| 18 | Complete YouTube video and upload to YouTube | 2023-05-16 | TBD |
| 19 | Upload README.md document to Github | 2023-05-17 | TBD |

________________________________________

#Introduction

The purpose of this project is to analyze and visualize air quality data for select cities and identifying the parameters that are most strongly correlated to AQI for each city.

What type of data are we using?
Air Quality Data for select cities are used for this project. Information on – 
1.	Air Quality Index 
2.	Hourly concentrations of air pollutants, including carbon monoxide, nitrogen dioxide, sulphur dioxide, and ozone 
3.	Geographical coordinates for each city

What are we doing with this data?
With this data, we are:
1.	Retrieving the current AQI for each city creating a bar chart of the AQI values.
2.	Retrieving the latitude and longitude for each city and plotting the locations of the cities on a map. 
3.	Retrieving hourly air quality data for each city and creating a time series plot of the AQI values for each city.
4.	Calculating the correlation between each air quality parameter and AQI for each city and creating a correlation matrix plot for each city.
5.	Creating a table of the time of day with the highest and lowest AQI for each city.
6.	Create a pie chart for each city showing the distribution of air parameters to find the most prevalent parameter for each city.
7.	Create box plots for each city showing the distribution of AQI values over time.
8.	Create a heat map for each city showing the AQI values over time.
9.	Identifying which parameters are most strongly correlated with AQI for each city.

What types of analysis you're conducting?
1.	Descriptive analysis - We are using descriptive statistics, to summarize the air quality data for each city.
2.	Comparative analysis - We are comparing air quality data across multiple cities to identify differences and similarities in air quality trends and correlations.
3.	Correlation analysis - We are calculating the correlation between each air quality parameter and AQI for each city to examine the relationship between these variables.
4.	Time series analysis - We are using time series plots to examine air quality trends over time, including hourly changes in AQI values for each city.
5.	Spatial analysis - We are using maps to visualize the geographic distribution of air quality data across different cities.

________________________________________

#References

•	Source code was adapted here - https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbFVVenMyaWhNcWJqWVZ2OWZNOXQzSEgyaEJzQXxBQ3Jtc0ttcWZwOUNCUFlxQm1BNi1hT3N1dEJhSWpDWkozSWV1ck0wV2p3aTNpU2tqbGJkaFN5VXRfUzF2emZiOTlEVUtUM05zOE8wYWVtRGo5TnlnR3U2T0pBaW1hWG8tYTloVDZkLUVOMlpGVFQ2eVZvNGI2VQ&q=https%3A%2F%2Fcolab.research.google.com%2Fdrive%2F1RCOkeSOWUKv-89h-wBuBc3SFajVs6DCP&v=PVW79cb6ZWo 

•	The code retrieves data from 
-	https://open-meteo.com/en
-	https://aqicn.org/api/
________________________________________

#Requirements

Python packages and libraries used: requests, pandas, matplotlib.pyplot and seaborn
•	APIs: 
-	http://api.waqi.info/feed/sydney/?token=504cf1362a47fda9e822768d19af839b22fee4ab
-	https://air-quality-api.open-meteo.com/v1/air-quality?latitude=51.5074&longitude=-0.1278&hourly=carbon_monoxide,nitrogen_dioxide,sulphur_dioxide,ozone,us_aqi
•	API key: 504cf1362a47fda9e822768d19af839b22fee4ab
________________________________________

#Motivation

The main purpose behind this project is to raise awareness about air quality issues in select cities around the world. The project will use visualization tools to demonstrate the severity of air pollution in different parts of the world and attention to the need for air quality management and public health interventions.
•	API key: 504cf1362a47fda9e822768d19af839b22fee4ab
________________________________________

#Explanation of the Code
1. The code, Skylines_and_Smog.py, begins by importing necessary Python packages:
•	import requests
•	import pandas as pd
•	import matplotlib.pyplot as plt
•	import seaborn as sns
•	import cartopy.crs as ccrs
Note: To install an unavailable library, run the code - conda install <library_name>

2. We then import data from ‘Open Metro’ api and ‘waqi’ api. We print the data to allow us to verify what we've imported:
# view data in a tabular manner
url = "https://air-quality-api.open-meteo.com/v1/air-quality"
params = {"latitude": 51.5074, "longitude": -0.1278, "hourly": "us_aqi"}
response = requests.get(url, params=params)
# Convert the response JSON to a Pandas DataFrame
data = pd.DataFrame(response.json()["hourly"])
# Display the data as a table
print(data)
# Make a request to the WAQI API endpoint
url = "http://api.waqi.info/feed/sydney/?token=504cf1362a47fda9e822768d19af839b22fee4ab"
response = requests.get(url)
# Convert the response JSON to a Pandas DataFrame
data = pd.DataFrame(response.json()["data"]["iaqi"])
# Display the data as a table
print(data)
Output:
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/00dfff4c-1f81-4c05-aa62-ee81a68e3890)
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/23ae7761-f9ce-47fd-9e55-49f716aef143)

3.	We then create a list of selected cities and a list of AQI values for each city in the cities list:
# Define a list of cities and the API key
cities = ['mumbai', 'london', 'new york', 'beijing', 'sydney']
api_key = '504cf1362a47fda9e822768d19af839b22fee4ab'
# Create an empty list to store the AQI for each city
aqi_list = []
# Loop over each city and make an API call
for city in cities:
    url = f'http://api.waqi.info/feed/{city}/?token={api_key}'
    response = requests.get(url)
    data = response.json()['data']
    aqi = data['aqi']
    aqi_list.append(aqi)

4.	Finally, we visualize the data – generating a comparison of live AQI data between selected cities. We save our plot as ‘AQI bar chart.png’:
# Create a bar chart of the AQI for each city
plt.bar(cities, aqi_list)
plt.title('Air Quality Index for Selected Cities')
plt.xlabel('City')
plt.ylabel('AQI')
plt.savefig('AQI bar chart.png')
plt.show()
Output:
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/54758e41-9dcf-4435-a20f-372bf128ee78)


5.	We then visualize the live data by plotting the locations and the respective AQIs on the world map. We save this plot as ‘AQI plot.png’:
# Create a figure and axis object using PlateCarree projection
fig = plt.figure(figsize=(10, 8))
ax = plt.axes(projection=ccrs.PlateCarree())
# Add stock imagery to the axis
ax.stock_img()
# Loop over each city and make an API call
for city in cities:
    url = f'http://api.waqi.info/feed/{city}/?token={api_key}'
    response = requests.get(url)
    data = response.json()['data']
    geo = data['city']['geo']
    aqi = data['aqi']
    
    # Plot a scatter point for the city's location and add a label with the AQI value
    plt.scatter(geo[1], geo[0], color='blue', transform=ccrs.PlateCarree())
    plt.text(geo[1] + 3, geo[0] - 2, f'{city} AQI\n     {aqi}', color='red', transform=ccrs.PlateCarree())
# Set the title and show the plot
plt.title('Air Quality Index for Selected Cities')
plt.savefig('AQI map.png')
plt.show()
Output:
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/8b3481e0-6292-4430-ba5e-a899a0018d26)

6.	We then proceed to gather the historical data and retrieve the data for each city:
# Define the API URLs and parameters for the five cities
london_url = 'https://air-quality-api.open-meteo.com/v1/air-quality?latitude=51.5074&longitude=-0.1278&hourly=carbon_monoxide,nitrogen_dioxide,sulphur_dioxide,ozone,us_aqi'
new_york_url = 'https://air-quality-api.open-meteo.com/v1/air-quality?latitude=40.7128&longitude=-74.0060&hourly=carbon_monoxide,nitrogen_dioxide,sulphur_dioxide,ozone,us_aqi'
mumbai_url = 'https://air-quality-api.open-meteo.com/v1/air-quality?latitude=19.07&longitude=72.88&hourly=carbon_monoxide,nitrogen_dioxide,sulphur_dioxide,ozone,us_aqi'
beijing_url = 'https://air-quality-api.open-meteo.com/v1/air-quality?latitude=39.9042&longitude=116.4074&hourly=carbon_monoxide,nitrogen_dioxide,sulphur_dioxide,ozone,us_aqi'
sydney_url = 'https://air-quality-api.open-meteo.com/v1/air-quality?latitude=-33.8688&longitude=151.2093&hourly=carbon_monoxide,nitrogen_dioxide,sulphur_dioxide,ozone,us_aqi'

# Define a dictionary of city names and their respective API URLs
cities = {
    'London': {'url': london_url},
    'New York': {'url': new_york_url},
    'Mumbai': {'url': mumbai_url},
    'Beijing': {'url': beijing_url},
    'Sydney': {'url': sydney_url}
}

# Retrieve the data for each city using the API
for city in cities.keys():
    response = requests.get(cities[city]['url'])
    data = response.json()
    df = pd.DataFrame(data['hourly'])
    df['time'] = pd.to_datetime(df['time'])
    df = df.set_index('time')
    cities[city]['data'] = df
    cities[city]['aqi_data'] = df['us_aqi']

7.	We then compare and visualize the historical AQI data of the five city over different time in a day and for a line chart of the comparison. We save our plot as ‘AQI comparison.png’:
# Plot the AQI data for all five cities on the same chart
fig, ax = plt.subplots(figsize=(10, 8))

for city in cities.keys():
    ax.plot(cities[city]['aqi_data'], label=city)

ax.set_title('Hourly AQI for Selected Cities')
ax.set_xlabel('Time')
ax.set_ylabel('AQI')
ax.legend()
plt.savefig('AQI comparison.png')
plt.show()
Output:
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/1cc7e1d7-f3b2-4951-a28f-84e67180fcd4)

8.	We then proceed to visualize the correlation between different parameters and the aqi, for individual city by plotting a heat map of the correlation. We save our plots as a ‘{city}_correlation_matrix.png’:
# Calculate the correlation between each air quality parameter and AQI for each city
for city in cities.keys():
    df = cities[city]['data']
    corr = df[['carbon_monoxide', 'nitrogen_dioxide', 'sulphur_dioxide', 'ozone', 'us_aqi']].corr()
    cities[city]['corr'] = corr

# Plot the correlation matrices for each city
for city in cities.keys():
    corr = cities[city]['corr']
    sns.heatmap(corr, annot=True, cmap='coolwarm')
    plt.title(f'Correlation Matrix for {city}')
    plt.savefig(f'{city}_correlation_matrix.png')
    plt.show()
 
 Output:
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/ba5771d9-5406-4d42-9111-e4fed7cbef3d)
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/0d013162-3b08-40f8-91eb-784fd9c83d90)
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/2fd7b377-24b1-4f2e-9fd6-999209e4bd72)
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/267ae8c0-ec28-423f-bb06-9dcd825531af)
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/2fa407f2-709f-47d9-8fae-2fe7f6412c06)
 
9.	We then generate a table to show the time of the day with the highest and the lowest AQI, for each city. 
# Create a table of the time of the day with the highest and lowest AQI for each city
table_data = []
for city in cities.keys():
    df = cities[city]['data']
    max_aqi_time = df['us_aqi'].idxmax().strftime('%H:%M')
    min_aqi_time = df['us_aqi'].idxmin().strftime('%H:%M')
    max_aqi = df['us_aqi'].max()
    min_aqi = df['us_aqi'].min()
    table_data.append([city, max_aqi_time, max_aqi, min_aqi_time, min_aqi])

table = pd.DataFrame(table_data, columns=['City', 'Time', 'Max AQI', 'Time', 'Min AQI'])
print(table)
Output:
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/6935fceb-dd59-4085-a30f-853f3b93b27b)

10.	We then proceed to create a box plot for each city to study AQI distribution over time. We save our plots as '{city}_AQI box plot.png’:
# Create a box plot for each city
for city in cities.keys():
    df = cities[city]['data']
    sns.boxplot(x=df.index.hour, y=df['us_aqi'])
    plt.title(f'AQI Distribution over Time for {city}')
    plt.xlabel('Hour of the Day')
    plt.ylabel('AQI')
    plt.savefig(f'{city}_AQI box plot.png')
    plt.show()
 Output:
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/144967c4-8499-4f64-bbe1-1e11c5ae8c90)
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/b50f8c43-f05e-40ca-8ac6-dd40e7755491)
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/2e81cb15-3df0-4474-9b5b-668b5fbc0fe4)
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/827a9b02-62a7-4ebf-969d-5615756fbb5a)
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/67c427bd-d12c-4dab-a8c5-dec7097dd4d0)
 
11.	We then generate the heat map to compare AQI data for each city in the last 24 hours. We save the plot as 'AQI heatmap.png’:
# Create a DataFrame to hold the hourly AQI values for each city
df_hourly = pd.DataFrame(columns=cities.keys())

# Fill in the DataFrame with hourly AQI values for each city
for city in cities.keys():
    hourly_data = cities[city]['data'].resample('H').mean()
    df_hourly[city] = hourly_data['us_aqi'].tail(24).reset_index(drop=True)

# Create the heatmap
ax = sns.heatmap(df_hourly, cmap='coolwarm')
plt.title('AQI Heatmap over Time for Each City')
plt.xlabel('City')
plt.ylabel('Hour of the Day')
plt.savefig('AQI heatmap.png')
plt.show()
Output:
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/08e3d425-33b0-4076-a613-43f21efda58b)

12.	Finally, we generate a pie chart plot for each city to view the individual parameters and their percentage in the air for that city. We save our plots as '{city}_AQI parameters.png’:
# Make pie chart for Air Quality Parameters for each city
parameters = ['carbon_monoxide', 'nitrogen_dioxide', 'sulphur_dioxide', 'ozone']

for city in cities.keys():
    data = cities[city]['data'][parameters].mean()
    plt.pie(data, labels=parameters, autopct='%1.1f%%')
    plt.title(f'Average Air Quality Parameters\nfor {city}')
    plt.savefig(f'{city}_AQI parameters.png')
Output:
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/e4a6dc95-e645-481f-8fc1-3e46cd1c2f6e)
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/c2154ee9-4abd-41af-a656-42e12eeee4a3)
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/6ae0713b-d9e9-4425-b98a-2480fb924b9a)
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/68bfafac-5dea-49fb-ad22-cd13b010b348)
![image](https://github.com/IE-555/final-project-avnish-rai/assets/124153815/0a6c0d53-60c3-42f5-b9b3-f9d85469577e)

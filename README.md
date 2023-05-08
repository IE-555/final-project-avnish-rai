Comparative Analysis of Air Quality in Major Cities
Authors: Aditya Vikram Bagaria (50479384) – abagaria@buffalo.edu, Avnish Surendra Rai (50488246) – avnishsu@buffalo.edu
________________________________________

Task List
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

Introduction
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

References
•	Source code was adapted here 
•	The code retrieves data from 
-	https://open-meteo.com/en
-	https://aqicn.org/api/
________________________________________

Requirements
Python packages and libraries used: requests, pandas, matplotlib.pyplot and seaborn
•	APIs: 
-	http://api.waqi.info/feed/sydney/?token=504cf1362a47fda9e822768d19af839b22fee4ab
-	https://air-quality-api.open-meteo.com/v1/air-quality?latitude=51.5074&longitude=-0.1278&hourly=carbon_monoxide,nitrogen_dioxide,sulphur_dioxide,ozone,us_aqi
•	API key: 504cf1362a47fda9e822768d19af839b22fee4ab
________________________________________

Motivation
The main purpose behind this project is to raise awareness about air quality issues in select cities around the world. The project will use visualization tools to demonstrate the severity of air pollution in different parts of the world and attention to the need for air quality management and public health interventions.

**PROJECT SUMMARY**


This project focuses on analyzing COVID-19 data spanning from March 2020 to September 2021 to understand the pandemic's impact on various regions and demographic groups. By examining trends in infection rates, mortality rates, and vaccination rates over time, key patterns and insights will be identified to inform public health strategies and interventions. Through this analysis, stakeholders can gain valuable insights into the progression of the pandemic, assess the effectiveness of mitigation measures, and prioritize resources for future response efforts.



**QUESTIONS TO ANSWER**

1. What is the global death percentage?
2. What is the total death count per continent?
3. What is the percentage of population infected per country?
4. What is the monthly infection rate per country?



**DATA SOURCE**


I will conduct an analysis using COVID-19 data extracted from March 2020 to September 2021, accessible for download via https://ourworldindata.org/covid-deaths.



**DATA EXPLORATION**


Before cleaning the data, I am familiarizing myself with the data to find any inconsistencies

*Observations*:


The data set has 27 columns but this analysis is only going to focus on nine columns, country_name', 'continent', 'location', 'date', 'total_cases', 'new_cases', 'total_deaths', 'new_deaths', and 'population'.

The table CovidDeaths has 85,171 from March 2020 to March 2021


| Total_data |
|------------|
| 85171      |

The provided table displays data with null values across various columns, including 'country_name', 'continent', 'location', 'date', 'total_cases', 'new_cases', 'total_deaths', 'new_deaths', and 'population'. These zeros indicate missing or unavailable information for the corresponding records.


![Screenshot (198)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/0e4a3f25-1bb9-4175-8457-bf0a5d9fafaa)



**DATA ANALYSIS**


I queried the data for analysis using SQL and visualized the findings using Tableau.
The analysis question is,


*What is the global death percentage?*


![Screenshot (199)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/e65f5bbe-6359-411c-b20a-7a083d1eb608)

The provided data summarizes the global impact of COVID-19, indicating a total of 150,574,977 reported cases and 3,180,206 recorded deaths. The calculated death percentage is approximately 2.11%, derived from the ratio of total deaths to total cases, demonstrating the severity of the pandemic's health outcomes. This data underscores the significance of continued efforts to mitigate the spread of the virus and improve healthcare measures worldwide.


Next, the *total death count per continent* was examined.


![Screenshot (201)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/bf4359ef-6912-4ecd-81c4-eea4d8b7d92a)


The provided data offers a breakdown of total death counts attributed to COVID-19 across continents:


![Screenshot (204)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/29a088af-f327-454d-9380-edebf5181823)



**Europe**: The continent has reported the highest total death count of 1,016,750, indicating a significant impact of the pandemic on the region's population.

**North America**: Following closely, North America has reported 847,942 total deaths, highlighting the substantial toll of the virus on countries within the continent.

**South America**: South America has recorded 672,415 total deaths, underscoring the widespread impact of COVID-19 across the continent.

**Asia**: With 520,269 total deaths, Asia has also experienced significant mortality rates due to the pandemic, although varying considerably across different countries within the region.

**Africa**: The continent has reported 121,784 total deaths, indicating comparatively lower mortality rates but still facing challenges in managing the pandemic's impact on healthcare 
systems.

**Oceania**: Oceania has reported the lowest total death count of 1,046, reflecting relatively successful containment measures implemented by countries within the region.



Thirdly, the *percentage of infection per country* was analyzed.



![Screenshot (202)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/b4db941d-5123-451b-ac86-1392d08055e4)


The provided data offers insights into the COVID-19 impact on various countries, including their highest infection counts, percent population infected, and total population.


*Key observations*:


- Countries like Andorra, Montenegro, and Czechia have experienced relatively high infection rates, with percentages of the population infected surpassing 15%.
Larger nations such as the United States, Brazil, and India, while having high absolute infection counts, exhibit lower percentages of the population infected, likely due to their large population sizes.

- Larger populations, such as India, Indonesia, and Pakistan, have substantial absolute numbers of cases despite lower infection rates per capita.

This summary underscores the diverse impact of COVID-19 on different countries, influenced by factors such as population density, healthcare infrastructure, and public health measures implemented.


Lastly, I analyzed the *monthly infection rate per country* focusing on the United States, United Kingdom, China, India and Mexico.


![Screenshot (203)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/a4bb7761-c0a0-4e5c-b251-9c450978127f)



**United Kingdom (UK)**:

The UK has experienced a fluctuating infection rate over the months, with a peak in January 2021, followed by a gradual decline. However, infections have remained relatively high compared to earlier months.

**United States (US)**:

The US has consistently reported high infection rates throughout the pandemic, with notable spikes in December 2020 and January 2021. While there have been fluctuations, infections have remained at a significant level over time.

**Mexico**:

Mexico's infection rate has also fluctuated, with peaks observed in January and July 2021. Despite fluctuations, infections have remained relatively high, indicating ongoing challenges in controlling the spread of the virus.

**India**:

India experienced a devastating surge in infections around April and May 2021, reaching unprecedented levels. Subsequent months have shown a decline in infection rates, although they remain relatively high compared to earlier periods.

**China**:

China's infection rate has remained relatively low compared to other countries, with occasional small spikes observed. Stringent containment measures implemented by the Chinese government have likely contributed to the comparatively lower infection rates.



**DASHBOARD**

![Screenshot (205)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/a7aa742d-6100-4798-970f-871ce6347c1a)


- **Global Numbers**: 
As of March 2021, there was a total of 150,574,977 confirmed cases of COVID-19 reported worldwide, and 3,180,206 deaths. This means that 2.11% of the world's population had been infected with the virus.

- **Percent Of Population Infected Per Country**: 
The map on the right-hand side of the dashboard shows the percentage of people infected with COVID-19 in each country. The countries are color-coded according to the percentage of their population that has been infected, with darker colors indicating a higher percentage of infection.

- **Total Death Count Per Continent**: 
The bar chart on the left-hand side of the dashboard shows the total number of deaths from COVID-19 in each continent. The continents are listed from lowest to highest death toll.

- **Percent Population Infected Per Month**:
The line graph at the bottom of the dashboard shows the percentage of the population infected with COVID-19 over time. The graph shows data for five countries: the United States, the United Kingdom, Mexico, China, and India, and their infection estimates for the next 6 months.


It is important to note that the data on this dashboard is based on reported cases, and the actual number of cases may be higher. Additionally, the data may not be representative of all countries, as some countries may have better testing and reporting systems than others.



**CONCLUSION**


In conclusion, the provided data offers valuable insights into the global impact of the COVID-19 pandemic, highlighting significant variations in infection rates and mortality across countries and continents. 

Analysis of the data reveals that certain regions, such as Europe and North America, have borne the brunt of the pandemic, reporting high infection and death counts. Conversely, countries like China have managed to maintain relatively lower infection rates through stringent containment measures.

Despite varying levels of success in controlling the virus, the data underscores the need for continued vigilance, international cooperation, and robust public health measures to mitigate the spread of COVID-19 and minimize its adverse effects on global health and economies.


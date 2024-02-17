PROJECT SUMMARY

This project focuses on analyzing COVID-19 data spanning from March 2020 to September 2021 to understand the pandemic's impact on various regions and demographic groups. By examining trends in infection rates, mortality rates, and vaccination rates over time, key patterns and insights will be identified to inform public health strategies and interventions. Through this analysis, stakeholders can gain valuable insights into the progression of the pandemic, assess the effectiveness of mitigation measures, and prioritize resources for future response efforts.


QUESTIONS TO ANSWER

1. What is the global death percentage?
2. What is the total death count per continent?
3. What is the percentage of population infected per country?
4. What is the monthly infection rate per country?


DATA SOURCE

I will conduct an analysis using COVID-19 data extracted from March 2020 to September 2021, accessible for download via https://ourworldindata.org/covid-deaths.

DATA EXPLORATION

Before cleaning the data, I am familiarizing myself with the data to find any inconsistencies

Observations:

The data set has 27 columns but this analysis is only going to focus on nine columns, country_name', 'continent', 'location', 'date', 'total_cases', 'new_cases', 'total_deaths', 'new_deaths', and 'population'.

The table CovidDeaths has 85,171 from March 2020 to September 2021

| Total_data |
|------------|
| 85171      |

The provided table displays data with null values across various columns, including 'country_name', 'continent', 'location', 'date', 'total_cases', 'new_cases', 'total_deaths', 'new_deaths', and 'population'. These zeros indicate missing or unavailable information for the corresponding records.

![Screenshot (198)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/0e4a3f25-1bb9-4175-8457-bf0a5d9fafaa)


DATA ANALYSIS

I queried the data for analysis using SQL and visualized the findings using Tableau.
The analysis question is,

What is the global death percentage?

![Screenshot (199)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/e65f5bbe-6359-411c-b20a-7a083d1eb608)

The provided data summarizes the global impact of COVID-19, indicating a total of 150,574,977 reported cases and 3,180,206 recorded deaths. The calculated death percentage is approximately 2.11%, derived from the ratio of total deaths to total cases, demonstrating the severity of the pandemic's health outcomes. This data underscores the significance of continued efforts to mitigate the spread of the virus and improve healthcare measures worldwide.

Next, the total death count per continent was examined.

![Screenshot (201)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/bf4359ef-6912-4ecd-81c4-eea4d8b7d92a)

The provided data offers a breakdown of total death counts attributed to COVID-19 across continents:

Europe: The continent has reported the highest total death count of 1,016,750, indicating a significant impact of the pandemic on the region's population.
North America: Following closely, North America has reported 847,942 total deaths, highlighting the substantial toll of the virus on countries within the continent.
South America: South America has recorded 672,415 total deaths, underscoring the widespread impact of COVID-19 across the continent.
Asia: With 520,269 total deaths, Asia has also experienced significant mortality rates due to the pandemic, although varying considerably across different countries within the region.
Africa: The continent has reported 121,784 total deaths, indicating comparatively lower mortality rates but still facing challenges in managing the pandemic's impact on healthcare systems.
Oceania: Oceania has reported the lowest total death count of 1,046, reflecting relatively successful containment measures implemented by countries within the region.

Thirdly, the percentage of infection per country was analyzed.


![Screenshot (202)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/b4db941d-5123-451b-ac86-1392d08055e4)

The provided data offers insights into the COVID-19 impact on various countries, including their highest infection counts, percent population infected, and total population.

Key observations:

Countries like Andorra, Montenegro, and Czechia have experienced relatively high infection rates, with percentages of the population infected surpassing 15%.
Larger nations such as the United States, Brazil, and India, while having high absolute infection counts, exhibit lower percentages of the population infected, likely due to their large population sizes.
Larger populations, such as India, Indonesia, and Pakistan, have substantial absolute numbers of cases despite lower infection rates per capita.

This summary underscores the diverse impact of COVID-19 on different countries, influenced by factors such as population density, healthcare infrastructure, and public health measures implemented.

Lastly, I analyzed the monthly infection rate per country.


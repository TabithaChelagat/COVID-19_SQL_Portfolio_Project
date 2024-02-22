**PROJECT SUMMARY**


This project focuses on analyzing COVID-19 data spanning from March 2020 to September 2021 to understand the pandemic's impact on various regions and demographic groups. By examining trends in infection rates, mortality rates, and vaccination rates over time, key patterns and insights will be identified to inform public health strategies and interventions. Through this analysis, stakeholders can gain valuable insights into the progression of the pandemic, assess the effectiveness of mitigation measures, and prioritize resources for future response efforts.



**QUESTIONS TO ANSWER**

1. What is the global death percentage?
2. What is the maximum total death count per continent?
3. What is the highest percentage of population infected per country?
4. What is the monthly infection rate per country?



**DATA SOURCE**


I will conduct an analysis using COVID-19 data extracted from March 2020 to September 2021, accessible for download via https://ourworldindata.org/covid-deaths.



**DATA EXPLORATION**


Before cleaning the data, I am familiarizing myself with the data to find any inconsistencies

***Observations***

- *Columns*

The data set has ``27 columns`` but this analysis is only going to focus on nine columns,

| Column Name   | Description                          |
|---------------|--------------------------------------|
| country_name  | Name of the country                  |
| continent     | Continent where the country is located|
| location      | Location within the country          |
| date          | Date of the recorded data            |
| total_cases   | Total number of confirmed cases      |
| new_cases     | Number of new confirmed cases        |
| total_deaths  | Total number of confirmed deaths     |
| new_deaths    | Number of new confirmed deaths       |
| population    | Total population of the country      |


- *Total data*

With the iso_code as the primary key, this code counts the total number of rows in the dataset. 

```
Select COUNT(iso_code) as Total_data
From PortfolioProject..CovidDeaths
```

| Total_data |
|------------|
| 85171      |

The table CovidDeaths has ``85,171`` data entries from March 2020 to March 2021

- *Checking for nulls*

In this code, ```COUNT(*)``` returns the total number of rows in the table while ```COUNT(column_name)``` returns the number of non-NULL values in each respective column.
Subtracting COUNT(*) from COUNT(column_name) effectively counts the number of NULL values in each column.

```
Select COUNT(*)-COUNT(continent) as continent,
COUNT(*)-COUNT(iso_code) as country_abrv,
COUNT(*)-COUNT(location) as location,
COUNT(*)-COUNT(date) as date,
COUNT(*)-COUNT(total_cases) as total_cases,
COUNT(*)-COUNT(new_cases) as new_cases,
COUNT(*)-COUNT(total_deaths) as total_deaths,
COUNT(*)-COUNT(new_deaths) as new_deaths,
COUNT(*)-COUNT(population) as population
From PortfolioProject..CovidDeaths
```

The provided table displays data with null values across various columns, including 'country_name', 'continent', 'location', 'date', 'total_cases', 'new_cases', 'total_deaths', 'new_deaths', and 'population'. These zeros indicate missing or unavailable information for the corresponding records.

![Screenshot (198)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/0e4a3f25-1bb9-4175-8457-bf0a5d9fafaa)


These null values will be excluded when doing our analysis.


**DATA ANALYSIS**


I queried the data for analysis using ``SQL`` and visualized the findings using ```Tableau```.

The analysis question is,


***1. What is the global death percentage?***

The code aggregates data from the CovidDeaths table, calculates the ```total number of cases and deaths```, computes the ```death percentage```, and filters the results to exclude records with null continent values, finally presenting the result set ordered by total cases and total deaths.

```
Select SUM(new_cases) as total_cases, SUM(cast(new_deaths as int)) as total_deaths, SUM(cast(new_deaths as int))/SUM(New_Cases)*100 as DeathPercentage
From CovidDeaths$
where continent is not null 
order by 1,2
```


| Total_cases | Total_deaths | DeathPercentage |
|-------------|--------------|-----------------|
| 150,574,977 | 3,180,206    | 2.11%           |



*Summary of findings*

- The provided data summarizes the global impact of COVID-19, indicating a total of ``150,574,977`` reported cases and ``3,180,206`` recorded deaths.

- The calculated death percentage is approximately ``2.11%``, derived from the ratio of total deaths to total cases, demonstrating the severity of the pandemic's health outcomes.

- This data underscores the significance of continued efforts to mitigate the spread of the virus and improve healthcare measures worldwide.


***2. Maximum total death count per continent***

This query retrieves the ```maximum total death``` count for each ```continent``` from the table "CovidDeaths", excludes null values, groups the data by continent, and lists the results in descending order.

```
Select continent, MAX(cast(Total_deaths as int)) as TotalDeathCount
From CovidDeaths$
Where continent is not null 
Group by continent
order by TotalDeathCount desc

```
The provided data offers a breakdown of ```total death counts``` attributed to COVID-19 across continents.

![Screenshot (200)](https://github.com/TabithaChelagat/COVID-19_SQL_Portfolio_Project/assets/112205355/c56f5c00-3f53-43e5-80d7-cab5bd80bdcc)


![Screenshot (204)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/29a088af-f327-454d-9380-edebf5181823)


*Summary of findings*

**Europe**: The continent has reported the highest total death count of ``1,016,750``, indicating a significant impact of the pandemic on the region's population.

**North America**: Following closely, North America has reported ``847,942`` total deaths, highlighting the substantial toll of the virus on countries within the continent.

**South America**: South America has recorded ``672,415`` total deaths, underscoring the widespread impact of COVID-19 across the continent.

**Asia**: With ``520,269`` total deaths, Asia has also experienced significant mortality rates due to the pandemic, although varying considerably across different countries within the region.

**Africa**: The continent has reported ``121,784`` total deaths, indicating comparatively lower mortality rates but still facing challenges in managing the pandemic's impact on healthcare 
systems.

**Oceania**: Oceania has reported the lowest total death count of ``1,046``, reflecting relatively successful containment measures implemented by countries within the region.



***3. Highest percentage of infection rate per country***

This SQL query retrieves the top 8 ```locations``` (the whole data was too large to be included in this analysis) with their corresponding populations, ```maximum total cases``` recorded, and the ```percentage of the population infected```.

It groups the data by location and population, calculates the maximum total cases for each group, and then calculates the percentage of the population infected based on the maximum total cases and population. 

Finally, it orders the result set by the percentage of the population infected in descending order to display the locations with the highest percentage of the population infected at the top.

```
Select top 8 Location, Population, MAX(total_cases) as HighestInfectionCount,  Max((total_cases/population))*100 as PercentPopulationInfected
From CovidDeaths$
Group by Location, Population
order by PercentPopulationInfected desc
```

| Location   | Population | HighestInfectionCount | PercentPopulationInfected |
|------------|------------|-----------------------|---------------------------|
| Andorra    | 77,265     | 13,232                | 17.13%                    |
| Montenegro | 628,062    | 97,389                | 15.51%                    |
| Czechia    | 10,708,982 | 1,630,758             | 15.23%                    |
| San Marino | 33,938     | 5,066                 | 14.93%                    |
| Slovenia   | 2,078,932  | 240,292               | 11.56%                    |
| Luxembourg | 625,976    | 67,205                | 10.74%                    |
| Bahrain    | 1,701,583  | 176,934               | 10.40%                    |
| Serbia     | 6,804,596  | 689,557               | 10.13%                    |


![Screenshot (202)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/b4db941d-5123-451b-ac86-1392d08055e4)


*Summary of findings*


- Countries like Andorra, Montenegro, and Czechia have experienced relatively high infection rates, with percentages of the population infected surpassing 15%.
  
- Larger nations such as the United States, Brazil, and India, while having high absolute infection counts, exhibit lower percentages of the population infected, likely due to their large population sizes.

- Larger populations, such as India, Indonesia, and Pakistan, have substantial absolute numbers of cases despite lower infection rates per capita.

- This summary underscores the diverse impact of COVID-19 on different countries, influenced by factors such as population density, healthcare infrastructure, and public health measures implemented.


***4. Monthly infection rate per country*** - *Focusing on the United States, United Kingdom, China, India and Mexico*

This SQL query retrieves data from the CovidDeaths table, selecting the ``Location, date, Population, and total_cases```, and calculates the ```PercentPopulationInfected``` by dividing total_cases by Population and multiplying by 100. 

The Order by 1,2 sorts the result set by the first and second columns, which are Location and date respectively. 

Additionally, Tableau was utilized to extract the month from the date column for analysis and visualization purposes.

```
Select Location, date, Population, total_cases,  (total_cases/population)*100 as PercentPopulationInfected
From CovidDeaths$
Order by 1,2

```

![Screenshot (203)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/a4bb7761-c0a0-4e5c-b251-9c450978127f)

*Summary of findings*

In this analysis, I focused on the United Kingdom, the United States, Mexico, India, and China.

- *United Kingdom (UK)*

The UK has experienced a fluctuating infection rate over the months, with a peak in January 2021, followed by a gradual decline. However, infections have remained relatively high compared to earlier months.

- *United States (US)*

The US has consistently reported high infection rates throughout the pandemic, with notable spikes in December 2020 and January 2021. While there have been fluctuations, infections have remained at a significant level over time.

- *Mexico*

Mexico's infection rate has also fluctuated, with peaks observed in January and July 2021. Despite fluctuations, infections have remained relatively high, indicating ongoing challenges in controlling the spread of the virus.

- *India*

India experienced a devastating surge in infections around April and May 2021, reaching unprecedented levels. Subsequent months have shown a decline in infection rates, although they remain relatively high compared to earlier periods.

- *China*

China's infection rate has remained relatively low compared to other countries, with occasional small spikes observed. Stringent containment measures implemented by the Chinese government have likely contributed to the comparatively lower infection rates.



**DASHBOARD**

![Screenshot (205)](https://github.com/tabby1307/COVID-19_Portfolio_Project/assets/112205355/a7aa742d-6100-4798-970f-871ce6347c1a)


- ***Global Numbers***
  
As of March 2021, there was a total of ``150,574,977`` confirmed cases of COVID-19 reported worldwide, and ``3,180,206`` deaths. This means that ``2.11%`` of the world's population had been infected with the virus.

- ***Percent Of Population Infected Per Country***
  
The map on the right-hand side of the dashboard shows the percentage of people infected with COVID-19 in each country. The countries are color-coded according to the percentage of their population that has been infected, with darker colors indicating a higher percentage of infection.

- ***Total Death Count Per Continent***

The bar chart on the left-hand side of the dashboard shows the total number of deaths from COVID-19 in each continent. The continents are listed from lowest to highest death toll.

- ***Percent Population Infected Per Month***
  
The line graph at the bottom of the dashboard shows the percentage of the population infected with COVID-19 over time. The graph shows data for five countries: the United States, the United Kingdom, Mexico, China, and India, and their infection estimates for the next 6 months.


It is important to note that the data on this dashboard is based on reported cases, and the actual number of cases may be higher. Additionally, the data may not be representative of all countries, as some countries may have better testing and reporting systems than others.



**CONCLUSION**


- The provided data offers valuable insights into the global impact of the COVID-19 pandemic, highlighting significant variations in infection rates and mortality across countries and continents. 

- Analysis of the data reveals that certain regions, such as Europe and North America, have borne the brunt of the pandemic, reporting high infection and death counts. Conversely, countries like China have managed to maintain relatively lower infection rates through stringent containment measures.

- Despite varying levels of success in controlling the virus, the data underscores the need for continued vigilance, international cooperation, and robust public health measures to mitigate the spread of COVID-19 and minimize its adverse effects on global health and economies.


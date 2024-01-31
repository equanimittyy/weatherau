# weatherau
A basic statistical analysis of weather data in PowerBI. This exercise was intended as a self-directed introduction into PowerBI's DAX and MySQL in order to further technical abilities and improve familiarity with MS PowerBI and MySQL.

The analysis was required to find the following:

**Goal 1**: Identify, for the records found within Victoria, the times/dates at which rainfall were the highest,
and, at what temperature rainfall is most likely to fall.

**Goal 2**: Identify which state has the highest accumlative rainfall each year.

**Goal 3**: Identify possible relationships between rainfall amount to humidity and atmospheric pressure.

Data was sourced from Kaggle via the following link: 
https://www.kaggle.com/datasets/arunavakrchakraborty/australia-weather-data

## Analysis and Findings
### Victorian Rainfall
Analysis of weather data sourced from Kaggle identified that, within Victoria, rainfall averaged around 1.73mm between the observation period of 2007 to 2017.

Further, a maxmimum of 51.62mm of average rainfall (calculated by day) was identified on the 5th of February 2011.

![image](https://github.com/equanimittyy/weatherau/assets/104692345/df3a40c5-7afb-458d-bf1e-ad8ad7c6f887)

In order to calculate the temperature range that which rainfall would most likely occur, statistical analysis using confidence intervals were used where:


![image](https://github.com/equanimittyy/weatherau/assets/104692345/53269f55-3dce-491e-a4ff-b99ab07052cd)

Using a confidence level of 95% (i.e. a z value of 1.96), population size and mean we can calculate the range of temperature values wherein we have 95% confidence that rainfall occurs for the subset of data that includes only days where Rainfall > 0 (i.e. rainfall actually occurs). Accordingly, we can identify the range of temperature values that will with 95% certainty contain days with rainfall.

![image](https://github.com/equanimittyy/weatherau/assets/104692345/1622d1f7-2f71-4cca-9978-acc31ef5366d)

### State Accumalative Rainfall
The second goal was to identify, by state, which state had the highest accumalative rainfall for each year. The methedology to obtain these results entailed splitting each weather station locations by state, and summing the total rainfall based on year filters. Interestingly, it is important to note that there was an uneven distribution of weather stations per state:

**Weather Station Count**

VIC: 11

WA: 7

SA: 4

NT: 4

NSW: 14

QLD: 4

ACT: 2

TAS: 2

Noting the above, the results for accumalative rainfall were as follows:

![image](https://github.com/equanimittyy/weatherau/assets/104692345/ab8a0b8d-6b76-4b60-a0eb-48015825cdca)

### Rainfall, Humidity and Pressure Relationships
Thirdly and lastly, an analysis regarding rainfall, humidity and atmospheric pressure figures was made to understand and identify how these indicators may be related each other and ascertain any patterns, if any. There was some expected differences between the humidity and atmospheric measures at 9am and 3pm, though generally, the relationship between rainfall and these measures stayed similar despite the time changes. The relationship between rainfall and pressure was found to be normally distributed, whilst the relationship between rainfall and humidity was found to be a weak, negatively skewed distribution:

**Distribution with distinct datapoints**
_(Distribution of each distinct datapoint between rainfall, pressure and humidity.)_
![image](https://github.com/equanimittyy/weatherau/assets/104692345/b4f856f1-a10c-4566-a31e-4dde3aeb4b4a)

**Summarised Distribution with a count of rainfall per day**
_(This is to identify the frequencies of rainfall relative to pressure and humidity.)_
![image](https://github.com/equanimittyy/weatherau/assets/104692345/fecc2a1f-4b54-4440-a522-a7c03c06e2c9)

Accordingly, it is clear that there is a relationship between the occurence of rainfall relative to the atmospheric pressure and humidity of a given day with an ideal range for both humidity and pressure for which rainfall is most likely to occur.

## Limitations
### Assumptions
There are a number of limitations regarding the analysis and the data set used. For example, regarding the data set, there were a number of **assumptions** asserted:
- That the data itself is entirely accurate and that the errors presented through measurement error are inconsequential to the analysis;
- and that the source of the data is reliable. Whilst the Bureau of Meteorology is a government sponsered organisation and therefore deemed reliable, access to the data was through Kaggle, which does not necessitate reliability.

### Completeness of Data and Qualitative Evaluation

## Reflection


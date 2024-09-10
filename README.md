# AQI_Prediction

**AQI (Air Quality Index)** is a measure of the air pollution levels of a region, which can be used to speculate the potential health risks from exposure to polluted air. The value ranges from 0 to 500. Higher the value, greater is the level of pollution.
The project aims at building a prediction model to predict the AQI of a region. The dataset used is collected from the **Central Pollution Control Board - CCR Website**. The details regarding the dataset is provided for reference.
- **Link** : [Dataset](https://airquality.cpcb.gov.in/ccr/#/caaqm-dashboard-all/caaqm-landing/caaqm-data-repository)
- **Location** : Bagalkot, Karnataka
- **Station** : Vidayagiri,Bagalkot-KSPCB
- **Duration** : Jan 2021 - Dec 2023
- **Frequency of data collected** : 1 day
- **Raw Features** :
  - *Timestamp* :  Data and time of measurement
  - *PM2.5 (µg/m³)* : Concentration of particulate matter with diameter less than 2.5
  - *PM10 (µg/m³)* : Concentration of particulate matter with diameter less than 10
  - *NO (µg/m³)* : Concentration of Nitrogen monoxide
  - *NO2 (µg/m³)* : Concentration of Nitrogen Dioxide
  - *NOx (ppb)* : Concentration of Nitrogen oxides
  - *NH3 (µg/m³)* : Concentration of ammonia
  - *SO2 (µg/m³)* : Concentration of Sulphur dioxide
  - *CO (mg/m³)* : Concentration of Carbon Monoxide
  - *Ozone (µg/m³)* : Concentration of Ozone
  - *Benzene (µg/m³)* : Concentration of Benzene
  - *Toluene (µg/m³)* : Concentration of Toluene
  - *Xylene (µg/m³)* : Concentration of Xylene
  - *O Xylene (µg/m³)* : Concentration of 0-xylene
  - *Eth-Benzene (µg/m³)* : Concentration of ethylbenzene
  - *MP-Xylene (µg/m³)* : Concentration of m-xylene
  - *AT (°C)* : Ambient Temperature
  - *RH (%)* : Relative Humidity
  - *WS (m/s)* : Windspeed
  - *WD (deg)* : Wind direction
  - *RF (mm)* : Rainfall
  - *TOT-RF (mm)* : Total Rainfall
  - *SR (W/mt2)* : Solar Radiation
  - *BP (mmHg)* : Barometric Pressure
  - *VWS (m/s)* : Vertical Windspeed


**Data Engineering Pipeline**

<p align='center'>
	<img src='https://github.com/user-attachments/assets/dbf2ce15-fce0-416f-9a76-e832c6d674d5'/>
</p>

The folder consists of two analysis files - one using a pre trained model and the other built from scratch.

**Resource Analysis**
- The factors that majorly decide the resources needed for the entire process are - size of the data and the complexity of the prcoess.
- The process implemented in this project faces a bottleneck situation when it calculates the AQI for each data entry. As the size of the data grows the complexity of this stage over rules the overall complexity. This could lead to bringing in more computing resources in addition to the general computing resources.
- On the other hand, there is an ambigious upper bound for the size of the data. Since the data collected is of daily basis, even a considerable larger duration as that of a decade, results in only 3650 entries. This size of data is easily manageable using General Computing Resources such as Intel x86 or x64. Therefore, the implemented data pipeline process works efficiently on a CPU without the need for bringing in a GPU.

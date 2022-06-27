# PV_Data_Collection
 
Today, photovoltaic (PV) systems are widely integrated in industrial, commercial and residential applications. The output characteristics of PV systems are affected by atmospheric conditions and device aging. I am developing a data collection system. This system automatically and continuously collects and records the output characteristics and atmospheric conditions of the PV system. The details of the system are as follows.


##	PV strings (PVS) characteristic recording system
<div align="center">
  <img src="https://github.com/KangshiWang/pics/1.png">
</div>
The system has an automatic switching system (URL: ) Controlled by computer, the output characteristics of PV string with different PV modules (PVMs) are continuously recorded. It also records light (in LUS), solar irradiance (in W/m^2), wind speed (in m/s), wind direction, temperature (in Celsius), humidity (in %RH), PM2.5 (μg/m^3), PM10 (μg/m^3), rainfall data (mm).

Under the PVS/PV_WeatherStation folder, the daily atmospheric data is stored. The format of the subfolders is named according to the date of the record. The example read MATLAB script is xxx.mat.

Under the PVS/PV_dcLoad folder, the PV characteristic data is stored. The format of the subfolders is named according to the date of the record and the number of PVMs. For example, 2022-06-23_2 means the PV characteristic data is collected on 2022(year)-06(month)-23(day). ‘_2’ means the data is collected on a PVS with 2 serious connected PVMs. The example read MATLAB script is xxx.mat. 

Under the record folder of each group in each day, you can also see the following preview of the data (in JPG format).

Parameter| Value 
 ---- | ----- 
Maximum Power Pmpp | 50.00W 
Open Circuit Voltage Voc  | 22.02V  
Short Circuit Current Isc | 3.18A 
Voltage at Pmpp | 17.82V  
Current at Pmpp | 2.80A 
Cells per Module | 36  
 

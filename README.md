# PV_Data_Collection
 
Today, photovoltaic (PV) systems are widely integrated in industrial, commercial and residential applications. The output characteristics of PV systems are affected by atmospheric conditions and device aging. I am developing a data collection system. This system automatically collects and records the output characteristics and atmospheric conditions of the PV system. The details of the system are as follows.


##	PV strings (PVS) characteristic recording system

<div align="center">
  <img src="https://github.com/KangshiWang/pics/blob/main/1.png">
</div>

The system has an automatic switching system (URL: ). The output characteristics of PV string with different number of PV modules (PVMs) are continuously recorded. It also records light (in LUS), solar irradiance (in W/m^2), wind speed (in m/s), wind direction, temperature (in Celsius), humidity (in %RH), PM2.5 (μg/m^3), PM10 (μg/m^3), rainfall data (mm).

Under the **PVS/PV_WeatherStation** folder, the daily atmospheric data is stored. The format of the subfolders is named according to the date of the record. The example read MATLAB script is **xxx.mat**.

Under the **PVS/PV_dcLoad** folder, the PV characteristic data is stored. The format of the subfolders is named according to the date of the record and the number of PVMs. For example, 2022-06-23_2 means the PV characteristic data is collected on 2022(year)-06(month)-23(day). _2 means the data is collected on a PVS with 2 serious connected PVMs. The example read MATLAB script is **xxx.mat**. 

Under the record folder of each group in each day, you can also see the following preview of the data (in JPG format).

<div align="center">
  <img src="https://github.com/KangshiWang/pics/blob/main/2.jpg">
</div>

This preview graph shows the history of maximum power point power (Pmpp), maximum power point voltage (Vmpp), open circuit voltage (Voc), and short circuit current (Isc). Note that the horizontal axis indicates the number of data points rather than the actual time.

The **previewOneDay.m** script can preview one day data. For example, change these codes to:

 <span style="color:#333333">`date_str='2022-06-23';` </span> 
 
 <span style="color:#333333">`endframe_pv='_2';` </span>  
 
run the **previewOneDay.m**, you can get this:

<div align="center">
  <img src="https://github.com/KangshiWang/pics/blob/main/3.png">
</div>
 
Note that the horizontal axis is in actual time. 

The sky images are recorded in the **PVS/CAM directory**. For example, as the following images.
<div align="center">
  <img src="https://github.com/KangshiWang/pics/blob/main/4.jpg">
</div> 

The specifications for the PV modules in this data collection system is shown as follows:
Parameter| Value 
 ---- | ----- 
Name | SWM10W
Maximum Power Pmpp | 10.00W 
Open Circuit Voltage Voc  | 18.68V  
Short Circuit Current Isc | 0.53A 
Voltage at Pmpp | xxV  
Current at Pmpp | xxA 
Cells per Module | xx 
Size | 290*240*17mm
Manufactor | DONGGUAN SUNWORLD CO.,LTD

##	PV modules (PVMs) characteristic recording system

<div align="center">
  <img src="https://github.com/KangshiWang/pics/blob/main/5.png">
</div> 

Unlike the PVS characteristic recording system, the PVM characteristic recording system records the output characteristics of different PV modules. They have a similar system architecture, but different switching systems. The design files of the automatic switching system used in the PVM characteristic recording system could be found here: . 

The specifications for the PV modules in this data collection system is shown as follows:

Monocrystalline/Polycrystalline 30W PV module
Parameter| Value 
 ---- | -----  
Maximum Power Pmpp | 30.0W 
Open Circuit Voltage Voc  | 21.5V  
Short Circuit Current Isc | 2.5A 
Voltage at Pmpp | 18.5V  
Current at Pmpp | 1.5A   

(To be continued)

 
 

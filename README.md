# PV_Data_Collection
 
Nowadays, photovoltaic (PV) systems are widely integrated in industrial, commercial and residential applications. The output characteristics of PV systems are affected by atmospheric conditions and device aging. This automatic data collection system collects and records the output characteristics and atmospheric conditions of the PV system. The details of the system are as follows.

## Data-set Link

Google Drive

<https://drive.google.com/drive/folders/1s6uMW6d0xD_Iv5dUj78k7jUzsvoMfuV4?usp=sharing> 

Last Update on 29, June, 2022

##	PV strings (PVS) characteristic recording system

<div align="center">
  <img src="https://github.com/KangshiWang/pics/blob/main/1.png">
</div>

The system has an automatic switching system (URL: ). The output characteristics of PV string with different number of PV modules (PVMs) are continuously recorded. It also records light (in LUS), solar irradiance (in W/m^2), wind speed (in m/s), wind direction, temperature (in Celsius), humidity (in %RH), PM2.5 (μg/m^3), PM10 (μg/m^3), rainfall data (mm).

Under the folder **PVS1/PV_WeatherStation**, the daily atmospheric data is stored. The format of the subfolders is named according to the date of the record. The example read MATLAB script is **xxx.mat**.

Under the folder **PVS1/PV_dcLoad**, the PV characteristic data is stored. The format of the subfolders is named according to the date of the record and the number of PVMs. For example, 2022-06-23_2 means the PV characteristic data is collected on 2022(year)-06(month)_23(day). _2 means the data is collected on a PVS with 2 series-connected PVMs. The example read MATLAB script is **xxx.mat**. 

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

The sky images are recorded in the **PVS1/CAM**. For example, as the following images.
<div align="center">
  <img src="https://github.com/KangshiWang/pics/blob/main/4.jpg">
</div> 

The specifications for the PV modules in the PVS1 collection system is shown as follows.
Parameter| Value 
 ---- | ----- 
Name | SWM10W
Maximum Power Pmpp | 10.00W 
Open Circuit Voltage Voc  | 22.32V  
Short Circuit Current Isc | 0.58A 
Voltage at Pmpp | 18.18V  
Current at Pmpp | 0.55A 
Cells per Module | 36 (Monocrystalline silicon) 
Size | 290 \times 240 \times 17 mm
Manufactor | DONGGUAN SUNWORLD CO.,LTD

##	PV modules (PVMs) characteristic recording system

<div align="center">
  <img src="https://github.com/KangshiWang/pics/blob/main/5.png">
</div> 

Unlike the PVS characteristic recording system, the PVM characteristic recording system records the output characteristics of different PV modules. They have a similar system architecture, but different switching systems. The design files of the automatic switching system used in the PVM characteristic recording system could be found here: . 

Under the folder **PVM1/PV_dcLoad**, different PVM's output characteristics are recorded. The folders are name with YYYY-MM-DD-Z, where Z is the module id form 'A' to 'Z'. For example, under the folder **PVM1/PV_dcLoad/2022-06-28_A**, it records the output characteristics of the PVM A on 2022-06-28. As for now, the chanel A-E and T-X, totally 10 chanels are used.

Chanel A-Z: Polycrystalline XKD-30W

Chanel T-X: Monocrystalline XKD-30W

The specifications for the PV modules in this data collection system are shown as follows.

Parameter| Value 
 ---- | -----  
Name | XKD-30W
Type | Monocrystalline or Polycrystalline
Maximum Power Pmpp | 30.0W 
Open Circuit Voltage Voc  | 22.02V  
Short Circuit Current Isc | 2.11A 
Voltage at Pmpp | 17.95V  
Current at Pmpp | 1.92A

The PVMs system records light (in LUS), temperature (in Celsius), humidity (in %RH), atmospheric pressure (kPa). Due to the fact that the two systems running almost synchronously, the atmospheric data collected in PVSs system is also valuebale for the PVMs system. There is a MATLAB script named with **previewOneDay.m** under **PVM1** folder. For example, change these codes to:

 <span style="color:#333333">`date_str='2022-06-28';` </span> 
 
 <span style="color:#333333">`endframe_pv='_A';` </span>  
 
Run it, you can have a preview of characsterstic and atmospheric data about PVM A on 2022-06-28. 

##	Important Updates
1. From 2022/07/02, new temperature sensors are added into the systems. For PV panels used in PVS and PVM data collection systems, three different temperature sensors are placed on the front, side and back of the PV panel. These data are stored in the folder **PVM1/PV_TempSensors/** and **PVS1/PV_TempSensors/**. Run the script **previewCompare2days.m**, you can get a figure that shows the comparsions between the ambient temperature and the PVM's temperature on a specific day. For example:
<div align="center">
  <img src="https://github.com/KangshiWang/pics/blob/main/6.bmp">
</div> 


##	Pictures
1. Rooftop system
<div align="center">
  <img src="https://github.com/KangshiWang/pics/blob/main/7.jpg">
</div> 

2. Indoor host PCs and DC Loads
<div align="center">
  <img src="https://github.com/KangshiWang/pics/blob/main/8.jpg">
</div> 
(To be continued)

##	Cautions
### 1. The daily maintenance of the system and the uploading of data are basically from 11pm to 12pm (China Standard Time, UTC +8), during which time the data may not be recorded continuously.
### 2. The data on a daily basis may not be continuous, as I may choose to shut down the entire system on certain days for maintenance.
### 3. I use the code from Richard Droste et al. to calculate the local sunrise and sunset times (https://rdroste.com/project/sunrise-sunset/).
### 4. The electroinc loads used in these systems are from ITECH ELECTRONIC CO.,LTD. (IT8511A+,IT8512).
### 5. The sky camera is not good enough to capture the sky image clearly. For example, the sky camera may be covered with dew at sunrise. I plan to replace this camera.
### 6. The rainfall data is collected from an optical rain gauge, and each system reset causes the cumulative number of rainfall to change to 0.

 
 
 

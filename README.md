Air Quality Exploratory Data Analysis (Task 2)
Task 2 of my virtual internship with SWYNEX Technologies. Exploratory analysis of the cleaned Air Quality dataset from Task 1, done in Excel.
Objective
Use the cleaned dataset from Task 1 to calculate important statistics, identify trends, patterns and anomalies, include charts, and explain at least five useful insights.
Dataset
About 9,000 hourly readings of air quality and weather, from March 2004 to April 2005. Parameters used:
Reference gas readings: CO(GT) in mg/m³, C6H6(GT) in µg/m³, NO2(GT) in µg/m³, NOx(GT) in ppb
Sensor response: PT08.S1(CO), a low-cost carbon monoxide sensor
Weather: T (temperature, °C) and RH (relative humidity, %)
NMHC(GT) was left out because almost all of its values were missing.
Tool
Microsoft Excel (formulas, pivot tables, charts, conditional formatting).
Method
Summary statistics: mean, median, minimum, maximum and standard deviation for each parameter.
Distribution charts: histograms for CO(GT), C6H6(GT), NO2(GT) and PT08.S1(CO).
Relationship chart: scatter plot of RH against T.
Outlier detection: the IQR method, flagging values below Q1 − 1.5×IQR or above Q3 + 1.5×IQR.
Correlation matrix: CORREL across 7 variables, shown as a colour-scale heatmap.
Key insights
The data is right-skewed. Most hours have low pollution, with a long tail of high readings. The mean is above the median for CO (2.15 vs 1.8), C6H6 (10.08 vs 8.24) and NOx (246.9 vs 179.8), so the median describes a typical hour better.
Anomalies are all high spikes. NOx had the most outliers (436 readings, about 6%), then C6H6 (230, about 3%), CO (215, about 3%) and NO2 (108, about 1%). Every lower fence was negative, so there are no low-end outliers. The most extreme reading was C6H6 at 63.7 µg/m³ (about seven standard deviations above the mean) at 10 AM on 22 November 2004. Neighbouring hours were not checked, so it is unclear whether this was a real pollution event or a sensor error.
Pollutants move together. CO and C6H6 are strongly correlated (r = 0.93), and CO and NOx fairly strongly (r = 0.80). This suggests shared sources, most likely traffic.
The low-cost sensor tracks the reference instrument. PT08.S1(CO) correlates with CO(GT) at r = 0.88, so it follows CO well, although it would still need calibration.
Weather has little effect on pollution. Temperature and humidity are moderately negatively correlated (r = −0.58), matching the scatter plot. Their correlations with the pollutants stay between about −0.27 and +0.22.
Limitations
Correlation does not prove causation.
The extreme readings were flagged but not verified.
No time-trend chart is included, so daily and seasonal patterns were not analysed.
Files
Air_Quality_EDA.xlsx: the Excel workbook. Sheets: AirQualityUCI (raw data), Clean_Data, Outliers, Working_Sheet (statistics and charts).
Video walkthrough: see the link above.

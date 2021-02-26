# Prediction of African soil fertility from cheap analytical data

## 1. Background

The goal of this model is to find a correlation between the soil elemental analysis and its fertility.

One of the main bottlenecks in scaling soil surveillance has been the high cost of wet chemical methods for soil nutrient measurements. AfSIS has pioneered the usage of lower-cost dry chemical methods that run only on the cost of electricity, and which, when calibrated against wet chemistry and coupled with machine learning, can infer the concentrations of certain nutrients quite well. Still this is not a direct correlation to fertility.

In this work we tried to correlate measurements taken using "dry chemistry", i.e. XRF and FTIR spectroscopy to the presence of crops.
This alghorithm would ideally allow a quick and cheap screening to assess the soil quality.


---
![tested_samples](/img/folium.png)

## 2. The data
The dataset hosted at `arn:aws:s3:::afsis` contains field and laboratory measurements of soil samples collected through the Africa Soil Information Service (AfSIS) project, which spanned from 2009 through 2018. Georeferenced soil samples were collected from many countries throughout Sub-Saharan Africa, and their nutrient content was analyzed using *both* wet chemistry (e.g. Mehlich-3) and dry chemistry (e.g., infrared spectroscopy, x-ray fluorescence).
[Cleaning and exploratory analysis code](https://github.com/opsabarsec/African-soil-chemistry-fertility-correlation/blob/master/afsis-soil-chem-EDA.ipynb)

# 3. The model

Fertility has been correlated to soil Chemistry using Logistic Regression, 83% accuracy. 
![model_LR](/img/logisticregression.png)

FTIR data have been modeled and a possible correlation of infrared peak intensity to soil compositional parameters has been modeled using

- Partial Least Squares (PLS) regression
- Random Forest regression
- A custom-made convolutional neural network

Details (in French) on the [report.](https://github.com/opsabarsec/African-soil-chemistry-fertility-correlation/blob/master/documents/P7_report.pdf) 

![model](/img/CNN.png)

[Models code](https://github.com/opsabarsec/African-soil-chemistry-fertility-correlation/blob/master/afsis-soil-chem-MODEL.ipynb)




# AfSIS Soil Chemistry Data -from AWS S3 bucket 

The goal of this model is to find a correlation between the soil elemental analysis and its fertility.
We tried to correlate measurements taken using "dry chemistry", i.e. XRF and FTIR spectroscopy.
Those are much quicker and cheaper than chromatography and ideally this alghorithm would allow a quick screening to assess the soil quality.


---
![tested_samples](/img/folium.png)

The dataset hosted at `arn:aws:s3:::afsis` contains field and laboratory measurements of soil samples collected through the Africa Soil Information Service (AfSIS) project, which spanned from 2009 through 2018. Georeferenced soil samples were collected from many countries throughout Sub-Saharan Africa, and their nutrient content was analyzed using *both* wet chemistry (e.g. Mehlich-3) and dry chemistry (e.g., infrared spectroscopy, x-ray fluorescence).


# Data EDA + modelling

Fertility has been correlated to soil Chemistry using Logistic Regression

FTIR data have been modeled and a possible correlation of infrared peak intensity to soil compositional parameters has been modeled using

- Partial Least Squares (PLS) regression
- Random Forest regression
- A custom-made convolutional neural network

Details (in French) on the report available in the folder
documents/P7_report.pdf

![model](/img/CNN.png)




# Historical context

Soil is vital to life on Earth. It is our natural reservoir for storing and moving all the nutrients, liquids, and gases needed for life, including 90% of all water for food production, and 2300 Gigatons of organic carbon. And yet, while humankind has depended on soil since the beginning of civilization, we still know extremely little about it. In most parts of the world, both the public and private agricultural sectors remain extremely uninformed about the nutrient content and overall health of the soil beneath our feet.

The Africa Soil Information Service (AfSIS) was created to address this information gap in Africa and develop clever strategies for collecting the missing soil data. We focus on Africa because the future of the continent depends on Africa’s agricultural growth, and Africa’s soils are enduring widespread nutrient depletion and erosion. The data scarcity problem in Africa is also exceptional --- prior to the AfSIS project, the amount of publicly available soil chemistry data across the continent of Africa was no more than 18533 samples. (See [QED: Legacy African Soil Data, Descriptive Statistics](https://africa-legacy-soil-data.qed.ai) for more details.)

One of the main bottlenecks in scaling soil surveillance has been the high cost of wet chemical methods for soil nutrient measurements. AfSIS has pioneered the usage of lower-cost dry chemical methods that run only on the cost of electricity, and which, when calibrated against wet chemistry and coupled with machine learning, can infer the concentrations of certain nutrients quite well. The dataset here provides a start for building these inference models, and will be updated over time as more data comes in. All data is first collected by our partner labs into [AfSIS DB](https://afsisdb.qed.ai), a web-based data portal providing centralized storage and lookup of raw soil chemistry data sans transformations, and curated archives can now also be disseminated through the Registry of Open Data on AWS.

For a quick and casual introduction to the big picture, you are invited to view our [Goalkeepers 2018 video](https://www.youtube.com/watch?v=Fb9R0CnPMkc) about soil mapping.

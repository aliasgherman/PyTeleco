# PyTeleco
Short snippet collection (RAN/Core/TX Teleco Data centric)

**Wherever the README refers to 'this notebook' it simply means this repository :)**

# Introduction

This notebook is designed to be a walk-through of simple exercises on real RF Network Data (Telecom Network) to help the reader get familiarized with the common Python functions and Libraries which may be useful for day to day work.
The notebook is designed to be a comprehensive study starting from basic **data exploration** and then moving into **data transformation** and finally **Machine Learning**

# Assumptions

* Reader is familiar with **common RF datasets**. Like Cell level stats, BSC level stats, MSC/MGW/EPS Counters and stats
* Reader has some background in **Python** Programming and knows how to navigate a **Jupyter** notebook

# Disclaimer

* All notebooks are designed as small functions which can be run independently
* Only a moderate level of care is taken to reduce memory footprint / cpu usage. This is not the code written for **constrained resources**
* This is not a guide to write **Pretty** programs. I absolutely hate *code golfing*. [https://en.wikipedia.org/wiki/Code_golf]

# Common Definitions [Ignore if you know these]

## Numerical Variables

* Our bread and butter. All the KPIs, counters, statistics are usually numeric and continuous. These include CDR, CSSR, Traffic, Throughput, Latency etc. For telecom dataset, we usually have ALL Numeric data apart from Date/Time, Cell Names, Site Names, RNC/BSC Names, MME/MSC/MGW Names, VLAN IDs etc.
* If we know that our data has some strings in a numerical column then we should try to clean it up as much as possible. (Code included in second snippet. Read notebook for details)

## Categorical Variables

* Data which is defined as categories. Example is Gender (Male, Female) or Alarm Types (Major, Minor, Critical)
* Extremely rare for Telecom datasets

### Nominal Variables

* A categorical variable which has no order defined. Example is Gender (Male / Female) where no order should be assumed

### Ordinal Variables

* A categorical variable which has some order. Like Alarms. Critical, Major, Minor can be ordered based on severity


## Univariate Analysis

* Analyze each variable one-by-one. This is the common way of a data analysis by an RF Engineer. We usually look into each feature separately. (Like CDR, CSSR, Traffic etc.). 

## Multi-variate Analysis

* Analyze relationship between two or more variables. Like impact of Traffic vs. Throughputs. This is the type of analysis which provides a higher level of picture and most Telecom engineers are starting to utilize such charts (going beyong Line/Bar towards Scatter/PCA etc.) 
* Hopefully, you shall be able to utilize such analyses for a deeper understanding of trends

## Sample vs. Population Statistics

* We consider all definitions as being population values and not a sample value. This is true considering the nature of our dataset as we are not trying to infer a larger population values based on a sample of the data. For serious Data Scientists, please note that there is a significant difference between Population and Sampling and appropriate care should be taken for other projects.
* Population is the entire group. Sample is a (*representative*) small small sample from a population.

## Population Mean

*  μ = Σ (X)/ N
    * μ = Population Mean
    * Σ(X) = Sum of all items X
    * N = Number of items
    
## Z-Score

* Distance of an item (in terms of standard deviations) from the mean of the population/sample
* Useful to construct list of Worst performing cells by targetting cells which are far from the overall Network means



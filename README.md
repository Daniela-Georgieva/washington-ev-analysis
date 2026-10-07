# Washington State Electric Vehicle Analysis

This project looks at electric vehicle registrations in Washington State using both Power BI and Python. The goal was to better understand what types of EVs are registered, where most EVs are located, and how electric range has changed over the years.

## Project Overview

The project has two main parts:

* **Power BI dashboard** (`EV_Dashboard_Washington.pdf`) – includes key KPIs, range vs. price, the counties with the most EVs, EV type distribution, and a detailed vehicle table. The dashboard also includes filters for make, model year, EV type, range category, and Clean Fuel eligibility.
* **Python analysis** (`EV_Washington_Analysis.ipynb`) – focuses on data cleaning, exploring electric range over time, and comparing BEVs and PHEVs statistically.

## Key Findings

* BEVs make up about **78%** of all EVs in the dataset. The rest are PHEVs.
* King County has about half of all the EVs in the dataset, so it has the most EVs by far.
* For about **46%** of the vehicles, the electric range is shown as 0. These 0 values are actually missing data, so I treated them as missing instead of real 0-mile ranges.
* Only about **2.3%** of vehicles have price information, so the range vs. price analysis is based on a small part of the dataset.
* For BEVs, the average known range increased from about **75 miles in 2011 to around 210 miles in 2018–2019**.
* The increase in 2020 should be looked at carefully. Many of the BEVs with known range that year were Tesla Model 3 and Model Y, which was one reason the average increased.
* From 2011 to 2020, BEVs had an average range of about **195 miles**, while PHEVs had an average of about **32 miles**. That is a difference of about **163 miles**. The 95% confidence interval for the difference was **162.3 to 163.8 miles** based on a Welch's t-test.

## Data Limitations

* Each row in the dataset is a registered vehicle, not a unique car model. This means that popular models, especially Tesla vehicles, have a bigger effect on the results.
* Range data is available for most BEVs up to 2020, but there is very little range data for vehicles from 2021 and later. Because of this, the range analysis only goes up to 2020.
* Most vehicles do not have price information. Only about **2.3%** have a recorded price, so the range vs. price chart does not represent the whole dataset.
* Clean Fuel eligibility is related to battery range. Because of this, comparing the range of eligible and non-eligible vehicles would not be a fair comparison. I included it in the dashboard for information, but did not use it in the statistical analysis.

## Tools Used

* Power BI
* Power Query
* Python
* pandas
* NumPy
* matplotlib
* seaborn
* SciPy
* Jupyter Notebook / Google Colab

## Data Source

[Electric Vehicle Population Data (Washington State), Kaggle](https://www.kaggle.com/datasets/willianoliveiragibin/electric-vehicle-population)

## How to Run the Notebook

1. Download the dataset from Kaggle.
2. Open `EV_Washington_Analysis.ipynb` in Google Colab.
3. Run the first cell and upload the CSV file when asked.
4. Run the remaining cells to see the analysis.


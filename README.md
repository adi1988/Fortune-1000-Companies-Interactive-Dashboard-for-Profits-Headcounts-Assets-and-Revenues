# Fortune 1000 Companies Interactive-Dashboard-for-Profits-Headcounts-Assets-and-Revenues

Documentation page given along with this which gives an explanation of the dashboard

This was created with data from earlier repository raw data (see files from Companies that Suffered and were Resilient during Pandemic) as a single dashboard for users to get an understanding of data of the parameters - Profits, Headcounts, Assets and Revenues of Fortune 1000 companies for years 2018 - 2021 in a visualization format

## SQL Query
create view vw_all as

(select a.Company_Name,a.Type_of_Industry,

a.Number_of_Employees Headcount_2021,b.Number_of_Employees Headcount_2020,

c.Number_of_Employees Headcount_2019,d.Number_of_Employees Headcount_2018,

a.Profits Profits_2021,b.Profits Profits_2020,c.Profits Profits_2019,d.Profits Profits_2018,

a.Assets Assets_2021,b.Assets Assets_2020,c.Assets Assets_2019,d.Assets Assets_2018,

a.Revenues Revenues_2021, b.Revenues Revenues_2020, c.Revenues Revenues_2019, d.Revenues Revenues_2018,

from dbo.Year_2022 a,dbo.Year_2021 b,dbo.Year_2020 c,dbo.Year_2019 d,dbo.Year_2018 e

where a.Unique_ID=b.Unique_ID and b.Unique_ID=c.Unique_ID and b.Unique_ID=d.Unique_ID)


## Python (Pandas) -  To get line graphs
### Code --

pip install xlrd
pip install openpyxl

import pandas as pd
import numpy as np
from pandas import Series,DataFrame

#### Downloaded the excel tables for 2018-2022 companies

Fortune1000dataset = pd.ExcelFile('Fortune_1000_2018_2022_companies_data.xlsx')

dframe2022 = Fortune1000dataset.parse('2022')

dframe2021 = Fortune1000dataset.parse('2021')

dframe2020 = Fortune1000dataset.parse('2020')

dframe2019 = Fortune1000dataset.parse('2019')

dframe2018 = Fortune1000dataset.parse('2018')


#### Sorted Years into each so could subsequently concat to get a single dataset and vizualize by year in linegraphs

dframe2022['Year'] = 2022

dframe2021['Year'] = 2021

dframe2020['Year'] = 2020

dframe2019['Year'] = 2019

dframe2018['Year'] = 2018


#### To check if the structure of the dataframes are correct

dframe2022.head()

dframe2021.head()

dframe2020.head()

dframe2019.head()

dframe2018.head()

concat_dframe = pd.concat([dframe2018,dframe2019,dframe2020,dframe2021,dframe2022], ignore_index = True)

concat_dframe.sort_values('Company Name',ascending=True)


#### Export back into excel to get a final concatinated dataset which can then be imported into PowerBI

concat_dframe.to_excel('Fortune1000_concatinated.xlsx')




## Attached are four files

Documentation (Line Graphs), PowerBI Line Graphs
Documentation, PowerBI vizualization

### Documentation (Line Graphs)
https://github.com/adi1988/Interactive-Dashboard-for-Profits-Headcounts-Assets-and-Revenues/blob/main/Python-%20Pandas%20Script%20for%20Line%20Graphs.pdf

### PowerBI (Line Graphs)
https://github.com/adi1988/Interactive-Dashboard-for-Profits-Headcounts-Assets-and-Revenues/blob/main/Fortune%201000%202018-2022%20(line%20graphs).pbix

### Documentation
https://github.com/adi1988/Interactive-Dashboard-for-Profits-Headcounts-Assets-and-Revenues/blob/main/Creating%20a%20Single%20Interactive%20Dashboard%20for%20Profits%2C%20Headcounts%2C%20Assets%20and%20Revenues%20.pdf

### PowerBI 
https://github.com/adi1988/Interactive-Dashboard-for-Profits-Headcounts-Assets-and-Revenues/blob/main/Interactive%20Dashboard%20for%20Profits%2C%20Headcounts%2C%20Assets%20and%20Revenues.pbix
#### PowerBI - need to have PowerBI installed and then view raw/download in PowerBI)

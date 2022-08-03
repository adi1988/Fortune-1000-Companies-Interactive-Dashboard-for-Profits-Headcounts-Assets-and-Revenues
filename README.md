# Interactive-Dashboard-for-Profits-Headcounts-Assets-and-Revenues

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


## Attached are two files
Documentation, PowerBI vizualization

### Documentation
https://github.com/adi1988/Interactive-Dashboard-for-Profits-Headcounts-Assets-and-Revenues/blob/main/Creating%20a%20Single%20Interactive%20Dashboard%20for%20Profits%2C%20Headcounts%2C%20Assets%20and%20Revenues%20.pdf

### PowerBI 
https://github.com/adi1988/Interactive-Dashboard-for-Profits-Headcounts-Assets-and-Revenues/blob/main/Interactive%20Dashboard%20for%20Profits%2C%20Headcounts%2C%20Assets%20and%20Revenues.pbix
#### PowerBI - need to have PowerBI installed and then view raw/download in PowerBI)

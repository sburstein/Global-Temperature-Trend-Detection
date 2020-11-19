# Data Codebook

## df (GlobalLandTemperaturesByMajorCity joined with GlobalTemperatures)
`dt`: Year/month/day, starting in 1750 for average land temperature and 1850 for max and min land temperatures and global ocean and land temperatures   
`LandAverageTemperature`: global average land temperature in celsius   
`LandMaxTemperature`: global average maximum land temperature in celsius  
`LandMinTemperature`: global average minimum land temperature in celsius  
`LandAndOceanAverageTemperature`: global average land and ocean temperature in celsius  
`Country`: country of recorded data point  
`Latitude`: latitude of recorded data point  
`Longitude`: longitude of recorded data point  
`year`: year of recorded data point, taken from `dt`  
`month`: month of recorded data point, taken from `dt`  
`season`: season of recorded data point based on month  


## annual_avg
`year`: `year` from **df**  
`avg`: mean of `LandAverageTemperature` from all data of that year from **df**  
`max_avg`: mean of `LandMaxTemperature` from all months of respective year from **df**
`min_avg`: mean of `LandMinTemperature` from all months of respective year from **df**
`anomaly`: (`avg`) - (mean of `avg` from 1900-1980)  
`post1980`: logical variable: TRUE for years after 1980  
`post2000`: logical variable: TRUE for years after 2000  


## bycountrypre1950
`Country`: taken from **df**  
`avg`: mean of `LandAverageTemperature` in **df** from all data before 1950 for that country  
`lat`: mean of `Latitude` in **df** from all data before 1950 for that country 
`long`: mean of `Longitude` in **df** from all data before 1950 for that country  


## bycountry2010s
`Country`: taken from **df**  
`avg`: mean of `LandAverageTemperature` in **df** from all data after 2010 for that country  
`lat`: mean of `Latitude` in **df** from all data after 2010 for that country 
`long`: mean of `Longitude` in **df** from all data after 2010 for that country  


## changesbycountry
`country`: taken from **bycountry2010s**  
`change`: `avg` from **bycountry2010s** - `avg` from **bycountrypre1950s**  
`lat`: taken from **bycountry2010s**  
`long`: taken from **bycountry2010s**  
`continent`: continent of country  
`is_europe`: logical variable: TRUE for countries in Europe  
`is_northamerica`: logical variable: TRUE for countries in North America  
 
 
## differences
`year`: reference point year  
`differences`: (`avg` for `year` in **annual_avg**) - (`avg` of `year` - 1 in **annual_avg**)  
`net_diff`: absolute value of `differences`  


## fiveyearslopes
`year`: ID of five-year period between 1900-2010 
`slopes`: slope from linear model of **annual_avg** for `yearstart` to (`yearstart` + 5)  
`yearstart`: every five years, starting from 1900 up to 2010   

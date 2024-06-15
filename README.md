# Resale HDB Apartments Price Analysis

## Executive Summary

Based on the comprehensive analysis of the factors affecting resale prices in the housing market, it is evident that certain key variables play a significant role in determining the value of a property. The top 10 factors identified include floor area (sqm), highest floor level in the entire flat, number of rooms, upper floor levels, mid floor levels, year completed, lower floor levels, lease commence date, and HDB age. Among these factors, the number of room units, HDB age, and floor area exhibit the highest correlation with resale prices.

The correlation heatmap further illustrates the relationship between these factors and resale prices. It indicates that properties with a larger floor area, higher maximum floor level, and a greater number of room units tend to command higher resale prices. Conversely, flats located in buildings with more 3-room units and higher HDB age are associated with lower resale prices.

These findings provide valuable insights for stakeholders in the housing market, including buyers, sellers, and policymakers. Understanding the factors that influence resale prices can inform strategic decision-making and help optimize investments in real estate. Moving forward, continued research and analysis in this area will be essential for navigating the dynamic landscape of the housing market and promoting sustainable growth and development.

---

## Problem Statement

Real estate agencies are facing difficulties in providing HDB resellers with accurate market price quotes close to the HDB valuation. Our objective is to develop an analysis using historical data: Singapore Housing Dataset, to find variables affecting resale prices. This is to aid in more adiscovering factors that affects chages in the price of HDB apartment during the resale process to better provide a quote with a reasonable error margin to offer clients.

---

## Dataset

Resale HDB Flat Prices 2012 - 2023 [Source](https://www.kaggle.com/datasets/syrahmadi/resale-hdb-flat-prices-2000-2022)

---

## Data Dictionary

|Feature|Type|Description|
|---|---|---|
|**id**|*integer*|unique id for each transaction|
|**town**|*string*|HDB township where the flat is located, e.g. BUKIT MERAH|
|**flat_type**|*string*|type of the resale flat unit, e.g. 3 ROOM|
|**block**|*string*|block number of the resale flat, e.g. 454|
|**street_name**|*string*|street name where the resale flat resides, e.g. TAMPINES ST 42|
|**storey_range**|*string*|floor level (range) of the resale flat unit, e.g. 07 TO 09|
|**floor_area_sqm**|*float*|floor area of the resale flat unit in square metres|
|**flat_model**|*string*|HDB model of the resale flat, e.g. Multi Generation|
|**lease_commence_date**|*integer*|commencement year of the flat unit's 99-year lease|
|**resale_price**|*float*|the property's sale price in Singapore dollars|
|**tranc_year**|*integer*|year of resale transaction|
|**tranc_month**|*integer*|month of resale transaction|
|**mid_storey**|*integer*|median value of storey_range|
|**lower**|*integer*|lower value of storey_range|
|**upper**|*integer*|upper value of storey_range|
|**mid**|*integer*|middle value of storey_range|
|**full_flat_type**|*string*|combination of flat_type and flat_model|
|**address**|*string*|combination of block and street_name|
|**floor_area_sqft**|*float*|floor area of the resale flat unit in square feet|
|**price_per_sqft**|*float*|the property's price per square feet in Singapore dollars|
|**hdb_age**|*integer*|number of years from lease_commence_date to present year|
|**max_floor_lvl**|*integer*|highest floor of the resale flat|
|**year_completed**|*integer*|year which construction was completed for resale flat|
|**residential**|*string*|boolean value if resale flat has residential units in the same block|
|**commercial**|*string*|boolean value if resale flat has commercial units in the same block|
|**market_hawker**|*string*|boolean value if resale flat has a market or hawker centre in the same block|
|**multistorey_carpark**|*string*|boolean value if resale flat has a multistorey carpark in the same block|
|**precinct_pavilion**|*string*|boolean value if resale flat has a pavilion in the same block|
|**total_dwelling_units**|*integer*|total number of residential dwelling units in the resale flat|
|**1room_sold**|*integer*|number of 1-room residential units in the resale flat|
|**2room_sold**|*integer*|number of 2-room residential units in the resale flat|
|**3room_sold**|*integer*|number of 3-room residential units in the resale flat|
|**4room_sold**|*integer*|number of 4-room residential units in the resale flat|
|**5room_sold**|*integer*|number of 5-room residential units in the resale flat|
|**exec_sold**|*integer*|number of executive type residential units in the resale flat block|
|**multigen_sold**|*integer*|number of multi-generational type residential units in the resale flat block|
|**studio_apartment_sold**|*integer*|number of studio apartment type residential units in the resale flat block|
|**1room_rental**|*integer*|number of 1-room rental residential units in the resale flat block|
|**2room_rental**|*integer*|number of 2-room rental residential units in the resale flat block|
|**3room_rental**|*integer*|number of 3-room rental residential units in the resale flat block|
|**other_room_rental**|*integer*|number of "other" type rental residential units in the resale flat block|
|**postal**|*string*|postal code of the resale flat block|
|**latitude**|*float*|Latitude based on postal code|
|**longitude**|*float*|Longitude based on postal code|
|**planning_area**|*string*|Government planning area that the flat is located|
|**mall_nearest_distance**|*float*|distance (in metres) to the nearest mall|
|**mall_within_500m**|*float*|number of malls within 500 metres|
|**mall_within_1km**|*float*|number of malls within 1 kilometre|
|**mall_within_2km**|*float*|number of malls within 2 kilometre|
|**hawker_nearest_distance**|*float*|distance (in metres) to the nearest hawker centre|
|**hawker_within_500m**|*float*|number of hawker centres within 500 metres|
|**hawker_within_1km**|*float*|number of hawker centres within 1 kilometre|
|**hawker_within_2km**|*float*|number of hawker centres within 2 kilometre|
|**hawker_food_stalls**|*integer*|number of hawker food stalls in the nearest hawker centre|
|**hawker_market_stalls**|*integer*|number of hawker and market stalls in the nearest hawker centre|
|**mrt_nearest_distance**|*float*|distance (in metres) to the nearest MRT station|
|**mrt_name**|*string*|name of the nearest MRT station|
|**bus_interchange**|*integer*|boolean value if the nearest MRT station is also a bus interchange|
|**mrt_interchange**|*integer*|boolean value if the nearest MRT station is a train interchange station|
|**mrt_latitude**|*float*|latitude (in decimal degrees) of the the nearest MRT station|
|**mrt_longitude**|*float*|longitude (in decimal degrees) of the nearest MRT station|
|**bus_stop_nearest_distance**|*float*|distance (in metres) to the nearest bus stop|
|**bus_stop_name**|*string*|name of the nearest bus stop|
|**bus_stop_latitude**|*float*|latitude (in decimal degrees) of the the nearest bus stop|
|**bus_stop_longitude**|*float*|longitude (in decimal degrees) of the nearest bus stop|
|**pri_sch_nearest_distance**|*float*|distance (in metres) to the nearest primary school|
|**pri_sch_name**|*string*|name of the nearest primary school|
|**vacancy**|*integer*|number of vacancies in the nearest primary school|
|**pri_sch_affiliation**|*integer*|boolean value if the nearest primary school has a secondary school affiliation|
|**pri_sch_latitude**|*float*|latitude (in decimal degrees) of the the nearest primary school|
|**pri_sch_longitude**|*float*|longitude (in decimal degrees) of the nearest primary school|
|**sec_sch_nearest_dist**|*float*|distance (in metres) to the nearest secondary school|
|**sec_sch_name**|*string*|name of the nearest secondary school|
|**cutoff_point**|*integer*|PSLE cutoff point of the nearest secondary school|
|**affiliation**|*integer*|boolean value if the nearest secondary school has an primary school affiliation|
|**sec_sch_latitude**|*float*|latitude (in decimal degrees) of the the nearest secondary school|
|**sec_sch_longitude**|*float*|longitude (in decimal degrees) of the nearest secondary school|

---

## Conclusions

Properties with larger floor areas, higher maximum floor levels, and more room units typically command higher resale prices due to their spaciousness, elevated positioning, and versatility, which are highly valued by prospective buyers.

Conversely, flats in buildings with a higher proportion of 3-room units and those with a longer HDB age tend to have lower resale prices. This could be attributed to perceptions of limited space and potential maintenance concerns associated with older properties.

However, it's important to note that this analysis exclusively focuses on factors influencing the resale prices of HDB apartments. For a more robust predictive model that accurately forecasts actual prices, further research and development are necessary. Such a model would be invaluable for real estate agents seeking to provide precise and informed recommendations to their clients in the future.
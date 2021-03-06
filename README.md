    *Goals of this project.*

    1. Describe the data. 
    2. What features (columns) did you have to work with? 
    3. What features were you interested in? 
    4. Were the features numerical/categorical/text? 
    5. Was a lot of data missing? If so, what did you do to handle it? 
    6. How did features relate to each other, and the values that you were interested in? 
    7. Pictures are worth 1000s of words!

**Tasking**

    1. Data Frame csv files.  
    2. View each data-frame columns and verify IDs  
    3. Merge data-frames   
    4. Check for data inaccuracy ie. Missing values, inaccurate data types.   
    5. Transform data if needed.  
    6. Create charts and graphs to view.  

## Case Study

This project is a test case study on the efficiency on the use of the pandas, numpy and matplotlib libraries (libs). It is an official test case study and is meant to familiarizes the users with the use of the mentioned libs. The data is collected from kaggle “Transit Systems of World” project, which can be reviewed at the following link  [Data](https://www.kaggle.com/citylines/city-lines). It contains seven data-set CITIES, LINES, STATION_LINES, STATIONS, SYSTEMS, TRACK_LINES and TRACKS. Due to the scope and limited of time, the project will be limited to the following:

**CITY (7 columns)**
> 'id', 'name', 'coords', 'start_year', 'url_name', 'country',  'country_state'

**LINES(7 columns)**
> 'id', 'city_id', 'name', 'url_name', 'color', 'system_id', 'transport_mode_id'

**TRACKS(6 columns)**
> id', 'geometry', 'buildstart', 'opening', 'closure', 'length'

The 3 data-sets is merged as followed: 

    cities_track_lines = pd.merge(cities, track_lines, left_on = 'id', right_on = 'city_id', how = 'inner')

    cities_station_lines = pd.merge(cities, station_lines, left_on = 'id', right_on = 'city_id', how = 'inner')

    cities_lines = pd.merge(cities, lines, left_on = 'id', right_on = 'city_id', how = 'inner')

The scope has also been reduce to focus on the country ‘United States’ and the columns 'id_x', 'coords', 'start_year', 'url_name_x', 'country', 'country_state', 'city_id', 'name_y' is kept for further exploration.  

**The Data** 
 i  | Column        | Non-Null Count | Dtype | Feature Type
--- | ------        | -------------- | ----- | -------
 0  | id_x          | 142 non-null   | int64 | numeric
 1  | coords        | 142 non-null   | object| ?
 2  | start_year    | 142 non-null   | float64| numeric 
 3  | url_name_x    | 142 non-null   | object | ?
 4  | country       | 142 non-null   | object | ?
 5  | country_state | 142 non-null   | object | ?
 6  | city_id       | 142 non-null   | int64  | numeric
 7  | name_y        | 142 non-null   | object | ?
 
**Data Overiew**

![Overview of Cities in the data set](https://github.com/tibrado/GDS-Pandas-EDA-Case-Study/blob/master/images/cityfreq.png)
![Rail Line per City](https://github.com/tibrado/GDS-Pandas-EDA-Case-Study/blob/master/images/numcitylines.png)

EDIT: title is california
<img src="https://github.com/tibrado/GDS-Pandas-EDA-Case-Study/blob/master/images/Screen%20Shot%202021-02-05%20at%203.28.19%20PM.png" width="500" height="400">
<img src="https://github.com/tibrado/GDS-Pandas-EDA-Case-Study/blob/master/images/Screen%20Shot%202021-02-05%20at%203.45.41%20PM.png" width="400" height="400">
<img src="https://github.com/tibrado/GDS-Pandas-EDA-Case-Study/blob/master/images/Screen%20Shot%202021-02-05%20at%203.45.51%20PM.png" width="400" height="400">
<img src="https://github.com/tibrado/GDS-Pandas-EDA-Case-Study/blob/master/images/USAStartDate.png" width="600" height="400">

### Conclusion:

After analyzing our gathered data, we have concluded the following points:

    1.  New York City has the most transit systems, Cincinati has the fewest.
    2.  Boston and San-Fransisco have the oldest and newest tain systems.
    3.  Washington D.C. has a total of 10 lines.

>In the future, we will explore the datasets more thoughtfully before extracting and presenting our information. Most of the graphs were barcharts and held very little data. We would like to expand into other types. Additionally, we would like to include more meaningful data such as means and medians, however these stats were not very helpful in the set of data we chose to explore.

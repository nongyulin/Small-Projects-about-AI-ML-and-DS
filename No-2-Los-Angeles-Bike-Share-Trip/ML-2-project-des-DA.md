# Los Angeles Metro Bike Share Trip Data Analysis

The original dataset could be find in [Kaggle](https://www.kaggle.com/cityofLA/los-angeles-metro-bike-share-trip-data). Based on the discription on KAggle, the dataset is updated daily (I doubt. Really?).

## Dataset Columns

- Trip ID,(eg. 1912818)
- Duration (sec),(eg. 180)
- Start Time,(eg. 2016-07-07T04:17:00)
- End Time,(eg. 2016-07-07T04:20:00)
- Starting Station ID,(eg. 3014)
- Starting Station Latitude,(eg. 34.0566101)
- Starting Station Longitude,(eg. -118.23721)
- Ending Station ID,(eg. 3014)
- Ending Station Latitude,(eg. 34.0566101)
- Ending Station Longitude,(eg. -118.23721)
- Bike ID,(eg. 6281)
- Plan Duration,(eg. 30)
- Trip Route Category,(eg. Round Trip)
- Passholder Type,(eg. Monthly Pass)
- Starting Lat-Long,(eg. "{'longitude': '-118.23721', 'latitude': '34.0566101', 'needs_recoding': False}")
- Ending Lat-Long,(eg. "{'longitude': '-118.23721', 'latitude': '34.0566101', 'needs_recoding': False}")

## Steps (For people who don't have a lot of time to go through the details of the code.)

1. Import libraries
2. Import dataset "metro-bike-share-trip-data.csv"
3. Data exploration
	* look the general information of the dataset, how many records, how many columns and what types 
	* Check beginning of the dataset
	* check end of the dataset
	* Look the description of the dataset
	* Check the missing data
	* Check the duplicated data
	* Put _ instead of spaces in column names 
	* Draw Conclusion
		+ From above data exploration, it could be seen that the dataset contains 132426 records, in which no more than 38000 have null values. There are no duplicated records in this dataset. 
		+ So even the null records are dropped, the dataset still has very good quantity of records for furhter works. (If records quantity is small, a reasonable way should be found to fill the null values.)

		+ "Starting Lat-Long" is already included in "Starting Station Latitude" and "Starting Station Longitude". So "Starting Lat-Long" could be dropped.
		+ "Ending Lat-Long" is already included in "Ending  Station Latitude" and "Ending  Station Longitude". So "Starting Lat-Long" could be dropped.

		+ "Trip ID" is like an index and provides no additional info.
		+ "Plan Duration" and "Passholder Type" contains same info. "Plan Duration" represents in numbers, and "Passholder Type" represents in strings.
		+ The data and time in "Start Time" and "End Time" should be seperated for further analysis.
4. Data cleaning and preparation
	* Drop null values.
	* Drop 'Starting Lat-Long' and 'Ending Lat-Long'
	* Convert 'Start Time' and 'End Time'
	* Check dataset again
5. Data Analyzation and Visualization
	* Analysis on Duration
		+ Conclusion
			+ The majority of the trips are lower than 30 minutes long. From Metro Bike Share official website, it is known that "**Single ride fees are \\$1.75 for the first half hour, and \\$1.75 per half hour thereafter.**". These could be used to explain why most people only ride bikes less than 30 minutes.
	* Analysis on Trip Route Category
		+ Conclusion
			+ 90.23% users take One Way trip. The round-trip might be take for leisure or for fun.
	* Analysis on Passholder Type
		+ Conclusion:
			+ There are only three passholder types: Monthly Pass, Flex Pass, Walk-up.
			+ 61.43% users hold the Monthly Pass.
			+ The "Walk-up" users takes 31.21% in the total users, but they use bikes longer than other users. The total use time of "Walk-up" users takes the biggest percentage among these available types.
			+ In one way route, most users hold Monthly Pass. In round trip, most users hold Walk-up pass.
	* Analysis on start time (the most common pick-up time) 	
		+ Conclusion:
			+ The most popular time to pick up bikes are: 17-18h, 12-13h. 17-18h is after work hours, and 12-13h is lunch time.
			+ After 0h, the usage of bikes drops down, and starts going up.
	* Analysis on the top 5 popular places to pick up,  and return bikes
		+ Conclusion:
			+ For the top 5 popular places to pick up bikes:
				+ Starting_Station_ID 3030.0 is close to Grand Park, Los Angeles Police Department Headquarders, California Department of Transportation, Los Angeles City Hall, etc.
				+ Starting_Station_ID 3069.0 is close to Grand Central Market, Bradbury Building, Angels Flight Railways, etc.
				+ Starting_Station_ID 3005.0 is close to Macy's shopping center, a lot of restaurants and shopping malls, etc.
				+ Starting_Station_ID 3014.0 is close to a Union Station, Union Station- Metro Gold Line, etc.
				+ Starting_Station_ID 3031.0 is close to a lot of restaurants and shopping malls, etc.
			+ For the top 5 popular places to return up bikes:
				+ Ending_Station_ID 3005.0 is also the 3rd popular place to pick up bikes.
				+ Ending_Station_ID 3031.0 is also the 5th popular place to pick up bikes.
				+ Ending_Station_ID 3014.0 is also the 4th popular place to pick up bikes.
				+ Ending_Station_ID 3042.0 is close to Little Tokyo/Arts District Station, Japanese restaurants, Janpanese hotels, etc. (This is interesting, maybe further works could be done.)
				+ Ending_Station_ID 3069.0 is also the 2nd popular place to pick up bikes.
					
	
[Los Angeles Share Bike Fees](https://bikeshare.metro.net/user-agreement/) shows:
> Metro Bike Share pass fees and associated usage fees are listed on the website, at bikeshare.metro.net. Single ride fees are $1.75 for the first half hour, and $1.75 per half hour thereafter.


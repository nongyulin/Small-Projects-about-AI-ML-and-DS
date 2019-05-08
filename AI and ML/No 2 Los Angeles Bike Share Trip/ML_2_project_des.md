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

## Steps

1. Import libraries
2. Import dataset "metro-bike-share-trip-data.csv"
3. Data exploration
	* look the general information of the dataset, how many records, how many columns and what types 
	* Check beginning of the dataset
	* check end of the dataset
	* Look the description of the dataset
	* Check the missing data
	* Check the duplicated data
4. Data cleaning and preparation
	* Drop null values.
5. Data Analyzation and Visualization

[Los Angeles Share Bike Fees](https://bikeshare.metro.net/user-agreement/) shows:
> Metro Bike Share pass fees and associated usage fees are listed on the website, at bikeshare.metro.net. Single ride fees are $1.75 for the first half hour, and $1.75 per half hour thereafter.

<p>
Hey look at my map!
<iframe src="https://www.google.com/maps/embed/v1/view?key=AIzaSyA6V569KZ4lx97ZgygX3gSmnbDQmCbHkMg&center=34.0566101,-118.23721&zoom=19&maptype=satellite" width="600" height="450" frameborder="0" style="border:0" allowfullscreen></iframe>
</p>
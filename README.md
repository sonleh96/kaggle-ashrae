# ASHRAE - Great Energy Predictor III

The Jupyter Notebook in this repository is my own solution to the, now expired, Great Energy Predictor III competition by ASHRAE. It can be found using the link below

https://www.kaggle.com/c/ashrae-energy-prediction/overview


The objective of this competition is to use the given data on 1000 buildings over a three-year time frame to develop an accurate model on metered building energy consumption. The accuracy of the model is evaluated using the Root Mean Squared Logarithmic Error 

<a href="https://www.codecogs.com/eqnedit.php?latex=\epsilon&space;=&space;\sqrt{\frac{1}{n}&space;*&space;\sum_{i=1}^{n}&space;((\log{p_{i}&space;&plus;&space;1})&space;-&space;(\log{a_{i}&plus;1}))^2}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\epsilon&space;=&space;\sqrt{\frac{1}{n}&space;*&space;\sum_{i=1}^{n}&space;((\log{p_{i}&space;&plus;&space;1})&space;-&space;(\log{a_{i}&plus;1}))^2}" title="\epsilon = \sqrt{\frac{1}{n} * \sum_{i=1}^{n} ((\log{p_{i} + 1}) - (\log{a_{i}+1}))^2}" /></a>

ϵ is the RMSLE value (score)  
n is the total number of observations in the (public/private) data set,  
pi is your prediction of target,  
ai is the actual target for _i_,  
log(x) is the natural logarithm of x  


The dataset the following files:

__train.csv__
* building_id - Foreign key for the building metadata.
* meter - The meter id code. Read as {0: electricity, 1: chilledwater, 2: steam, 3: hotwater}. Not every building has all meter types.
* timestamp - When the measurement was taken
* meter_reading - The target variable. Energy consumption in kWh (or equivalent). Note that this is real data with measurement error, which we expect will impose a baseline level of modeling error. UPDATE: as discussed here, the site 0 electric meter readings are in kBTU.


__building_meta.csv__

* site_id - Foreign key for the weather files.
* building_id - Foreign key for training.csv
* primary_use - Indicator of the primary category of activities for the building based on EnergyStar property type definitions
* square_feet - Gross floor area of the building
* year_built - Year building was opened
* floor_count - Number of floors of the building

__weather_[train/test].csv__

Weather data from a meteorological station as close as possible to the site.

* site_id
* air_temperature - Degrees Celsius
* cloud_coverage - Portion of the sky covered in clouds, in oktas
* dew_temperature - Degrees Celsius
* precip_depth_1_hr - Millimeters
* sea_level_pressure - Millibar/hectopascals
* wind_direction - Compass direction (0-360)
* wind_speed - Meters per second

__test.csv__

* row_id - Row id for your submission file
* building_id - Building id code
* meter - The meter id code
* timestamp - Timestamps for the test data period


(The provided datasets were not uploaded due to their large sizes, but can be found in the above link)

This is my first experience working with Big Data and the LightGBM Regression algorithm. I will provide a report detailing my results and learning experience once the solution is complete. 






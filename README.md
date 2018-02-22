# the_crash_detective
Data Analysis on the Airplane Crash data since 1908 


Introduction 
The Control Flight into Terrain
Airline and Military flights are the safest way of travel in the world, accounting for one civilian accident per 1000,000 flight hours. However, given a long enough time frame, an interesting chronicle emerges from the collected airplane disasters.
A lot of interesting data points can be derived from this well documented collection. 

Airplane crash and Fatalities Layout on Kaggle
In order to analyze the data based on the given csv file, we can work here with 5268 data points from all segments of aviation. The column names and variable come from Kaggle:
 Variable Descriptions:
Date: 1908 – 2006  Format: Month/Day/Year
Time: 0 – 24           Format: h:min
Location: Global    Format: Mainz,Germany
Operator: Military/Postal/Civilian Format: Military -German Navy
Flight #              Format: Integer
Route                 Format :Demonstration
Type                  Format: De Havilland
Registration       Format: Integer
Cn/ln                 Format: String and Integers
Aboard              Format: Integer
Fatalities           Format: Integer 
Ground             Format: Integer
Summary          Format: Description (Strings)




Thematic Questions concerning the Airplane Data Set
(1)	How clean is the data set. 

The data set contains about ~5000 data entries per column and needs a lot of data wrangling concerning the Time and Date columns that contain inconsistent date formats.  Given that I tried to do a top down approach to fix all in one python code example, it took me too long to figures this out. What I did is I stripped out the two digit year and  created a new column called ‘Survivors’  which is the subtraction of the ‘Aboard’ column – ‘Fatalities’ column.

The date column indirectly created another problem because it spans more than a 100 years. It ignored the 1900’s and put everything from 2006 to 2106, which messed up the true period where the airplane catastrophes happened. With the help of Ramesh I found a way to display .

The Code to fix the Time issue is displayed here:

 


The Code to display the Year and the Survivors is displayed here:

 

(2)	How many airplane crashes per year? 
This took me a long time and the graph associated with it printed out the wrong type of Year. 

 

(3)	The associated graph shows clearly that the early period (1906 – 1930) and World War II  as a perilous developmental area. However, the early period of Jet powered aircraft increased the fatalities as well. However, since about the year 2000, we can see a significant drop in casualties.
(4)	Trying to find a visual ratio of the Survivors I printed out a similar graph but this type in a histogram. 

 
Here is the associated graph with it. 


 
Running a Spearman correlation, it provides a bit of an insight that the survival rate across the dataset is about 0.351 or about 1/3 which is collaborated in the previous graph. 

(5)	Is there an airline that stands out ( the one with the most crashes? 
Currently I have only a false answer here. Writing the Code here I have a problem where the graph only lists military crashes which is not what I was after …
The way I would like to find a solution is to run through the column called Operator and filter bye Civilian in the text…
 
 

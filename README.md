# 18-Tableau-Challenge

completed by Li Chen, 4/40/2024

*************************
Steps:
*************************

1- download JC 2023 data, 12 zip files (https://s3.amazonaws.com/tripdata/index.html)
2- extract and combine in Excel Power Query, save as JC_citibike_2023.csv
3- connect csv in Tableau, get data ready
	change [Start Lng], [End Lng] to longitude geographic role
	add calculated field
		[Duration]: DATEDIFF('minute',[Started At], [Ended At])
		[Round Trip]: [Start Station Name] = [End Station Name]
		[StartPoint]: MAKEPOINT([Start Lat], [Start Lng])
		[EndPoint]: MAKEPOINT([End Lat], [End Lng])
		[Path]: MAKELINE([StartPoint], [EndPoint])
		[Distance]: DISTANCE([StartPoint], [EndPoint], 'mi')
4- create visuals, build dashboards, finalize my story



*************************
Phenomena
*************************
expected:
popular start and end stations highly overlap.
member has more rides than casual, but casual rides longer distance.
member ride counts are stable during the week, casual rides significantly higher in weekend.
member ride peaks at commute hours, casual does not.

unexpected:
casual rides peak duration starts at 2am, my best guess is the rides are for exercise purpose, so they pick this time to start for less traffic impact.

over 3000 rides are missing start or end station, is this data error or user fault?
further check on map indicates those rides extend outside Jersey City border, maybe that is the reason.


*************************
Story: My Biking Plan
*************************
suppose I live in Jersey City and would like to ride citibike for leisure purpose.
so here is my research using 2023 data:
1. find out location and popularity of bike stations in city
2. look for best riding month, weekday and hours
3. decide bike type and route

my final choice would be: ride a classic bike for round trip at South Waterfront Walkway station in spring or fall months, and avoid commute hours.

tableau public workbook link: https://public.tableau.com/app/profile/leo.chen3760/viz/ttt_17144853586000/MyBikingPlan?publish=yes









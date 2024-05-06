AboveAvg = 
VAR Sales = [Total Sales]
VAR AvgSales = AVERAGEX(
    ALLEXCEPT(dimDates, dimDates[Date],  dimDates[Days in Month], dimDates[Month Of Year]),
    CALCULATE([Total Sales]))
var Result = IF(Sales > AvgSales, 1, 0)
RETURN Result

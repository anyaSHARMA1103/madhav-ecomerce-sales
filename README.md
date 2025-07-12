# madhav-ecomerce-sales
Total Sales = SUM(SalesData[Sales])

Total Profit = SUM(SalesData[Profit])

Total Quantity = SUM(SalesData[Quantity])

Profit Margin = DIVIDE([Total Profit], [Total Sales])

Sales YoY Growth = 
VAR CurrentYear = YEAR(MAX(SalesData[Order Date]))
VAR LastYear = CurrentYear - 1
RETURN
DIVIDE(
    CALCULATE([Total Sales], YEAR(SalesData[Order Date]) = CurrentYear) -
    CALCULATE([Total Sales], YEAR(SalesData[Order Date]) = LastYear),
    CALCULATE([Total Sales], YEAR(SalesData[Order Date]) = LastYear)
)

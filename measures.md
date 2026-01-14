1. \*\* Core Sales Measures \*\*

* Total Revenue =
  SUMX (
  'Sales Data',
  'Sales Data'\[OrderQuantity] \* RELATED ( 'Product Lookup'\[ProductPrice] )
  )

* Total Orders =
  DISTINCTCOUNT ( 'Sales Data'\[OrderNumber] )
* Order Quantity =
  SUM ( 'Sales Data'\[OrderQuantity] )
* Total Customers =
  DISTINCTCOUNT ( 'Sales Data'\[CustomerKey] )
* Average Revenue Per Customer =
  DIVIDE ( \[Total Revenue], \[Total Customers] )



2)\*\* Cost \& Profit Measures \*\*

* Total Cost =
  SUMX (
  'Sales Data',
  'Sales Data'\[OrderQuantity] \* RELATED ( 'Product Lookup'\[ProductCost] )
  )
* Total Profit =
  \[Total Revenue] - \[Total Cost]



3)\*\* Return Analysis \*\*

* Quantity Returned =
  SUM ( 'Returns Data'\[ReturnQuantity] )
* Total Returns =
  COUNT ( 'Returns Data'\[ReturnQuantity] )
* Return Rate =
  DIVIDE ( \[Quantity Returned], \[Order Quantity] )
* All Returns =
  CALCULATE ( \[Total Returns], ALL ( 'Returns Data' ) )
* % of All Returns =
  DIVIDE ( \[Total Returns], \[All Returns] )



4)\*\* Order Share \& Contribution \*\*

* All Orders =
  CALCULATE ( \[Total Orders], ALL ( 'Sales Data' ) )
* % of All Orders =
  DIVIDE ( \[Total Orders], \[All Orders] )



5)\*\* Time Intelligence Measures \*\*

* Previous Month Revenue =
  CALCULATE (
  \[Total Revenue],
  DATEADD ( 'Calendar Lookup'\[Date], -1, MONTH )
  )
* Previous Month Orders =
  CALCULATE (
  \[Total Orders],
  DATEADD ( 'Calendar Lookup'\[Date], -1, MONTH )
  )
* Previous Month Profit =
  CALCULATE (
  \[Total Profit],
  DATEADD ( 'Calendar Lookup'\[Date], -1, MONTH )
  )
* YTD Revenue =
  CALCULATE (
  \[Total Revenue],
  DATESYTD ( 'Calendar Lookup'\[Date] )
  )
* 10 Days Rolling Revenue =
  CALCULATE (
  \[Total Revenue],
  DATESINPERIOD (
  'Calendar Lookup'\[Date],
  MAX ( 'Calendar Lookup'\[Date] ),
  -10,
  DAY
  )
  )



6)\*\* Target \& Growth Measures\*\*

* Target Revenue =
  \[Previous Month Revenue] \* 1.1
* Target Orders =
  \[Previous Month Orders] \* 1.1
* Target Profit =
  \[Previous Month Profit] \* 1.1
* Revenue Target Gap =
  \[Total Revenue] - \[Target Revenue]
* Order Target Gap =
  \[Total Orders] - \[Target Orders]
* Profit Target Gap =
  \[Total Profit] - \[Target Profit]



7)\*\* Category-Specific Measures (Bike Analysis) \*\*

* Bike Sales =
  CALCULATE (
  \[Total Orders],
  'Product Categories Lookup'\[CategoryName] = "Bikes"
  )
* Bike Returns =
  CALCULATE (
  \[Total Returns],
  'Product Categories Lookup'\[CategoryName] = "Bikes"
  )
* Bike Return Rate =
  CALCULATE (
  \[Return Rate],
  'Product Categories Lookup'\[CategoryName] = "Bikes"
  )



8)\*\* Pricing \& Adjustment Measures \*\*

* Average Retail Price =
  AVERAGE ( 'Product Lookup'\[ProductPrice] )
* Overall Average Price =
  CALCULATE (
  \[Average Retail Price],
  ALL ( 'Product Lookup' )
  )
* Adjusted Price =
  \[Average Retail Price]
  \* ( 1 + 'Price Adjustment %'\[Parameter Value] )
* Adjusted Revenue =
  SUMX (
  'Sales Data',
  'Sales Data'\[OrderQuantity] \* \[Adjusted Price]
  )
* Adjusted Profit =
  \[Adjusted Revenue] - \[Total Cost]



9)\*\*  Advanced / Conditional Measures \*\*

* High Ticket Orders =
  CALCULATE (
  \[Total Orders],
  FILTER (
  'Product Lookup',
  'Product Lookup'\[ProductPrice] > \[Overall Average Price]
  )
  )
* Bulk Orders =
  CALCULATE (
  \[Total Orders],
  'Sales Data'\[OrderQuantity] > 1
  )
* Weekend Orders =
  CALCULATE (
  \[Total Orders],
  'Calendar Lookup'\[Days of week] = "Weekend"
  )



10)\*\* Customer-Level Display Measures\*\*

* Full Name (Customer Detail) =
  IF (
  HASONEVALUE ( 'Customer Lookup'\[CustomerKey] ),
  MAX ( 'Customer Lookup'\[Full Name] ),
  "Multiple Customers"
  )
* Total Orders (Customer Detail) =
  IF (
  HASONEVALUE ( 'Customer Lookup'\[CustomerKey] ),
  \[Total Orders],
  "-"
  )
* Total Revenue (Customer Detail) =
  IF (
  HASONEVALUE ( 'Customer Lookup'\[CustomerKey] ),
  \[Total Revenue],
  "-"
  )

# Tableau Supply Chain Dashboarding

## Procurement

* Cost per Unit
    SUM(OrderTotal)/SUM(OrderQuantity)

* Fulfillment accuracy
    Order Correct = IF {INCLUDE [OrderNum]:SUM([DeliveredQuantity]} = IF {INCLUDE [OrderNum]:SUM([OrderedQuantity]}
    THEN 1 ELSE 0
    END

    Percent of Correct Orders = {FIXED : SUM(Order Correct)}/COUNTD([OrderNum])

* Lead Time
    
    (Implicit)

    Promised Lead Time - Actual Lead Time

* Inbound Transportation Costs
    
    Per Unit Shipping = 
    {FIXED [Product Name]: SUM([ItemShippingCost])}/{FIXED [Product Name]: SUM([Quantity])}
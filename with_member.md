```
WITH 
MEMBER  [Measures].[Avg Sales Price] AS
        [Measures].[Dollar Sales] / [Measures].[Unit Sales]

SELECT
    { 
        [Measures].[Dollar Sales], 
        [Measures].[Unit Sales], 
        [Measures].[Avg Sales Price] 
    } ON COLUMNS,

    { 
        [Time].[Q1, 2005], 
        [Time].[Q2, 2005] 
    } ON ROWS

FROM [Sales]

WHERE ([Customer].[MA])

```

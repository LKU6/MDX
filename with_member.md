```
WITH MEMBER [Measures].[Avg Sales Price] AS ‘[Measures].[Dollar Sales] / [Measures].[Unit Sales]’

SELECT
{ [Measures].[Dollar Sales], [Measures].[Unit Sales], [Measures].[Avg Sales Price] } on columns,
{ [Time].[Q1, 2005], [Time].[Q2, 2005] } on rows

FROM Sales

WHERE ([Customer].[MA])
```

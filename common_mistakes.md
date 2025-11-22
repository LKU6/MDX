## confusing sets, tuples, and members
### Mistake: Using parentheses {} and () incorrectly.

* Why it happens: {} defines a set; () defines a tuple. 

```
SELECT [Measures].[Sales] ON COLUMNS, {[Date].[Calendar].[2025], [Date].[Calendar].[2026]} ON ROWS FROM [Sales]
```

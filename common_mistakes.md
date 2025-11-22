## Not testing iteratively
**Beginners often write huge MDX queries and expect them to work.**
**Fix**: Start small: test sets, members, and calculations one at a time.


## confusing sets, tuples, and members
### right way: {} defines a set; () defines a tuple. (mistake: Using parentheses {} and () incorrectly.)
```
SELECT [Measures].[Sales] ON COLUMNS, {[Date].[Calendar].[2025], [Date].[Calendar].[2026]} ON ROWS FROM [Sales]
```

## misunderstanding the WHERE clause
### right way: WHERE is a slicer, it fixes a dimension member across the cube. (mistake: WHERE does not works like SQL WHERE)
```
SELECT [Measures].[Sales] ON COLUMNS FROM [Sales] WHERE [Date].[Calendar].[2025]
```

## assuming MDX is like SQL
### MDX works on sets of tuples. Filtering and aggregation are set-based. (mistakes: Trying to do row-by-row logic like SQL)


## Using crossjoin incorrectly
**Mistake**: Forgetting that * or CROSSJOIN() produces a set of tuples, which can explode in size.

**Effect**: Query returns huge results or runs very slowly.

**Fix**: Limit the sets or use TOPCOUNT for large dimensions.

## Not understanding hierarchy levels
Mistake: Mixing members from different hierarchy levels incorrectly.
Example code:
```
[Date].[Calendar].[2025] + [Date].[Calendar].[January]
```
**fix:** combine members at the same level, or use functions like Descendants().

## overusing calculated measures

**Mistake**: creating too many calculated measures in the cube script for every small calculation.
**Effect**: Slows down the cube, makes maintenance hard.
**Fix**: Create only reusable or important calculations; ad hoc MDX can compute some values on the fly.

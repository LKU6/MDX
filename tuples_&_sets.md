
# MDX: Tuples and Sets Explained Simply

## 1 Tuple
- Imagine you are picking **one thing from each box**.  
- For example, you have:  

**Box 1:** Months → January, February  
**Box 2:** Fruits → Apples, Oranges  

A **tuple** is when you pick **one from each box** at the same time.  

- Example tuple:  
```

(January, Apple)

```
- This is like saying: “I want **January AND Apple together**.”  
- In MDX, tuples are written with parentheses: `(Member1, Member2)`
---

A tuple is a combination of members from one or more dimensions.

To compose a tuple with more than one dimension, you must wrap the members in parentheses, for example:
```
([Customer].[Chicago, IL], [Time].[Jan, 2005])
```
```
SELECT
  {
    ( [Time].[2005], [Measures].[Dollar Sales] ),
    ( [Time].[Feb, 2005], [Measures].[Unit Sales] )
  } ON COLUMNS ,
  { [Product].[Tools], [Product].[Toys]
  } ON ROWS

FROM [Sales]
```



---

## 2 Set
- Now imagine you want **many tuples together** — like a list of choices.  
- That’s a **set**.  
- Example set of tuples:  
```

{ (January, Apple), (February, Orange), (January, Orange) }

```
- Curly braces `{}` mean “this is a **collection of tuples**.”  

---

## 3 In MDX Tables
- A **tuple** points to **one cell** in the cube (one exact value)  
- A **set** points to **many cells** (a group of values)
```








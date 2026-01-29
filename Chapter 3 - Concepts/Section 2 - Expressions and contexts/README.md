# Expressions and Contexts

Polars has developed its own **Domain Specific Language (DSL)** for transforming data. The language is very easy to use and allows for complex queries that remain human readable. **Expressions** and **contexts** are the two key concepts that achieve this readability while enabling query optimization.

## Key Concepts

### Expressions
An **expression** is a lazy representation of a data transformation. Expressions are modular and flexible, meaning you can use them as building blocks to build more complex expressions.

```python
# Example: BMI calculation expression
bmi_expr = pl.col("weight") / (pl.col("height") ** 2)
```

Because expressions are **lazy**, no computations occur until they are executed in a **context**.

---

### Contexts

Polars expressions need a **context** in which they are executed to produce a result. The four most common contexts are:

| Context | Purpose | Key Behavior |
|---------|---------|--------------|
| `select` | Transform/compute columns | Returns **only** the columns you specify |
| `with_columns` | Add new columns | Keeps original columns **plus** adds new ones |
| `filter` | Filter rows | Keeps rows where condition is `True` |
| `group_by` + `agg` | Group and aggregate | Groups rows, then applies aggregations |

---

### Expression Expansion

Polars supports **expression expansion** - a shorthand notation for applying the same transformation to multiple columns:

```python
# Apply mean to multiple columns at once
pl.col("weight", "height").mean().name.prefix("avg_")

# Select by data type
(pl.col(pl.Float64) * 1.1).name.suffix("*1.1")
```

These expressions expand into multiple independent expressions that Polars can execute **in parallel**.

---

## Why This Matters

- **Lazy evaluation**: Polars can simplify expressions before running them
- **Parallel execution**: Separate expressions are embarrassingly parallel
- **Expression expansion**: Automatic parallelization across multiple columns
- **Query optimization**: The query engine finds the most efficient execution plan

## Code Examples

See [`code.ipynb`](./code.ipynb) for interactive examples covering:

1. Expression basics and BMI calculation
2. The `select` context with broadcasting
3. The `with_columns` context for adding columns
4. The `filter` context for row filtering
5. The `group_by` context with multiple aggregations
6. Expression expansion by column name and data type

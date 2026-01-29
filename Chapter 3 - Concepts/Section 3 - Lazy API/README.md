# Lazy API 

Overall, Lazy and Eager differ in the way they execute commands.

- Eager executes commands immediately.
- On the other hand, Lazy API have a execution plan, and it will allow Polars's query optimizer to hop in and help in reducing memory usage and improve overall performance.

## Previewing the query plan

- We can use `.explain()` to preview the query plan. It will explain the query, it's somewhat similar to SQL's explain command.
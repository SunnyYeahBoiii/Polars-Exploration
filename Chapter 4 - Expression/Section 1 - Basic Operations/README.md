# Basic Operations:

## Arithmetic operations:

- We can do basic operations like +, -, *, / to columns.

## Comparison operations:

- Besides, there are comparisions like ==, !=, <, >, <=, >=.

## Boolean operations:

- And boolean operations like &, |, ^, ~. These operations is implemented as methods and_() , or_() , xor_() , not_() .

## Conditional logic:

- We can use `when().then().otherwise()` to implement conditional logic.

## Counting values:

- `n_unique()` can be used to get the number of unique values in a column.
- `approx_n_unique()` can be used approximately count the number of unique values in a column by using an algorithm called HyperLogLog++.
- `value_counts()` can be used to get the count of unique values in a column.

## Conditionals:

- It acts like an if-else statement. By using `when()` for if, `.then()` for then and `.otherwise()` for else. 
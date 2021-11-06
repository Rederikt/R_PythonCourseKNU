---
title: "R Labs 2"
output: html_notebook
---

R Language labs
Kolumbet Anton

1. Create a vector v of 100 elements by command v <- rnorm(100). Show for this
vector: 10-th element; elements from 10-th to 20-th included; 10 elements
start from 20-th; elements that more than 0.

```{r}
v <- rnorm(100)
v[10]
v[10:20]
v[20:30]
v[v > 0]
```
2. Create data frame by command y <- data.frame(a = rnorm(100), b = 1:100, cc
= sample(letters, 100, replace = TRUE)). For this data frame show out: last 10
rows; rows from 10th till 20th included; 10-th element of column b; the whole
column cc, during this use the name of the column

```{r}
y <- data.frame(a = rnorm(100), b = 1:100, cc = sample(letters, 100, replace = TRUE))
last_ten = tail(y, 10)
last_ten
y[10:20, ]
y[10, "b"]
y[1:100 ,"cc"]
```

3. Create a vector z with elements 1, 2, 3, NA, 4, NA, 5, NA. For this vector:
display all not NA values; count average of all not NA values then count
including NA values. 

```{r}
z <- c(1, 2, 3, NA, 4, NA, 5, NA)
bad <- is.na(z)
z[!bad]
m <- z[!bad]
mean(m)
mean(z)
```


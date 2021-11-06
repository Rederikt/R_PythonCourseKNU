---
title: "Labs 2"
output: html_notebook
---

1. Function add2(x, y) that returns sum of two numbers.
```{r}
add2 <- function(a,b) {
  a+b
}
add2(3,2)
```
2. Function above(x, n), which takes the vector and the number n, and returns all
elements of the vector that are greater than n. By default n = 10.
```{r}
a <- c(1, 4, 2, 7, 3, 5)
above <- function(a ,n) {
  for (i in a) {
    if (i > n){
      print(i)
    }
  }
}
above(a, 3)
```

3. Function my_ifelse(x, exp, n), which takes vector x, compare all its elements
by using exp with n, and returns elements of the vector that match conditions
of expression. Example: my_ifelse(x, “>”, 0) returns all elements of x that
greater than 0. Exp can be equal to “<”, “>”, “<=”, “>=”, “==”. If exp doesn’t
match with any of those expressions returns vector x.
```{r}
x <- c(1, 4, 2, 7, 3, 5)
my_ifelse <- function(x, exp, n){
  if(exp == ">") {
    x[x > n]
  }
  else if (exp == "<") {
    x[x < n]
  }
  else if(exp == ">=") {
    x[x > n]
  }
  else if(exp == "<=") {
    x[x > n]
  }
  else if(exp == "==") {
    x[x > n]
  }
  else {
    x
  }
}

my_ifelse(x, "=h", 1)
```
4. Function columnmean(x, removeNA) which counts the mean value for each
column of the matrix, or data frame. The logical parameter removeNA
indicates whether to delete the NA value. By default, it is TRUE. 

```{r}
m1 <- c(0.5, NA, 0, 2, 1.3, 131, NA, 7, 3.5, 2.8, 4.6, NA)
x <- matrix(m1, nrow = 4, ncol = 3)


columnmean <- function(x, removeNA){
  mean(x[, 1])
  if (removeNA == F) {
    for (i in 1:3){
      m <- mean(x[, i])
      print(m)
    }
  }
  else {
    for (i in 1:3){
      xi <- x[, i]
      bad <- is.na(xi)
      m <- mean(xi[!bad])
      print(m)
    }
  }
}

columnmean(x, T)
```




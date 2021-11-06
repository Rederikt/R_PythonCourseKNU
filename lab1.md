---
title: "R Labs"
output: html_notebook
---

R Language labs
Kolumbet Anton

1. Create variables with basic (atomic) type. Basic types: character, numeric,
integer, complex, logical.

```{r}
character_var <- "A"
numeric_var <- 0.2
logical_var <- TRUE
integer_var <- 9
complex_var <- 3+2i

```
2. Create vectors that: contain a sequence from 5 to 75; contains the numbers
3.14, 2.71, 0, 13; 100 TRUE values.

```{r}
x <- 5:75
y <- c(3.14, 2.71)
z <- c(T, length=100)
z
```
3. Create the following matrix with function matrix and with cbind or rbind
0.5 1.3 3.5
3.9 131 2.8
0 2.2 4.6
2 7 5.1
```{r}
x1 <- c(0.5, 1.3, 3.5)
x2 <- c(3.9, 131, 2.8)
x3 <- c(0, 2.2, 4.6)
x4 <- c(2, 7, 5.1)

rbind(x1, x2, x3, x4)

m1 <- c(0.5, 3.9, 0, 2, 1.3, 131, 2.2, 7, 3.5, 2.8, 4.6, 5.1)
m <- matrix(m1, nrow = 4, ncol = 3)
m
```
4. Create a random list and include there all basic types.

```{r}
x <- list(3, "f", F, 2+2i, 2.01)
x
```
5. Create a factor with three levels «baby», «child», «adult».

```{r}
x <- factor(c("baby", "baby", "adult", "child", "adult"))
x
```
6. Find an index of the first NA value in the vector 1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11. Find the number of NA values.
```{r}
x <- c(1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11)
n <- is.na(x)
match(NA, x)
table(n)
```
7. Create a random data frame and display to the console.
8. Change column names of this data frame.

```{r}
x <- data.frame(chars = c("a", "n", "t", "o", "n"), nums = 1:5)
x
names(x) <- c("not nums", "not chars")
x
```

---
title: "R Lab 6"
output: html_notebook
---
1. Створити матрицю mat з 5 стовпцями та 10 строками за допомогою
matrix з випадковими даними (функція rnorm(50)).
```{r}
  mat <- matrix(rnorm(50), ncol=5, nrow=10)
  print(mat)
```

2. Знайти максимальне значення в кожному стовпці.
```{r}
  max_var <- apply(mat, 2, max)
  max_var
```

3. Знайти середнє (mean) значення кожного стовпця

```{r}
  mean_var <- apply(mat, 2, mean)
  mean_var
```

4. Знайти мінімальне значення в кожному рядку.

```{r}
  min_var <- apply(mat, 2, mean)
  min_var
```

5. Відсортувати кожен стовбець таблиці.

```{r}
  sort_var <- apply(mat, 2, sort)
  sort_var
```

6. Знайти кількість значень < 0 для кожного стовпця. Використати свою
функцію.

```{r}
  count_negative <- function(x) {
    return (sum(x < 0))
  }
  all_neg <- apply(mat, 2, count_negative)
  all_neg
```

7. Вивести вектор з булевими значеннями TRUE та FALSE. TRUE, якщо в
стовпці є елементи >2, FALSE – якщо немає

```{r}
  more <- function(x) {
    return (sum(x > 2) > 0)
  }
  all_more <- apply(mat, 2, more)
  all_more
```

8. Створить список list1 <- list(observationA = c(1:5, 7:3), observationB =
matrix(1:6, nrow=2)). Для цього списку знайдіть sum за допомогою lapply.

```{r}
list1 <- list(observationA = c(1:5, 7:3), observationB = matrix(1:6, nrow=2))
list1
sums <- lapply(list1, sum)


```

9. Для кожного елементу списку list1 знайдіть максимальне та мінімальне
значення (range) за допомогою lapply та sapply

```{r}
list_range_l <- (lapply(list1, range))
list_range_l

list_range_s <- (sapply(list1, range))
list_range_s
```

10.Для вбудованого набору даних InsectSprays знайти середнє count для
кожного spray

```{r}
  InsectSprays
  insect_count <- with(InsectSprays, split(count, spray))
  print(sapply(insect_count, mean))
```

